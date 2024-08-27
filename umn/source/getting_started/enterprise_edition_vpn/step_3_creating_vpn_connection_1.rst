:original_name: vpn_qs_00008.html

.. _vpn_qs_00008:

.. _en-us_topic_0000001963846432:

Step 3: Creating VPN Connection 1
=================================

Procedure
---------

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.

#. On the **VPN Connections** page, click **Create VPN Connection**.

#. Set parameters for VPN connection 1 as prompted and click **Submit**.

   The following describes only key parameters.

   .. table:: **Table 1** Parameter settings for VPN connection 1

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                         | Description                                                                                                                                                                                                                | Example Value         |
      +===================================+============================================================================================================================================================================================================================+=======================+
      | Name                              | Enter the name of VPN connection 1.                                                                                                                                                                                        | vpn-001               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPN Gateway                       | Select the VPN gateway created in :ref:`Step 1: Creating a VPN Gateway <en-us_topic_0000001963686660>`.                                                                                                                    | vpngw-001             |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway IP Address                | Select the active EIP of the VPN gateway.                                                                                                                                                                                  | 11.xx.xx.11           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Customer Gateway                  | Select the customer gateway created in :ref:`Step 2: Creating a Customer Gateway <en-us_topic_0000002000246717>`.                                                                                                          | cgw-001               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPN Type                          | Select **Static routing**.                                                                                                                                                                                                 | Static routing        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Customer Subnet                   | Enter the subnet of the on-premises data center that needs to access the VPC.                                                                                                                                              | 172.16.0.0/16         |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   | .. note::                                                                                                                                                                                                                  |                       |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   |    -  The customer subnet can overlap with the local subnet but cannot be the same as the local subnet.                                                                                                                    |                       |
      |                                   |    -  A customer subnet cannot be included in the existing subnets of the VPC associated with the VPN gateway. It also cannot be the destination address in the route table of the VPC associated with the VPN gateway.    |                       |
      |                                   |    -  Customer subnets cannot be the reserved CIDR blocks of VPCs, for example, 100.64.0.0/10 or 214.0.0.0/8.                                                                                                              |                       |
      |                                   |    -  If the interconnection subnet is associated with an ACL rule, ensure that the ACL rule permits the TCP port for traffic between all local and customer subnets.                                                      |                       |
      |                                   |    -  Address groups cannot be used to configure the source and destination subnets in a policy on customer gateway devices.                                                                                               |                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Interface IP Address Assignment   | The options include **Manually specify** and **Automatically assign**.                                                                                                                                                     | Manually specify      |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Tunnel Interface Address    | Specify the tunnel interface address configured on the VPN gateway.                                                                                                                                                        | 169.254.70.2/30       |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   | .. note::                                                                                                                                                                                                                  |                       |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   |    The local and remote interface addresses configured on the customer gateway device must be the same as the values of **Customer Tunnel Interface IP Address** and **Local Tunnel Interface IP Address**, respectively.  |                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Customer Tunnel Interface Address | Specify the tunnel interface address configured on the customer gateway device.                                                                                                                                            | 169.254.70.1/30       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Link Detection                    | This function is used for route reliability detection in multi-link scenarios.                                                                                                                                             | **NQA** enabled       |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   | .. note::                                                                                                                                                                                                                  |                       |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   |    When enabling this function, ensure that the customer gateway supports ICMP and is correctly configured with the customer interface IP address of the VPN connection. Otherwise, VPN traffic will fail to be forwarded. |                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PSK, Confirm PSK                  | Specify the negotiation key of the VPN connection.                                                                                                                                                                         | Test@123              |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   | The PSKs configured on the VPN console and the customer gateway device must be the same.                                                                                                                                   |                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Policy Settings                   | Configure the IKE and IPsec policies, which define the encryption algorithms used by the VPN tunnel.                                                                                                                       | Default               |
      |                                   |                                                                                                                                                                                                                            |                       |
      |                                   | The policy settings on the VPN console and the customer gateway device must be the same.                                                                                                                                   |                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

Verification
------------

Check the created VPN connection on the **VPN Connections** page. The initial state of the VPN connection is **Creating**. As the customer gateway device has not been configured, no VPN connection can be established. After about 2 minutes, the VPN connection state changes to **Not connected**.
