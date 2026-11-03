:original_name: vpn_faq_00040.html

.. _vpn_faq_00040:

What Are VPN Negotiation Parameters? What Are Their Default Values?
===================================================================

.. table:: **Table 1** VPN negotiation parameters

   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Protocol              | Parameter                | Value                                                                                                                         |
   +=======================+==========================+===============================================================================================================================+
   | IKE                   | Version                  | -  v1 (v1 has low security. If the device supports v2, v2 is recommended.)                                                    |
   |                       |                          | -  v2 (default value)                                                                                                         |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Negotiation Mode         | -  Main (default value)                                                                                                       |
   |                       |                          | -  Aggressive                                                                                                                 |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Authentication Algorithm | -  MD5 (This algorithm is insecure. Exercise caution when using this algorithm.)                                              |
   |                       |                          | -  SHA1 (This algorithm is insecure. Exercise caution when using this algorithm.)                                             |
   |                       |                          | -  SHA2-256 (default value)                                                                                                   |
   |                       |                          | -  SHA2-384                                                                                                                   |
   |                       |                          | -  SHA2-512                                                                                                                   |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Encryption Algorithm     | -  3DES (This algorithm is insecure. Exercise caution when using this algorithm.)                                             |
   |                       |                          | -  AES-128 (default value)                                                                                                    |
   |                       |                          | -  AES-192 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  AES-256 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  AES-256-GCM-16                                                                                                             |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | DH Algorithm             | -  Group 1 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  Group 2 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  Group 5 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  Group 14 (default value)                                                                                                   |
   |                       |                          | -  Group 15                                                                                                                   |
   |                       |                          | -  Group 16                                                                                                                   |
   |                       |                          | -  Group 19                                                                                                                   |
   |                       |                          | -  Group 20                                                                                                                   |
   |                       |                          | -  Group 21                                                                                                                   |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Lifetime (s)             | **86400** (default value)                                                                                                     |
   |                       |                          |                                                                                                                               |
   |                       |                          | Unit: second                                                                                                                  |
   |                       |                          |                                                                                                                               |
   |                       |                          | Value range: **60** to **604800**                                                                                             |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Local ID                 | -  IP Address                                                                                                                 |
   |                       |                          |                                                                                                                               |
   |                       |                          |    The local IP address is automatically displayed as the EIP of the VPN gateway, removing the need to manually configure it. |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  FQDN                                                                                                                       |
   |                       |                          |                                                                                                                               |
   |                       |                          | By default, the local ID type is IP address and the local ID value is the EIP of the VPN gateway.                             |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Customer ID              | -  IP Address                                                                                                                 |
   |                       |                          | -  FQDN                                                                                                                       |
   |                       |                          |                                                                                                                               |
   |                       |                          | By default, the customer ID type is IP address and the customer ID value is the public IP address of the customer gateway.    |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | IPsec                 | Authentication Algorithm | -  SHA1 (This algorithm is insecure. Exercise caution when using this algorithm.)                                             |
   |                       |                          | -  MD5 (This algorithm is insecure. Exercise caution when using this algorithm.)                                              |
   |                       |                          | -  SHA2-256 (default value)                                                                                                   |
   |                       |                          | -  SHA2-384                                                                                                                   |
   |                       |                          | -  SHA2-512                                                                                                                   |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Encryption Algorithm     | -  AES-128 (default value)                                                                                                    |
   |                       |                          | -  AES-192 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  AES-256 (This algorithm is insecure. Exercise caution when using this algorithm.)                                          |
   |                       |                          | -  3DES (This algorithm is insecure. Exercise caution when using this algorithm.)                                             |
   |                       |                          | -  AES-128-GCM-16                                                                                                             |
   |                       |                          | -  AES-256-GCM-16                                                                                                             |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | PFS                      | -  DH group 1 (This algorithm is insecure. Exercise caution when using this algorithm.)                                       |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 2 (This algorithm is insecure. Exercise caution when using this algorithm.)                                       |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 5 (This algorithm is insecure. Exercise caution when using this algorithm.)                                       |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 14 (default value)                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 15                                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 16                                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 19                                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 20                                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  DH group 21                                                                                                                |
   |                       |                          |                                                                                                                               |
   |                       |                          | -  Disable (not recommended due to security risks)                                                                            |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Transfer Protocol        | -  ESP (default value)                                                                                                        |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   |                       | Lifetime (s)             | **3600** (default value)                                                                                                      |
   |                       |                          |                                                                                                                               |
   |                       |                          | Unit: second                                                                                                                  |
   |                       |                          |                                                                                                                               |
   |                       |                          | Value range: **30** to **604800**                                                                                             |
   +-----------------------+--------------------------+-------------------------------------------------------------------------------------------------------------------------------+

.. note::

   -  Perfect Forward Secrecy (PFS) is a security feature.

      IKE negotiation has two phases, phase one and phase two. The key of phase two (IPsec SA) is derived from the key generated in phase one. Once the key in phase one is disclosed, the security of the IPsec VPN may be adversely affected. To improve the key security, IKE provides PFS. When PFS is enabled, an additional DH exchange will be performed during IPsec SA negotiation to generate a new IPsec SA key, improving IPsec SA security.

   -  For security purposes, PFS is enabled on the cloud side by default. Ensure that PFS is also enabled on the gateway device in your on-premises data center and the PFS settings on both ends are the same. Otherwise, the negotiation will fail.

   -  The default traffic-based lifetime of an IPsec SA is 1,843,200 KB on the cloud side and cannot be changed for the VPN. This parameter is not involved in negotiation and has no impact on the establishment of an IPsec SA.
