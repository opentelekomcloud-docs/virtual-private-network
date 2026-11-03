:original_name: vpn_03_0336.html

.. _vpn_03_0336:

Step 4: Configuring the Customer Gateway Device
===============================================

Procedure
---------

.. note::

   In this example, the customer gateway device is an AR router.

#. Log in to the AR router.

#. Enter the system view.

   .. code-block::

      <AR651>system-view

#. Configure an IP address for the WAN interface. In this example, the WAN interface of the AR router is GigabitEthernet 0/0/8.

   .. code-block::

      [AR651]interface GigabitEthernet 0/0/8
      [AR651-GigabitEthernet0/0/8]ip address 22.xx.xx.22 255.255.255.0
      [AR651-GigabitEthernet0/0/8]quit

#. Configure a default route.

   .. code-block::

      [AR651]ip route-static 0.0.0.0 0.0.0.0 22.xx.xx.1

   In this command, *22.xx.xx.1* is the gateway address of the AR router's public IP address. Replace it with the actual gateway address.

#. Enable the SHA-2 algorithm to be compatible with the standard RFC algorithms.

   .. code-block::

      [AR651]IPsec authentication sha2 compatible enable

#. Configure an IPsec proposal.

   .. code-block::

      [AR651]IPsec proposal hwproposal1
      [AR651-IPsec-proposal-hwproposal1]esp authentication-algorithm sha2-256
      [AR651-IPsec-proposal-hwproposal1]esp encryption-algorithm aes-128
      [AR651-IPsec-proposal-hwproposal1]quit

#. Configure an IKE proposal.

   .. code-block::

      [AR651]ike proposal 2
      [AR651-ike-proposal-2]encryption-algorithm aes-128
      [AR651-ike-proposal-2]dh group14
      [AR651-ike-proposal-2]authentication-algorithm sha2-256
      [AR651-ike-proposal-2]authentication-method pre-share
      [AR651-ike-proposal-2]integrity-algorithm hmac-sha2-256
      [AR651-ike-proposal-2]prf hmac-sha2-256
      [AR651-ike-proposal-2]quit

#. Configure IKE peers.

   .. code-block::

      [AR651]ike peer hwpeer1
      [AR651-ike-peer-hwpeer1]undo version 1
      [AR651-ike-peer-hwpeer1]pre-shared-key cipher Test@123
      [AR651-ike-peer-hwpeer1]ike-proposal 2
      [AR651-ike-peer-hwpeer1]local-address 22.xx.xx.22
      [AR651-ike-peer-hwpeer1]remote-address 11.xx.xx.11
      [AR651-ike-peer-hwpeer1]rsa encryption-padding oaep
      [AR651-ike-peer-hwpeer1]rsa signature-padding pss
      [AR651-ike-peer-hwpeer1]ikev2 authentication sign-hash sha2-256
      [AR651-ike-peer-hwpeer1]quit
      [AR651]ike peer hwpeer2
      [AR651-ike-peer-hwpeer2]undo version 1
      [AR651-ike-peer-hwpeer2]pre-shared-key cipher Test@123
      [AR651-ike-peer-hwpeer2]ike-proposal 2
      [AR651-ike-peer-hwpeer2]local-address 22.xx.xx.22
      [AR651-ike-peer-hwpeer2]remote-address 11.xx.xx.12
      [AR651-ike-peer-hwpeer2]rsa encryption-padding oaep
      [AR651-ike-peer-hwpeer2]rsa signature-padding pss
      [AR651-ike-peer-hwpeer2]ikev2 authentication sign-hash sha2-256
      [AR651-ike-peer-hwpeer2]quit

   The commands are described as follows:

   -  **pre-shared-key cipher**: configures a PSK, which must be the same as that configured on the VPN console.
   -  **local-address**: specifies the public IP address of the AR router.
   -  **remote-address**: specifies the active EIP or active EIP 2 of the VPN gateway.

#. Configure an IPsec profile.

   .. code-block::

      [AR651]IPsec profile hwpro1
      [AR651-IPsec-profile-hwpro1]ike-peer hwpeer1
      [AR651-IPsec-profile-hwpro1]proposal hwproposal1
      [AR651-IPsec-profile-hwpro1]pfs dh-group14
      [AR651-IPsec-profile-hwpro1]quit
      [AR651]IPsec profile hwpro2
      [AR651-IPsec-profile-hwpro2]ike-peer hwpeer2
      [AR651-IPsec-profile-hwpro2]proposal hwproposal1
      [AR651-IPsec-profile-hwpro2]pfs dh-group14
      [AR651-IPsec-profile-hwpro2]quit

