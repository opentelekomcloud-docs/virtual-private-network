:original_name: vpn_admin_0016.html

.. _vpn_admin_0016:

.. _en-us_topic_0000002315357777:

Configuring VPN When Fortinet FortiGate Firewall Is Used
========================================================

Scenarios
---------

This section describes how to create a VPN gateway and VPN connections on the cloud to connect your on-premises network to a VPC subnet if your local data center uses FortiGate firewalls as Internet egresses.

Topology Connection
-------------------

As shown in :ref:`Figure 1 <en-us_topic_0000002315357777__en-us_topic_0000001542174002_fig433914417515>`, the local data center has multiple Internet egresses. The egress 11.11.11.11 is specified to establish a VPN connection with a VPC. The subnet of the local data center is 10.10.0.0/16, and the VPC subnet is 172.16.0.0/24. The IP address of the VPN gateway you created on the cloud is 22.22.22.22. Create a VPN connection to connect your on-premises network to the VPC subnet.

.. _en-us_topic_0000002315357777__en-us_topic_0000001542174002_fig433914417515:

.. figure:: /_static/images/en-us_image_0000001970660305.png
   :alt: **Figure 1** Multi-egress on-premises network connecting to a VPC through a VPN

   **Figure 1** Multi-egress on-premises network connecting to a VPC through a VPN

Configure VPN connection policies on the cloud based on :ref:`Figure 2 <en-us_topic_0000002315357777__en-us_topic_0000001542174002_fig135126335202>`.

.. _en-us_topic_0000002315357777__en-us_topic_0000001542174002_fig135126335202:

.. figure:: /_static/images/en-us_image_0000001542493866.jpg
   :alt: **Figure 2** Policy details

   **Figure 2** Policy details

Configuration Procedure
-----------------------

This example describes how to configure a VPN when a FortiGate firewall is used in your local data center.

#. Configure IPsec VPN.

   a. Create a tunnel.
   b. Configure the basic information for the tunnel.
   c. Configure IKE phase 1 parameters.
   d. Configure IPsec phase 2 parameters.
   e. Configure the IPsec tunnel.

#. Configure routes.

   a. Add a static route.

      Add a route to the cloud VPC subnet 172.16.0.0/24, with the outbound interface being the VPN tunnel interface.

   b. Configure policy-based routes for multiple egresses.

      Set the source address to the subnet of the local data center and the destination address to the subnet of the VPC. Adjust the configuration sequence of the policy-based routes to ensure that the policy-based routes will be preferentially used.

#. Configure policies and NAT.

   a. Configure a policy for access to the cloud from the local data center.
   b. Configure a policy for access to the local data center from the cloud.

Configuration Verification
--------------------------

#. Check whether the on-premises VPN status is normal.

2. Check whether the cloud-based VPN status is normal.

Configuration Using the CLI
---------------------------

#. Configure the physical interface.

   .. code-block::

      config system interface
         edit "port1"
              set vdom "root"
              set ip 11.11.11.11 255.255.255.0
              set type physical
      next
          edit "IPsec"                                  # Tunnel interface configuration
              set vdom "root"
              set type tunnel
              set interface "port1"               # Physical interface bound to the tunnel
                     next
               end

#. Configure interface zones.

   .. code-block::

      config system zone
          edit "trust"
              set intrazone allow
              set interface "A1"
          next
          edit "untrust"
              set intrazone allow
              set interface "port1 "
          next
      end

#. Configure subnets.

   .. code-block::

      config firewall address
               edit "hw-172.16.0.0/24"
              set uuid f612b4bc-5487-51e9-e755-08456712a7a0
              set subnet 172.16.0.0 255.255.255.0              # Subnet on the cloud
               next
          edit "local-10.10.0.0/16"
              set uuid 9f268868-5489-45e9-d409-5abc9a946c0c
              set subnet 10.10.0.0 255.255.0.0                     # Subnet of the local data center
          next

#. Configure IPsec.

   .. code-block::

      config vpn IPsec phase1-interface                                        # Phase 1 configuration
          edit "IPsec"
              set interface "port1"
              set nattraversal disable
              set proposal aes128-sha1
              set comments "IPsec"
              set dhgrp 5
              set remote-gw 22.22.22.22
              set psksecret ENC dmFyLzF4tRrIjV3T+lSzhQeU2nGEoYKC31NaYRWFJl8krlwNmZX5SfwUi5W5RLJqFu82VYKYsXp5+HZJ13VYY8O2Sn/vruzdLxqu84zbHEIQkTlf5n/63KEru1rRoNiHDTWfh3A3ep3fKJmxf43pQ7OD64t151ol06FMjUBLHgJ1ep9d32Q0F3f3oUxfDQs21Bi9RA==
          next
      end
      config vpn IPsec phase2-interface                                        # Phase 2 configuration
          edit "IP-TEST"
              set phase1name "IPsec "
              set proposal aes128-sha1
              set dhgrp 5
              set keylifeseconds 3600
              set src-subnet 10.10.0.0 255.255.0.0
              set dst-subnet 172.16.0.0 255.255.255.0
          next
      end

#. Configure access policies.

   .. code-block::

      config firewall policy
       edit 15                                                  # Policy 15 is used to access the on-premises data center from the cloud. NAT is disabled.
              set uuid 4f452870-ddb2-51e5-35c9-38a987ebdb6c
              set srcintf "IPsec"
              set dstintf "trust"
              set srcaddr "hw-172.16.0.0/24"
              set dstaddr "local-10.10.0.0/16"
              set action accept
              set schedule "always"
              set service "ALL"
              set logtraffic all
          next
          edit 29                                           # Policy 29 is used to access the cloud from the on-premises data center. NAT is disabled.
              set uuid c2d0ec77-5254-51e9-80dc-2813ccf51463
              set srcintf "trust"
              set dstintf "IPsec"
              set srcaddr "local-10.10.0.0/16"
              set dstaddr "hw-172.16.0.0/24"
              set action accept
              set schedule "always"
              set service "ALL"
              set logtraffic all
          next

#. Configure routes.

   .. code-block::

      config router static
          edit 24                                 # Route 24 is a static route that is used to access on the cloud.
              set dst 172.16.0.0 255.255.255.0
              set gateway 11.11.11.1
              set distance 10
              set device "port1"
      config router policy
      edit 2                         # Policy-based route 2 is used to access the cloud from the on-premises data center.
              set input-device "A1"
              set src "10.10.00/255.255.0.0"
              set dst "172.16.0.0/255.255.255.0"
              set gateway 11.11.11.1
              set output-device "port1"
