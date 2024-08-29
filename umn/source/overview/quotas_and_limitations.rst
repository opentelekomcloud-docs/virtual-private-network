:original_name: vpn_01_0005.html

.. _vpn_01_0005:

Quotas and Limitations
======================

VPN Gateway
-----------

.. table:: **Table 1** Constraints on Enterprise Edition VPN gateways

   +------------------------+--------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | VPN Type               | Resource                                                                                         | Default Quota                                                                                 |
   +========================+==================================================================================================+===============================================================================================+
   | Enterprise Edition VPN | VPN gateways per tenant in each region                                                           | 50                                                                                            |
   |                        |                                                                                                  |                                                                                               |
   |                        |                                                                                                  | -  If you have only one VPC, you can create a maximum of 50 VPN gateways for the VPC.         |
   |                        |                                                                                                  | -  If you have multiple VPCs, you can create a maximum of 50 VPN gateways for all these VPCs. |
   +------------------------+--------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | Enterprise Edition VPN | VPN connection groups per VPN gateway                                                            | 100                                                                                           |
   +------------------------+--------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | Enterprise Edition VPN | Local subnets per VPN gateway                                                                    | 50                                                                                            |
   +------------------------+--------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+
   | Enterprise Edition VPN | Number of BGP routes that a VPN gateway can receive from a customer gateway through a connection | 100                                                                                           |
   +------------------------+--------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------+

.. table:: **Table 2** Constraints on Classic VPN

   +-----------------------+--------------------------------+----------------------------------------+
   | VPN Type              | Resource                       | Default Quota                          |
   +=======================+================================+========================================+
   | Classic VPN           | VPNs per tenant in each region | 2                                      |
   |                       |                                |                                        |
   |                       |                                | Only one VPN can be created for a VPC. |
   +-----------------------+--------------------------------+----------------------------------------+

-  By default, the maximum length of TCP packets supported by a VPN gateway is 1300 bytes.

Customer Gateway
----------------

.. table:: **Table 3** Constraints on customer gateways

   +------------------------+---------------------------------------------+---------------+
   | VPN Type               | Resource                                    | Default Quota |
   +========================+=============================================+===============+
   | Enterprise Edition VPN | Customer gateways per tenant in each region | 100           |
   +------------------------+---------------------------------------------+---------------+

-  Enable NAT traversal on the customer gateway based on the networking.

   -  If the customer gateway is connected to the Internet through a NAT device, enable NAT traversal on the customer gateway.
   -  If the customer gateway is directly connected to the Internet, you do not need to enabled NAT traversal on the customer gateway.

-  Dead Peer Detection (DPD) must be enabled on a customer gateway.
-  A customer gateway must support IPsec tunnel interfaces and be configured with a corresponding security policy.
-  When Network Quality Analysis (NQA) is enabled for a connection in static routing mode, the IPsec tunnel interface of a customer gateway must have an IP address and be able to respond to ICMP requests.
-  It is recommended that the maximum segment size (MSS) of TCP packets be set to a value less than 1399 on a customer gateway, so as to prevent fragmentation caused by addition of an IPsec header.

VPN Connection
--------------

.. table:: **Table 4** Constraints on Enterprise Edition VPN connections

   +------------------------+-------------------------------------+---------------+---------------------------------+
   | VPN Type               | Resource                            | Default Quota | How to Increase Quota           |
   +========================+=====================================+===============+=================================+
   | Enterprise Edition VPN | Policy rules per VPN connection     | 5             | The quotas cannot be increased. |
   +------------------------+-------------------------------------+---------------+---------------------------------+
   | Enterprise Edition VPN | Customer subnets per VPN connection | 50            | This quota cannot be increased. |
   +------------------------+-------------------------------------+---------------+---------------------------------+

.. table:: **Table 5** Constraints on Classic VPN connections

   +-------------+-------------------------------------------+---------------+---------------------------------+
   | VPN Type    | Resource                                  | Default Quota | How to Increase Quota           |
   +=============+===========================================+===============+=================================+
   | Classic VPN | VPN connections per tenant in each region | 12            | This quota cannot be increased. |
   +-------------+-------------------------------------------+---------------+---------------------------------+

-  In multi-subnet scenarios, you are advised to use VPN connections in routing mode. For a VPN connection in policy-based or policy template mode, a VPN gateway creates a communications tunnel for each pair of the local and customer subnets by default. If there are multiple local or customer subnets for a VPN connection in policy-based or policy template mode, multiple communications tunnels are created.

   Each IP address of a VPN gateway supports a maximum of 100 communications tunnels for connecting to customer gateways.

   -  In routing mode, each VPN connection occupies only one communications tunnel of the corresponding VPN gateway IP address.
   -  In policy-based or policy template mode, each VPN connection occupies *M* x *N* communications tunnels of the corresponding VPN gateway IP address. *M* indicates the number of local subnets, and *N* indicates the number of customer subnets.

   If the number of communications tunnels occupied by all VPN connections in different modes established by a single gateway IP address has reached 100, excess VPN connections will fail to be created.

-  When creating a VPN connection in policy-based mode and adding multiple policy rules, ensure that the source and destination CIDR blocks in different policy rules do not overlap. Otherwise, data flows may be incorrectly matched or IPsec tunnels may flap.
