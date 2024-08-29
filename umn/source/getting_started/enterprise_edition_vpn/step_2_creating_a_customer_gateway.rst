:original_name: vpn_qs_00007.html

.. _vpn_qs_00007:

.. _en-us_topic_0000002000246717:

Step 2: Creating a Customer Gateway
===================================

Procedure
---------

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - Customer Gateways**.

#. On the **Customer Gateways** page, click **Create Customer Gateway**.

#. Set parameters as prompted and click **OK**.

   The following describes only key parameters.

   .. table:: **Table 1** Customer gateway parameters

      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+
      | Parameter                | Description                                                                               | Example Value           |
      +==========================+===========================================================================================+=========================+
      | Name                     | Name a customer gateway.                                                                  | cgw-001                 |
      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+
      | Routing Mode             | Set the routing mode of the customer gateway.                                             | Static                  |
      |                          |                                                                                           |                         |
      |                          | The options include **Dynamic (BGP)** and **Static**.                                     |                         |
      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+
      | Gateway IP Address       | Enter the IP address of the customer gateway.                                             | IP Address, 22.xx.xx.22 |
      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+
      | BGP ASN                  | The BGP ASN needs to be specified only when **Routing Mode** is set to **Dynamic (BGP)**. | 65000                   |
      |                          |                                                                                           |                         |
      |                          | Enter the ASN of your on-premises data center or private network.                         |                         |
      |                          |                                                                                           |                         |
      |                          | The BGP ASN of the customer gateway must be different from that of the VPN gateway.       |                         |
      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+
      | Advanced Settings > Tags | Configure **Tags** in **Advanced Settings**.                                              | ``-``                   |
      +--------------------------+-------------------------------------------------------------------------------------------+-------------------------+

Verification
------------

Check the created customer gateway on the **Customer Gateways** page.
