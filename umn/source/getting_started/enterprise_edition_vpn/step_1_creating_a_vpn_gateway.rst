:original_name: vpn_03_0204.html

.. _vpn_03_0204:

.. _en-us_topic_0000001963686660:

Step 1: Creating a VPN Gateway
==============================

Prerequisites
-------------

-  A VPC has been created. For details about how to create a VPC, see the *Virtual Private Cloud User Guide*.
-  Security group rules have been configured for ECSs in the VPC, and allow the customer gateway in the on-premises data center to access VPC resources. For details about how to configure security group rules, see `Security Group Rules <https://docs.otc.t-systems.com/virtual-private-cloud/umn/access_control/security_group/managing_security_group_rules/adding_a_security_group_rule.html>`__.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.
#. Set parameters as prompted, click , and complete the payment.
#. The following describes only key parameters.

   .. table:: **Table 1** Key VPN gateway parameters

      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Parameter                | Description                                                                                                                                                      | Example Value            |
      +==========================+==================================================================================================================================================================+==========================+
      | Region                   | Select the region nearest to you.                                                                                                                                | eu-de                    |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Name                     | Name a VPN gateway.                                                                                                                                              | vpngw-001                |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Network Type             | Select **Public network**.                                                                                                                                       | Public network           |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Associate With           | Select **VPC**.                                                                                                                                                  | VPC                      |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | VPC                      | Select the VPC that needs to access the on-premises data center.                                                                                                 | vpc-001(192.168.0.0/16)  |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Interconnection Subnet   | This subnet is used for communication between the VPN gateway and VPC. Ensure that the selected interconnection subnet has four or more assignable IP addresses. | 192.168.2.0/24           |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Local Subnet             | Specify the VPC subnet that needs to access the on-premises data center.                                                                                         | 192.168.0.0/24           |
      |                          |                                                                                                                                                                  |                          |
      |                          | You can manually enter a CIDR block or select a subnet from the drop-down list box.                                                                              |                          |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | BGP ASN                  | BGP AS number.                                                                                                                                                   | 64512                    |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Specification            | Select **Professional 1** and deselect **Access via a non-fixed IP address**.                                                                                    | Professional 1           |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | AZ                       | **AZ1** and **AZ2** are supported.                                                                                                                               | AZ1, AZ2                 |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Gateway IP Address       | This parameter is available only when **Network Type** is set to **Private network**.                                                                            | Self-assigned IP address |
      |                          |                                                                                                                                                                  |                          |
      |                          | -  Self-assigned IP address (default)                                                                                                                            |                          |
      |                          |                                                                                                                                                                  |                          |
      |                          |    An IP address on the access subnet will be automatically assigned to the VPN gateway.                                                                         |                          |
      |                          |                                                                                                                                                                  |                          |
      |                          |    You can view the automatically assigned IP address on the **VPN Gateways** page.                                                                              |                          |
      |                          |                                                                                                                                                                  |                          |
      |                          | -  Manually-specified IP address                                                                                                                                 |                          |
      |                          |                                                                                                                                                                  |                          |
      |                          |    Manually configure IP addresses on the access subnet for the VPN gateway.                                                                                     |                          |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Advanced Settings > Tags | Configure **Tags** in **Advanced Settings**.                                                                                                                     | ``-``                    |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | HA Mode                  | Select **Active-active**.                                                                                                                                        | Active-active            |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Active EIP               | You can buy a new EIP or use an existing EIP.                                                                                                                    | 11.xx.xx.11              |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+
      | Active EIP 2             | You can buy a new EIP or use an existing EIP.                                                                                                                    | 11.xx.xx.12              |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------+

Verification
------------

Check the created VPN gateway on the **VPN Gateways** page. The initial state of the VPN gateway is **Creating**. When the VPN gateway state changes to **Normal**, the VPN gateway is successfully created.

.. |image1| image:: /_static/images/en-us_image_0000001923096425.png
