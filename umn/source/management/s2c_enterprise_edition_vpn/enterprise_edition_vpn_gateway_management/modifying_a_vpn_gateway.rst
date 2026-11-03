:original_name: vpn_ug_00003.html

.. _vpn_ug_00003:

Modifying a VPN Gateway
=======================

Scenario
--------

You can modify basic information about a VPN gateway, including the name and local subnet.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.

#. On the **S2C VPN Gateways** page, click **Modify Basic Information** in the **Operation** column of the target VPN gateway.

   To modify only the name of a VPN gateway, you can also click |image3| on the right of the VPN gateway name.

#. Modify the name and local subnet of the VPN gateway as prompted.

#. Click **OK**.


.. figure:: /_static/images/en-us_image_0000001842114970.png
   :alt: **Figure 1** Modifying a VPN gateway

   **Figure 1** Modifying a VPN gateway

:ref:`Table 1 <en-us_topic_0000001542014738__table135441110101713>` describes the parameters for modifying the VPN gateway.

.. _en-us_topic_0000001542014738__table135441110101713:

.. table:: **Table 1** Parameters for modifying the VPN gateway

   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Parameter              | Description                                                                                                                                                                                   | Modifiable or Not                                                                      |
   +========================+===============================================================================================================================================================================================+========================================================================================+
   | Name                   | Name of a VPN gateway. The value can contain only letters, digits, underscores (_), hyphens (-), and periods (.).                                                                             | Y                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Local Subnet           | VPC subnets with which your on-premises data center needs to communicate through the customer gateway.                                                                                        | Y                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Region                 | For low network latency and fast resource access, select the region nearest to your target users.                                                                                             | N                                                                                      |
   |                        |                                                                                                                                                                                               |                                                                                        |
   |                        | Resources cannot be shared across regions.                                                                                                                                                    |                                                                                        |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Specification          | Three options are available: **Basic**, **Professional 1** and **Professional 2**.                                                                                                            | The supported specifications are subject to those displayed on the management console. |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Associate With         | Select **VPC**.                                                                                                                                                                               | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Enterprise Router      | The associated enterprise router needs to be specified only when **Associate With** is set to **Enterprise Router**.                                                                          | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | VPC                    | VPC that the on-premises data center needs to access.                                                                                                                                         | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | Interconnection Subnet | This subnet is used for communication between the VPN gateway and VPC. Ensure that the selected interconnection subnet has four or more assignable IP addresses.                              | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | BGP ASN                | BGP AS number.                                                                                                                                                                                | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+
   | AZ                     | An AZ is a geographic location with independent power supply and network facilities in a region. AZs in the same VPC are interconnected through private networks and are physically isolated. | N                                                                                      |
   +------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
.. |image3| image:: /_static/images/en-us_image_0000001542334214.png
