:original_name: vpn_01_0021.html

.. _vpn_01_0021:

Data Protection Technologies
============================

-  S2C VPN is a tunneling technology that provides IP-layer security using the IKE/IPsec protocol suite. It ensures confidentiality and integrity of IP data packets and prevents them from being intercepted, disclosed, or tampered with on insecure networks (such as the Internet).

-  When creating an S2C VPN connection, you can configure data encryption and authentication algorithms in a policy.

   :ref:`Table 1 <en-us_topic_0000001592879081__table108927017443>` lists the algorithms recommended for S2C VPN in descending order of security.

   .. _en-us_topic_0000001592879081__table108927017443:

   .. table:: **Table 1** Parameters for configuring an S2C VPN policy

      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      | Parameter             |                          | Description                                                                         |
      +=======================+==========================+=====================================================================================+
      | IKE Policy            | Version                  | -  v2                                                                               |
      |                       |                          | -  v1 (IKEv1 has low security. If the device supports IKEv2, IKEv2 is recommended.) |
      |                       |                          |                                                                                     |
      |                       |                          | The default value is **v2**.                                                        |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      |                       | Authentication Algorithm | Hash algorithm used for authentication. The following algorithms are supported:     |
      |                       |                          |                                                                                     |
      |                       |                          | -  SHA2-512                                                                         |
      |                       |                          | -  SHA2-384                                                                         |
      |                       |                          | -  SHA2-256                                                                         |
      |                       |                          | -  MD5(Insecure. Not recommended.)                                                  |
      |                       |                          | -  SHA1(Insecure. Not recommended.)                                                 |
      |                       |                          |                                                                                     |
      |                       |                          | By default, the SHA2-256 algorithm is used.                                         |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      |                       | Encryption Algorithm     | The following encryption algorithms are supported:                                  |
      |                       |                          |                                                                                     |
      |                       |                          | -  AES-256-GCM-16 (supported only by Enterprise Edition VPN)                        |
      |                       |                          | -  AES-128-GCM-16 (supported only by Enterprise Edition VPN)                        |
      |                       |                          | -  AES-256(Insecure. Not recommended.)                                              |
      |                       |                          | -  AES-192(Insecure. Not recommended.)                                              |
      |                       |                          | -  AES-128(Insecure. Not recommended.)                                              |
      |                       |                          | -  3DES(Insecure. Not recommended.)                                                 |
      |                       |                          |                                                                                     |
      |                       |                          | The default value is **AES-128**.                                                   |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      |                       | DH Algorithm             | The following algorithms are supported:                                             |
      |                       |                          |                                                                                     |
      |                       |                          | -  Group 21                                                                         |
      |                       |                          | -  Group 20                                                                         |
      |                       |                          | -  Group 19                                                                         |
      |                       |                          | -  Group 16                                                                         |
      |                       |                          | -  Group 15                                                                         |
      |                       |                          | -  Group 14(Insecure. Not recommended.)                                             |
      |                       |                          | -  Group 5(Insecure. Not recommended.)                                              |
      |                       |                          | -  Group 2(Insecure. Not recommended.)                                              |
      |                       |                          | -  Group 1(Insecure. Not recommended.)                                              |
      |                       |                          |                                                                                     |
      |                       |                          | By default, Group 15 is used.                                                       |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      | IPsec Policy          | Authentication Algorithm | Hash algorithm used for authentication. The following algorithms are supported:     |
      |                       |                          |                                                                                     |
      |                       |                          | -  SHA2-512                                                                         |
      |                       |                          | -  SHA2-384                                                                         |
      |                       |                          | -  SHA2-256                                                                         |
      |                       |                          | -  MD5(Insecure. Not recommended.)                                                  |
      |                       |                          | -  SHA1(Insecure. Not recommended.)                                                 |
      |                       |                          |                                                                                     |
      |                       |                          | By default, the SHA2-256 algorithm is used.                                         |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+
      |                       | Encryption Algorithm     | The following encryption algorithms are supported:                                  |
      |                       |                          |                                                                                     |
      |                       |                          | -  AES-256-GCM-16                                                                   |
      |                       |                          | -  AES-128-GCM-16                                                                   |
      |                       |                          | -  AES-256(Insecure. Not recommended.)                                              |
      |                       |                          | -  AES-192(Insecure. Not recommended.)                                              |
      |                       |                          | -  AES-128(Insecure. Not recommended.)                                              |
      |                       |                          | -  3DES(Insecure. Not recommended.)                                                 |
      |                       |                          |                                                                                     |
      |                       |                          | The default value is **AES-128**.                                                   |
      +-----------------------+--------------------------+-------------------------------------------------------------------------------------+

PFS
---

Perfect Forward Secrecy (PFS) ensures that the compromise of the keys of an IPsec tunnel does not affect the security of other tunnels by leveraging that the keys of these tunnels are irrelevant to each other. By default, the PFS function is enabled for S2C VPN.

Each IPsec VPN connection consists of at least one IPsec tunnel, each of which uses an independent set of keys to protect user traffic.

S2C VPN supports the following algorithms:

-  DH group 1 (This algorithm is insecure. Exercise caution when using it.)
-  DH group 2 (This algorithm is insecure. Exercise caution when using it.)
-  DH group 5 (This algorithm is insecure. Exercise caution when using it.)
-  DH group 14
-  DH group 15
-  DH group 16
-  DH group 19
-  DH group 20
-  DH group 21

Anti-replay
-----------

Anti-replay uses sequence numbers to protect IPsec encrypted packets against replay attacks, which are initiated by repeatedly sending intercepted data packets. By default, the anti-replay function is enabled for the VPN service.

Resource Isolation
------------------

A VPN gateway is exclusive to a tenant. As such, tenants are isolated from each, ensuring tenant data security.