#. Configure virtual tunnel interfaces.

   .. code-block::

      [AR651]interface Tunnel0/0/1
      [AR651-Tunnel0/0/1]mtu 1400
      [AR651-Tunnel0/0/1]ip address 169.254.70.1 255.255.255.252
      [AR651-Tunnel0/0/1]tunnel-protocol IPsec
      [AR651-Tunnel0/0/1]source 22.xx.xx.22
      [AR651-Tunnel0/0/1]destination 11.xx.xx.11
      [AR651-Tunnel0/0/1]IPsec profile hwpro1
      [AR651-Tunnel0/0/1]quit
      [AR651]interface Tunnel0/0/2
      [AR651-Tunnel0/0/2]mtu 1400
      [AR651-Tunnel0/0/2]ip address 169.254.71.1 255.255.255.252
      [AR651-Tunnel0/0/2]tunnel-protocol IPsec
      [AR651-Tunnel0/0/2]source 22.xx.xx.22
      [AR651-Tunnel0/0/2]destination 11.xx.xx.12
      [AR651-Tunnel0/0/2]IPsec profile hwpro2
      [AR651-Tunnel0/0/2]quit

   The commands are described as follows:

   -  **interface Tunnel0/0/1** and **interface Tunnel0/0/2**: indicate the tunnel interfaces corresponding to the two VPN connections.

      In this example, Tunnel0/0/1 establishes a VPN connection with the active EIP of the VPN gateway, and Tunnel0/0/2 establishes a VPN connection with active EIP 2 of the VPN gateway.

   -  **ip address**: configures an IP address for a tunnel interface on the AR router.

   -  **source**: specifies the public IP address of the AR router.

   -  **destination**: specifies the active EIP or active EIP 2 of the VPN gateway.

#. Configure NQA.

   .. code-block::

      [AR651]nqa test-instance IPsec_nqa1 IPsec_nqa1
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]test-type icmp
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]destination-address ipv4 169.254.70.2
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]source-address ipv4 169.254.70.1
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]frequency 15
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]ttl 255
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]start now
      [AR651-nqa-IPsec_nqa1-IPsec_nqa1]quit
      [AR651]nqa test-instance IPsec_nqa2 IPsec_nqa2
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]test-type icmp
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]destination-address ipv4 169.254.71.2
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]source-address ipv4 169.254.71.1
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]frequency 15
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]ttl 255
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]start now
      [AR651-nqa-IPsec_nqa2-IPsec_nqa2]quit

   The commands are described as follows:

   -  **nqa test-instance IPsec_nqa1 IPsec_nqa1** and **nqa test-instance IPsec_nqa2 IPsec_nqa2**: configure two NQA test instances named **IPsec_nqa1** and **IPsec_nqa2**.

      In this example, the test instance **IPsec_nqa1** is created for the VPN connection to which the active EIP of the VPN gateway belongs; the test instance **IPsec_nqa2** is created for the VPN connection to which active EIP 2 of the VPN gateway belongs.

   -  **destination-address**: specifies the tunnel interface address of the VPN connection.

   -  **source-address**: specifies the tunnel interface address of the AR router.

#. Configure association between the static route and NQA.

   .. code-block::

      [AR651]ip route-static 192.168.0.0 255.255.255.0 Tunnel0/0/1 track nqa IPsec_nqa1 IPsec_nqa1
      [AR651]ip route-static 192.168.0.0 255.255.255.0 Tunnel0/0/2 track nqa IPsec_nqa2 IPsec_nqa2

   The parameters are described as follows:

   -  **192.168.0.0** indicates the local subnet of the VPC.
   -  **Tunnel**\ *x* and **IPsec_nqa**\ *x* in the same command correspond to the same VPN connection.

Verification
------------

#. Log in to the management console.

#. Click |image1| in the upper left corner, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.

   Verify that the states of the two VPN connections are both **Normal**.

.. |image1| image:: /_static/images/en-us_image_0000002394353329.png
