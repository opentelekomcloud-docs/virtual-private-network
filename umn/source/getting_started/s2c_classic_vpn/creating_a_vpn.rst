:original_name: vpn_03_0004.html

.. _vpn_03_0004:

Creating a VPN
==============

Overview
--------

By default, ECSs in a VPC cannot communicate with devices in your on-premises data center or private network. To enable communication between them, you can use a VPN by creating it in your VPC and updating security group rules.

IPsec VPN Topology
------------------

In :ref:`Figure 1 <en-us_topic_0000001592573661__fig19884520114220>`, the VPC has subnets 192.168.1.0/24 and 192.168.2.0/24. Your on-premises data center has subnets 192.168.3.0/24 and 192.168.4.0/24. You can use VPN to enable subnets in the VPC to communicate with those in your data center.

.. _en-us_topic_0000001592573661__fig19884520114220:

.. figure:: /_static/images/en-us_image_0000001592573989.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Site-to-site VPN is supported to enable communication between VPC subnets and on-premises data center subnets. Before establishing an IPsec VPN, ensure that the on-premises data center where the VPN is to be established meets the following conditions:

-  On-premises devices that support the standard IPsec protocol are available.
-  The on-premises devices have fixed public IP addresses, which can be statically configured or translated by NAT.
-  The on-premises subnets do not conflict with VPC subnets, and devices in the on-premises subnets can communicate with the on-premises devices.

If the preceding conditions are met, ensure that the IKE policies and IPsec policies at both ends are consistent and the subnets at both ends are matched pairs when configuring IPsec VPN.

After the configuration is complete, VPN negotiation needs to be triggered by private network data flows.

Scenarios
---------

You need a VPN that sets up a secure, isolated communications tunnel between your on-premises data center and cloud services.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network**.

   If Enterprise Edition VPN is available for the selected region, choose **Virtual Private Network** > **Classic**.

#. .. _en-us_topic_0000001592573661__li11662386400:

   On the **Virtual Private Network** page, click **Create VPN**.

   If Enterprise Edition VPN is available for the selected region, click **Create VPN** on the **Classic** page.

