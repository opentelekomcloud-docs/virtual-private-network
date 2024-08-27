:original_name: vpn_qs_00003.html

.. _vpn_qs_00003:

Overview
========

The supported regions are subject to those available on the console.

Scenario
--------

To meet business development requirements, enterprise A needs to implement communication between its on-premises data center and its VPC. In this case, enterprise A can use the VPN service to create connections between the on-premises data center and the VPC.

-  If the on-premises data center has only one customer gateway and this gateway can be configured with only one IP address, it is recommended that the VPN gateway uses the active-active mode. :ref:`Figure 1 <en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig576114434011>` shows the networking.

   In active-active mode, if connection 1 fails, traffic is automatically switched to connection 2, without affecting enterprise services. After connection 1 recovers, VPN still uses connection 2 for data transmission.

   .. _en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig576114434011:

   .. figure:: /_static/images/en-us_image_0000001651244201.png
      :alt: **Figure 1** Active-active mode

      **Figure 1** Active-active mode

-  If the on-premises data center has two customer gateways or has only one customer gateway that can be configured with two IP addresses, it is recommended that the VPN gateway use the active/standby mode. :ref:`Figure 2 <en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig4294134917216>` shows the networking.

   In active/standby mode, connection 1 is the active link and connection 2 is the standby link. By default, traffic is transmitted only through the active link. If the active link fails, traffic is automatically switched to the standby link, without affecting enterprise services. After the active link recovers, traffic is switched back to the active link.

   .. _en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig4294134917216:

   .. figure:: /_static/images/en-us_image_0000001609202724.png
      :alt: **Figure 2** Active/Standby mode

      **Figure 2** Active/Standby mode

Limitations and Constraints
---------------------------

-  The customer gateway device must support standard IKE and IPsec protocols.

-  The interconnection subnets of the on-premises data center neither overlap with those of the VPC nor contain 100.64.0.0/10 or 214.0.0.0/8.

   If the VPC uses Direct Cloud or Cloud Connect connections to communicate with other VPCs, the on-premises data center subnets cannot overlap with those of these VPCs.

Data Plan
---------

.. table:: **Table 1** Data plan

   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Category                | Item                                                    | Data                                                                                                                                                                                                          |
   +=========================+=========================================================+===============================================================================================================================================================================================================+
   | VPC                     | Subnet that needs to access the on-premises data center | 192.168.0.0/16                                                                                                                                                                                                |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN gateway             | Interconnection subnet                                  | This subnet is used for communication between the VPN gateway and VPC. Ensure that the selected interconnection subnet has four or more assignable IP addresses.                                              |
   |                         |                                                         |                                                                                                                                                                                                               |
   |                         |                                                         | 192.168.2.0/24                                                                                                                                                                                                |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN gateway             | HA mode                                                 | Active-active                                                                                                                                                                                                 |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN gateway             | EIP                                                     | EIPs are automatically generated when you buy them. By default, a VPN gateway uses two EIPs. In this example, the EIPs are as follows:                                                                        |
   |                         |                                                         |                                                                                                                                                                                                               |
   |                         |                                                         | -  Active EIP: 11.xx.xx.11                                                                                                                                                                                    |
   |                         |                                                         | -  Active EIP 2: 11.xx.xx.12                                                                                                                                                                                  |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN connection          | Tunnel interface address                                | This address is used by a VPN gateway to establish an IPsec tunnel with a customer gateway. At the two ends of the IPsec tunnel, the configured local and remote tunnel interface addresses must be reversed. |
   |                         |                                                         |                                                                                                                                                                                                               |
   |                         |                                                         | -  VPN connection 1: 169.254.70.1/30                                                                                                                                                                          |
   |                         |                                                         | -  VPN connection 2: 169.254.71.1/30                                                                                                                                                                          |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | On-premises data center | Subnet that needs to access the VPC                     | 172.16.0.0/16                                                                                                                                                                                                 |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Customer gateway        | Gateway IP address                                      | The gateway IP address is assigned by a carrier. In this example, the gateway IP address is:                                                                                                                  |
   |                         |                                                         |                                                                                                                                                                                                               |
   |                         |                                                         | 22.xx.xx.22                                                                                                                                                                                                   |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Customer gateway        | Tunnel interface address                                | -  VPN connection 1: 169.254.70.2/30                                                                                                                                                                          |
   |                         |                                                         | -  VPN connection 2: 169.254.71.2/30                                                                                                                                                                          |
   +-------------------------+---------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Operation Process
-----------------

:ref:`Figure 3 <en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig10285152624918>` shows the process of using the VPN service to enable communication between an on-premises data center and a VPC.

.. _en-us_topic_0000002000327309__en-us_topic_0000001542494050_fig10285152624918:

.. figure:: /_static/images/en-us_image_0000001592879305.png
   :alt: **Figure 3** Operation process

   **Figure 3** Operation process

.. table:: **Table 2** Operation process description

   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | No.                   | Step                                                                                  | Description                                                                                                                                                                                             |
   +=======================+=======================================================================================+=========================================================================================================================================================================================================+
   | 1                     | :ref:`Step 1: Creating a VPN Gateway <en-us_topic_0000001963686660>`                  | Bind two EIPs to the VPN gateway.                                                                                                                                                                       |
   |                       |                                                                                       |                                                                                                                                                                                                         |
   |                       |                                                                                       | If you have purchased EIPs, you can directly bind them to the VPN gateway.                                                                                                                              |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 2                     | :ref:`Step 2: Creating a Customer Gateway <en-us_topic_0000002000246717>`             | Configure the VPN device in the on-premises data center as the customer gateway.                                                                                                                        |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 3                     | :ref:`Step 3: Creating VPN Connection 1 <en-us_topic_0000001963846432>`               | Create a VPN connection between the active EIP of the VPN gateway and the customer gateway.                                                                                                             |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 4                     | :ref:`Step 4: Creating VPN Connection 2 <en-us_topic_0000002000327313>`               | Create a VPN connection between active EIP 2 of the VPN gateway and the customer gateway.                                                                                                               |
   |                       |                                                                                       |                                                                                                                                                                                                         |
   |                       |                                                                                       | It is recommended that the routing mode, PSK, IKE policy, and IPsec policy settings of the two VPN connections be the same.                                                                             |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 5                     | :ref:`Step 5: Configuring the Customer Gateway Device <en-us_topic_0000001963686664>` | -  The local and remote tunnel interface addresses configured on the customer gateway device must be the same as the customer and local tunnel interface addresses of the VPN connection, respectively. |
   |                       |                                                                                       | -  The routing mode, PSK, IKE policy, and IPsec policy settings on the customer gateway device must be same as those of the VPN connection.                                                             |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | 6                     | :ref:`Step 6: Verifying Network Connectivity <en-us_topic_0000002000246725>`          | Log in to an ECS and run the **ping** command to verify the network connectivity.                                                                                                                       |
   +-----------------------+---------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
