:original_name: en-us_topic_0060118606.html

.. _en-us_topic_0060118606:

Creating a VPN
==============

**Overview**
------------

By default, ECSs in a VPC cannot communicate with your data center or private network. To enable communication between them, use a VPN. You need to create a VPN in your VPC and update the security group rules.

Description of a Simple IPsec VPN Intranet Topology
---------------------------------------------------

In :ref:`Figure 1 <en-us_topic_0060118606__fig19884520114220>`, a VPC has two subnets: 192.168.1.0/24 and 192.168.2.0/24. On your router deployed in your physical data center, you also have two subnets: 192.168.3.0/24 and 192.168.4.0/24. You can create a VPN to enable subnets in your VPC to communicate with those in your data center.

.. _en-us_topic_0060118606__fig19884520114220:

.. figure:: /_static/images/en-us_image_0159197475.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Currently, the site-to-site VPN and hub-spoke VPN are supported. You need to set up VPNs in both your data center and the VPC to establish the VPN connection.

Ensure that the VPN in your VPC and that in your data center use the same Internet Key Exchange (IKE) and IPsec policy configurations. Before creating a VPN, familiarize yourself with the protocols described in :ref:`Table 1 <en-us_topic_0060118606__en-us_topic_0013748707_table1573616693718>` and ensure that your device meets the requirements and configuration constraints of the involved protocols.

.. _en-us_topic_0060118606__en-us_topic_0013748707_table1573616693718:

.. table:: **Table 1** Involved protocols

   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | Parameter             | Description                                                                                                        | Constraint                                                      |
   +=======================+====================================================================================================================+=================================================================+
   | RFC 2409              | Defines the IKE protocol, which negotiates and verifies key information to safeguard VPNs.                         | -  Use the pre-shared key (PSK) to reach an IKE peer agreement. |
   |                       |                                                                                                                    | -  Use the main mode and aggressive mode for negotiation.       |
   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | RFC 4301              | Defines the IPsec architecture, the security services that IPsec offers, and the collaboration between components. | Use the IPsec tunnel to set up a VPN connection.                |
   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+

**Scenarios**
-------------

Perform the following procedure to create a VPN that sets up a secure, isolated communication tunnel between your data center and cloud services.

**Procedure**
-------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Network**.

#. On the **Virtual Private Network** page, click **Create VPN**.