#. Configure required parameters and click **Create Now**.

   :ref:`Table 1 <en-us_topic_0000001592573661__table786224517597>`, :ref:`Table 2 <en-us_topic_0000001592573661__table135874264220>`, and :ref:`Table 3 <en-us_topic_0000001592573661__table14353932124215>` describe the parameters.

   .. _en-us_topic_0000001592573661__table786224517597:

   .. table:: **Table 1** Basic parameters

      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                                                                                                                                                       | Example Value         |
      +==========================+===================================================================================================================================================================================================================================================================================================+=======================+
      | Region                   | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across regions. For low network latency and fast resource access, select the region nearest to your target users. | eu-de                 |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                     | The VPN name                                                                                                                                                                                                                                                                                      | VPN-001               |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPC                      | The VPC name                                                                                                                                                                                                                                                                                      | VPC-001               |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Subnet             | VPC subnets that will access your on-premises network through a VPN.                                                                                                                                                                                                                              | 192.168.1.0/24,       |
      |                          |                                                                                                                                                                                                                                                                                                   |                       |
      |                          |                                                                                                                                                                                                                                                                                                   | 192.168.2.0/24        |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Gateway           | The public IP address of the gateway in your data center or on the private network. This IP address is used for communicating with your VPC.                                                                                                                                                      | N/A                   |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Subnet            | The subnets of your on-premises network that will access a VPC through a VPN. The remote and local subnets cannot overlap with each other. The remote subnets cannot overlap with CIDR blocks involved in existing VPC peering connections created for the VPC.                                   | 192.168.3.0/24,       |
      |                          |                                                                                                                                                                                                                                                                                                   |                       |
      |                          |                                                                                                                                                                                                                                                                                                   | 192.168.4.0/24        |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PSK                      | Private key shared by two ends of a VPN connection for negotiation. PSKs configured at both ends of the VPN connection must be the same.                                                                                                                                                          | Test@123              |
      |                          |                                                                                                                                                                                                                                                                                                   |                       |
      |                          | The PSK can contain 6 to 128 characters.                                                                                                                                                                                                                                                          |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Confirm PSK              | Enter the PSK again.                                                                                                                                                                                                                                                                              | Test@123              |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings        | -  **Default**: Use default IKE and IPsec policies.                                                                                                                                                                                                                                               | Custom                |
      |                          | -  **Existing**: Use existing IKE and IPsec policies.                                                                                                                                                                                                                                             |                       |
      |                          | -  **Custom**: Use custom IKE and IPsec policies. For details, see :ref:`Table 2 <en-us_topic_0000001592573661__table135874264220>` and :ref:`Table 3 <en-us_topic_0000001592573661__table14353932124215>`.                                                                                       |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings > Tags | Configure **Tags** in **Advanced Settings**.                                                                                                                                                                                                                                                      | ``-``                 |
      +--------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0000001592573661__table135874264220:

   .. table:: **Table 2** IKE policy

      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                          | Example Value         |
      +==========================+======================================================================================================+=======================+
      | Authentication Algorithm | Hash algorithm used for authentication. The following algorithms are supported:                      | SHA2-256              |
      |                          |                                                                                                      |                       |
      |                          | -  MD5(Insecure. Not recommended.)                                                                   |                       |
      |                          | -  SHA1(Insecure. Not recommended.)                                                                  |                       |
      |                          | -  SHA2-256                                                                                          |                       |
      |                          | -  SHA2-384                                                                                          |                       |
      |                          | -  SHA2-512                                                                                          |                       |
      |                          |                                                                                                      |                       |
      |                          | The default value is **SHA2-256**.                                                                   |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | Encryption algorithm. The following algorithms are supported:                                        | AES-128               |
      |                          |                                                                                                      |                       |
      |                          | -  AES-128                                                                                           |                       |
      |                          | -  AES-192                                                                                           |                       |
      |                          | -  AES-256                                                                                           |                       |
      |                          | -  3DES(Insecure. Not recommended.)                                                                  |                       |
      |                          |                                                                                                      |                       |
      |                          | The default value is **AES-128**.                                                                    |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | DH Algorithm             | Diffie-Hellman key exchange algorithm. The following algorithms are supported:                       | Group 14              |
      |                          |                                                                                                      |                       |
      |                          | -  DH group 1(Insecure. Not recommended.)                                                            |                       |
      |                          | -  DH group 2(Insecure. Not recommended.)                                                            |                       |
      |                          | -  DH group 5(Insecure. Not recommended.)                                                            |                       |
      |                          | -  DH group 14                                                                                       |                       |
      |                          | -  Group 15                                                                                          |                       |
      |                          |                                                                                                      |                       |
      |                          | -  Group 16                                                                                          |                       |
      |                          | -  Group 19                                                                                          |                       |
      |                          | -  Group 20                                                                                          |                       |
      |                          | -  Group 21                                                                                          |                       |
      |                          |                                                                                                      |                       |
      |                          | The default value is **Group 14**.                                                                   |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | Version                  | Version of the IKE protocol. The value can be one of the following:                                  | v2                    |
      |                          |                                                                                                      |                       |
      |                          | -  v1 (For security reasons, IKEv1 is not recommended. If your devices support IKEv2, select IKEv2.) |                       |
      |                          | -  v2                                                                                                |                       |
      |                          |                                                                                                      |                       |
      |                          | The default value is **v2**.                                                                         |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifetime (s)             | Lifetime of an SA, in seconds                                                                        | 86400                 |
      |                          |                                                                                                      |                       |
      |                          | An SA will be renegotiated when its lifetime expires.                                                |                       |
      |                          |                                                                                                      |                       |
      |                          | The default value is **86400**.                                                                      |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+
      | Negotiation Mode         | The value is **Main**. This parameter is available only when **Version** is set to **v1**.           | Main                  |
      |                          |                                                                                                      |                       |
      |                          | The default value is **Main**.                                                                       |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0000001592573661__table14353932124215:

   .. table:: **Table 3** IPsec policy

      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                   | Example Value         |
      +==========================+===============================================================================================================+=======================+
      | Authentication Algorithm | Hash algorithm used for authentication. The following algorithms are supported:                               | SHA2-256              |
      |                          |                                                                                                               |                       |
      |                          | -  SHA1(Insecure. Not recommended.)                                                                           |                       |
      |                          | -  MD5(Insecure. Not recommended.)                                                                            |                       |
      |                          | -  SHA2-256                                                                                                   |                       |
      |                          | -  SHA2-384                                                                                                   |                       |
      |                          | -  SHA2-512                                                                                                   |                       |
      |                          |                                                                                                               |                       |
      |                          | The default value is **SHA2-256**.                                                                            |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | Encryption algorithm. The following algorithms are supported:                                                 | AES-128               |
      |                          |                                                                                                               |                       |
      |                          | -  AES-128                                                                                                    |                       |
      |                          | -  AES-192                                                                                                    |                       |
      |                          | -  AES-256                                                                                                    |                       |
      |                          | -  3DES(Insecure. Not recommended.)                                                                           |                       |
      |                          |                                                                                                               |                       |
      |                          | The default value is **AES-128**.                                                                             |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+
      | PFS                      | Algorithm used by the Perfect forward secrecy (PFS) function.                                                 | DH group 14           |
      |                          |                                                                                                               |                       |
      |                          | PFS supports the following algorithms:                                                                        |                       |
      |                          |                                                                                                               |                       |
      |                          | -  Disable                                                                                                    |                       |
      |                          | -  DH group 1(Insecure. Not recommended.)                                                                     |                       |
      |                          | -  DH group 2(Insecure. Not recommended.)                                                                     |                       |
      |                          | -  DH group 5(Insecure. Not recommended.)                                                                     |                       |
      |                          | -  DH group 14                                                                                                |                       |
      |                          | -  DH group 15                                                                                                |                       |
      |                          | -  DH group 16                                                                                                |                       |
      |                          | -  DH group 19                                                                                                |                       |
      |                          | -  DH group 20                                                                                                |                       |
      |                          | -  DH group 21                                                                                                |                       |
      |                          |                                                                                                               |                       |
      |                          | The default value is **DH group 14**.                                                                         |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+
      | Transfer Protocol        | Security protocol used in IPsec to transmit and encapsulate user data. The following protocols are supported: | ESP                   |
      |                          |                                                                                                               |                       |
      |                          | -  AH                                                                                                         |                       |
      |                          | -  AH-ESP                                                                                                     |                       |
      |                          | -  ESP                                                                                                        |                       |
      |                          |                                                                                                               |                       |
      |                          | The default value is **ESP**.                                                                                 |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifetime (s)             | Lifetime of an SA, in seconds                                                                                 | 3600                  |
      |                          |                                                                                                               |                       |
      |                          | An SA will be renegotiated when its lifetime expires.                                                         |                       |
      |                          |                                                                                                               |                       |
      |                          | The default value is **3600**.                                                                                |                       |
      +--------------------------+---------------------------------------------------------------------------------------------------------------+-----------------------+

   .. note::

      An IKE policy specifies the encryption and authentication algorithms to be used in the negotiation phase of an IPsec tunnel. An IPsec policy specifies the protocol, encryption algorithm, and authentication algorithm to be used in the data transmission phase of an IPsec tunnel. The IKE and IPsec policies must be the same at both ends of a VPN connection. Otherwise, the VPN connection cannot be set up.

