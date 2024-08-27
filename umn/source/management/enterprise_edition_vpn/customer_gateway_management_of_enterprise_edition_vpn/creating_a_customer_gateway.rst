:original_name: vpn_04_0431.html

.. _vpn_04_0431:

Creating a Customer Gateway
===========================

Scenario
--------

To connect your on-premises data center or private network to your ECSs in a VPC, you need to create a customer gateway before creating a VPN connection.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - Customer Gateways**.

#. On the **Customer Gateways** page, click **Create Customer Gateway**.

#. Set parameters as prompted and click **Create Now**.


   .. figure:: /_static/images/en-us_image_0000001867256192.png
      :alt: **Figure 1** Creating a customer gateway

      **Figure 1** Creating a customer gateway

   :ref:`Table 1 <en-us_topic_0000001542014850__table61829653>` lists the customer gateway parameters.

   .. _en-us_topic_0000001542014850__table61829653:

   .. table:: **Table 1** Description of customer gateway parameters

      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                                                                                                                | Example Value         |
      +==========================+============================================================================================================================================================================================================================================================+=======================+
      | Name                     | Name of a customer gateway. The value can contain only letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                                                                     | cgw-001               |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Routing Mode             | Routing mode of the customer gateway.                                                                                                                                                                                                                      | Static                |
      |                          |                                                                                                                                                                                                                                                            |                       |
      |                          | -  Select **Dynamic (BGP)** when **VPN Type** is set to **Route-based** and **Routing Mode** is set to **Dynamic (BGP)** for the VPN connection.                                                                                                           |                       |
      |                          |                                                                                                                                                                                                                                                            |                       |
      |                          |    -  When selecting this option, ensure that the customer gateway supports dynamic BGP.                                                                                                                                                                   |                       |
      |                          |    -  The customer gateway can advertise a maximum of 100 BGP routes to the VPN gateway. If more than 100 BGP routes are advertised, the BGP peer relationship is disconnected, causing traffic interruption between the VPN gateway and customer gateway. |                       |
      |                          |                                                                                                                                                                                                                                                            |                       |
      |                          | -  Select **Static** when **VPN Type** is set to **Route-based** and **Routing Mode** is set to **Static** for the VPN connection.                                                                                                                         |                       |
      |                          | -  You are advised to select **Static** when **VPN Type** is set to **Policy-based** for the VPN connection.                                                                                                                                               |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP ASN                  | Enter the ASN of your on-premises data center or private network.                                                                                                                                                                                          | 65000                 |
      |                          |                                                                                                                                                                                                                                                            |                       |
      |                          | The BGP ASN of the customer gateway must be different from that of the VPN gateway.                                                                                                                                                                        |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway IP Address       | IP address used by the customer gateway to communicate with the VPN gateway. The value must be a static address.                                                                                                                                           | 1.2.3.4               |
      |                          |                                                                                                                                                                                                                                                            |                       |
      |                          | Ensure that UDP port 4500 is permitted in a firewall rule on the customer gateway in your on-premises data center or private network.                                                                                                                      |                       |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings > Tags | Configure **Tags** in **Advanced Settings**.                                                                                                                                                                                                               | ``-``                 |
      +--------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. (Optional) If there are two customer gateways, repeat the preceding operations to configure the other customer gateway with a different identifier.

Related Operations
------------------

You need to configure an IPsec VPN tunnel on the router or firewall in your on-premises data center.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000001923096425.png