#. .. _en-us_topic_0060118606__en-us_topic_0013748707_li3027778720388:

   Set the parameters as prompted and click **Create Now**.

   .. _en-us_topic_0060118606__fig12119136431:

   .. figure:: /_static/images/en-us_image_0155784843.png
      :alt: **Figure 2** Creating a VPN

      **Figure 2** Creating a VPN

   .. _en-us_topic_0060118606__en-us_topic_0013748707_table968099720388:

   .. table:: **Table 2** Basic parameters

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                                   | Example Value         |
      +=======================+===============================================================================================================================================================================================================================================================================================================+=======================+
      | Region                | Specifies the desired region. Regions are geographic areas isolated from each other. Resources are region-specific and cannot be used across regions through internal network connections. For low network latency and quick resource access, select the nearest region.                                      | eu-de                 |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                  | Specifies the VPN name.                                                                                                                                                                                                                                                                                       | VPN-001               |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPC                   | Specifies the VPC name.                                                                                                                                                                                                                                                                                       | VPC-001               |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Subnet          | A local subnet is a VPC subnet that accesses a customer network through a VPN.                                                                                                                                                                                                                                | 192.168.1.0/24,       |
      |                       |                                                                                                                                                                                                                                                                                                               |                       |
      |                       | -  **Select subnet**: If you select this option, you can then select the subnets that need to communicate with your data center.                                                                                                                                                                              | 192.168.2.0/24        |
      |                       | -  **Specify CIDR block**: If you select this option, you can then enter the CIDR blocks that need to communicate with your data center.                                                                                                                                                                      |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Gateway        | Specifies the public IP address of the VPN in your data center or on the private network. This IP address is used for communicating with the VPN in the VPC.                                                                                                                                                  | N/A                   |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Subnet         | A remote subnet is a subnet in the customer data center that accesses a VPC through a VPN. The remote and local subnets cannot have overlapping or matching CIDR blocks. The remote subnet CIDR block cannot overlap with CIDR blocks involved in existing VPC peering connections created for the local VPC. | 192.168.3.0/24,       |
      |                       |                                                                                                                                                                                                                                                                                                               |                       |
      |                       |                                                                                                                                                                                                                                                                                                               | 192.168.4.0/24        |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PSK                   | Specifies the pre-shared key, which is a private key shared by two ends of a VPN connection. The PSK configurations for both ends of a VPN connection must be the same. This key is used for VPN connection negotiation.                                                                                      | Test@123              |
      |                       |                                                                                                                                                                                                                                                                                                               |                       |
      |                       | The value is a string of 6 to 128 characters.                                                                                                                                                                                                                                                                 |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Confirm PSK           | Specifies the confirm pre-shared key.                                                                                                                                                                                                                                                                         | Test@123              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                   | Specifies the VPN tag, which consists of a key and value pair. You can add a maximum of ten tags to each VPN.                                                                                                                                                                                                 | -  Key: vpn_key1      |
      |                       |                                                                                                                                                                                                                                                                                                               | -  Value: vpn-01      |
      |                       | The tag key and value must meet the requirements listed in :ref:`Table 3 <en-us_topic_0060118606__en-us_topic_0013748707_en-us_topic_0013935842_table248245914136>`.                                                                                                                                          |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings     | -  **Default**: uses default IKE and IPsec policies.                                                                                                                                                                                                                                                          | Custom                |
      |                       | -  **Existing**: uses existing IKE and IPsec policies. This option is available only after you have created IKE and IPsec policies.                                                                                                                                                                           |                       |
      |                       | -  **Custom**: uses custom IKE and IPsec policies. For details about the policies, see :ref:`Table 4 <en-us_topic_0060118606__en-us_topic_0013748707_table505541520388>` and :ref:`Table 5 <en-us_topic_0060118606__en-us_topic_0013748707_table4625367220388>`.                                              |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0060118606__en-us_topic_0013748707_en-us_topic_0013935842_table248245914136:

   .. table:: **Table 3** VPN tag key and value requirements

      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirement                                                                | Example Value         |
      +=======================+============================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                                   | vpn_key1              |
      |                       | -  Must be unique for the same VPN and can be the same for different VPNs. |                       |
      |                       | -  Contains a maximum of 36 characters.                                    |                       |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                                 | vpn-01                |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0060118606__en-us_topic_0013748707_table505541520388:

   .. table:: **Table 4** IKE policy

      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                                                         | Example Value         |
      +==========================+=====================================================================================================================================================================================================+=======================+
      | Authentication Algorithm | Specifies the authentication hash algorithm. The value can be **SHA1**, **SHA2-256**, **SHA2-384**, **SHA2-512**, or **MD5**.                                                                       | SHA1                  |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **SHA1**.                                                                                                                                                                      |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | Specifies the encryption algorithm. The value can be **AES-128**, **AES-192**, **AES-256**, or **3DES**. The 3DES algorithm is not recommended because it is risky.                                 | AES-128               |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **AES-128**.                                                                                                                                                                   |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | DH Algorithm             | Specifies the Diffie-Hellman key exchange algorithm. The value can be **Group 1**, **Group 2**, **Group 5**, **Group 14**, **Group 15**, **Group 16**, **Group 19**, **Group 20**, or **Group 21**. | Group 5               |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The DH group security level from the highest to lowest is as follows: Group 21 > Group 20 > Group 19 > Group 16 > Group 15 > Group 14 > Group 5 > Group 2 > Group 1.                                |                       |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **Group 5**.                                                                                                                                                                   |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Version                  | Specifies the version of the IKE protocol. The value can be **v1** or **v2**.                                                                                                                       | v1                    |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **v1**.                                                                                                                                                                        |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifecycle (s)            | Specifies the lifetime of the security association (SA), in seconds.                                                                                                                                | 86400                 |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The SA will be renegotiated if its lifetime expires.                                                                                                                                                |                       |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **86400**.                                                                                                                                                                     |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Negotiation Mode         | If the IKE policy version is **v1**, the negotiation mode can be configured. The value can only be **Main**.                                                                                        | Main                  |
      |                          |                                                                                                                                                                                                     |                       |
      |                          | The default value is **Main**.                                                                                                                                                                      |                       |
      +--------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0060118606__en-us_topic_0013748707_table4625367220388:

   .. table:: **Table 5** IPsec policy

      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                                                              | Example Value         |
      +==========================+==========================================================================================================================================================================================================+=======================+
      | Authentication Algorithm | Specifies the authentication hash algorithm. The value can be **SHA1**, **SHA2-256**, **SHA2-384**, **SHA2-512**, or **MD5**.                                                                            | SHA1                  |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The default value is **SHA1**.                                                                                                                                                                           |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | Specifies the encryption algorithm. The value can be **AES-128**, **AES-192**, **AES-256**, or **3DES**. The 3DES algorithm is not recommended because it is risky.                                      | AES-128               |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The default value is **AES-128**.                                                                                                                                                                        |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PFS                      | Specifies the perfect forward secrecy (PFS), which is used to configure the IPsec tunnel negotiation.                                                                                                    | DH group 5            |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | This function enables two parties to exchange the DH keys during the phase-two negotiation, improving key security. It is recommended that you enable this function.                                     |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | You can disable this function by selecting **Disable** from the drop-down list.                                                                                                                          |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The PFS used at the two sides of a VPN must be the same. Otherwise, the negotiation will fail. If you disable this function on the console, you also need to disable it at the customer side of the VPN. |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The value can be **DH group 1**, **DH group 2**, **DH group 5**, **DH group 14**, **DH group 15**, **DH group 16**, **DH group 19**, **DH group 20**, or **DH group 21**.                                |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The PFS group security level from the highest to lowest is as follows: DH group 21 > DH group 20 > DH group 19 > DH group 16 > DH group 15 > DH group 14 > DH group 5 > DH group 2 > DH group 1.         |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The default value is **DH group 5**.                                                                                                                                                                     |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Transfer Protocol        | Specifies the security protocol used for IPsec to transmit and encapsulate user data. The value can be **AH**, **ESP**, or **AH-ESP**.                                                                   | ESP                   |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The default value is **ESP**.                                                                                                                                                                            |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifecycle (s)            | Specifies the lifetime of the SA, in seconds.                                                                                                                                                            | 3600                  |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The SA will be renegotiated if its lifetime expires.                                                                                                                                                     |                       |
      |                          |                                                                                                                                                                                                          |                       |
      |                          | The default value is **3600**.                                                                                                                                                                           |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. note::

      The IKE policy specifies the encryption and authentication algorithms to use in the negotiation phase of an IPsec tunnel. The IPsec policy specifies the protocol, encryption algorithm, and authentication algorithm to use in the data transmission phase of an IPsec tunnel. These parameters must be the same between the VPN in your VPC and that in your data center. If they are different, the VPN cannot be set up.

#. Click **Submit**.

   After the IPsec VPN is created, a public network egress IP address is assigned to the IPsec VPN. The IP address is the local gateway address of a created VPN on the network console. When configuring the remote tunnel in your data center, you must set the remote gateway address to this IP address.

   .. _en-us_topic_0060118606__en-us_topic_0013748707_fig4815144716272:

   .. figure:: /_static/images/en-us_image_0152926732.png
      :alt: **Figure 3** Gateway egress IP address

      **Figure 3** Gateway egress IP address

#. Due to the symmetry of the tunnel, you also need to configure the IPsec VPN on your router or firewall in the data center.

   -  For the protocols supported by VPN connections, see section :ref:`Reference Standards and Protocols <en-us_topic_0081947484>`.
   -  For a list of supported VPN devices, see :ref:`Which Remote VPN Devices Are Supported? <en-us_topic_0109676043>`.

.. |image1| image:: /_static/images/en-us_image_0123091916.png
