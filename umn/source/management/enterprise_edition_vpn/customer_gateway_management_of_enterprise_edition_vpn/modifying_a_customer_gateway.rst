:original_name: vpn_ug_00010.html

.. _vpn_ug_00010:

Modifying a Customer Gateway
============================

Scenario
--------

After creating a customer gateway, you can modify its name.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - Customer Gateways**.

#. On the **Customer Gateways** page, click |image3| next to the name of a customer gateway.

#. Enter a new name for the customer gateway and click **OK**.

   :ref:`Table 1 <en-us_topic_0000001592773721__table135441110101713>` describes the parameters related to customer gateway modification.

   .. _en-us_topic_0000001592773721__table135441110101713:

   .. table:: **Table 1** Parameters related to customer gateway modification

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                           | Modifiable or Not     |
      +=======================+=======================================================================================================================================+=======================+
      | Name                  | Name of a VPN connection. The value can contain only letters, digits, underscores (_), hyphens (-), and periods (.).                  | Y                     |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | BGP ASN               | The BGP ASN needs to be specified only when **Routing Mode** is set to **Dynamic (BGP)**.                                             | N                     |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway IP Address    | IP address used by the customer gateway to communicate with the VPN gateway. The value must be a static address.                      | N                     |
      |                       |                                                                                                                                       |                       |
      |                       | Ensure that UDP port 4500 is permitted in a firewall rule on the customer gateway in your on-premises data center or private network. |                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000001923096425.png
.. |image3| image:: /_static/images/en-us_image_0000001542494178.png