#. Submit your application.

   After the IPsec VPN is created, a public IP address is assigned to the VPN. The IP address is the local gateway address of the created VPN. When configuring the remote tunnel in your data center, you must set the remote gateway address to this IP address.


   .. figure:: /_static/images/en-us_image_0000001542334190.png
      :alt: **Figure 2** Gateway IP address

      **Figure 2** Gateway IP address

#. You need to configure an IPsec VPN tunnel on the router or firewall in your on-premises data center.

   -  For a list of protocols supported by VPN connections, see :ref:`Reference Standards and Protocols <vpn_01_0006>`.

   -  Most devices that meet IPsec VPN standards and protocol requirements can be used as VPN devices. For example, a Fortinet FortiGate firewall can be used as a VPN device. For details, see :ref:`Configuring VPN When Fortinet FortiGate Firewall Is Used <vpn_admin_0016>`.

      Other devices that meet the requirements outlined in the reference protocols described in section :ref:`Reference Standards and Protocols <vpn_01_0006>` can also be deployed. However, some devices may not be supported because of the inconsistent protocol implementation methods of these devices. If connections cannot be set up, rectify the fault by referring to :ref:`What Do I Do If a VPN Connection Fails to Be Established? <vpn_faq_00144>` or contact technical support.

.. |image1| image:: /_static/images/en-us_image_0000001592773969.png
.. |image2| image:: /_static/images/en-us_image_0000002376415194.png
