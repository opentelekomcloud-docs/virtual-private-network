:original_name: vpn_ug_00013.html

.. _vpn_ug_00013:

Viewing a VPN Connection
========================

Scenario
--------

After creating a VPN connection, you can view its details.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.
#. On the **VPN Connection** page, view the VPN connection list.
#. Click the name of a VPN connection to view its basic information, policy configuration, and tags.

   -  When **VPN Type** is **Static routing**, the basic information includes the VPN connection information and health check information.
   -  When **VPN Type** is **BGP routing**, the basic information includes the VPN connection information and health check information.
   -  When **VPN Type** is **Policy-based**, the basic information includes the VPN connection information, policy rule information, and health check information.


.. figure:: /_static/images/en-us_image_0000001888252021.png
   :alt: **Figure 1** Viewing a VPN connection

   **Figure 1** Viewing a VPN connection

|image3|

.. note::

   -  In the VPN connection list, locate the target VPN connection, and choose **More** > **Modify Policy Settings** on the right to view IKE and IPsec policies of the VPN connection.

   -  In the VPN connection list, you can locate the target VPN connection and click **View Metric** to view monitoring information about the VPN connection.

      Check the value of **VPN Connection Status**. If the value is **0**, the VPN connection is not connected. If the value is **1**, the VPN connection is connected. If the value is **2**, the VPN connection status is unknown.

   -  In the VPN connection list, dual connections to the same customer gateway are identified by |image4|. If such dual connections are displayed on different pages, |image5| and |image6| are also displayed on different pages.

      The dual-connection identifier will be unavailable if you sort VPN connections by any field in the VPN connection list. The identifier will be restored after you cancel field-based sorting.

   -  In the VPN connection list, you can click **View Logs** corresponding to the target VPN connection to view its IPsec negotiation logs.

      If a VPN connection is in **Not connected** state, you can determine the cause of the disconnection based on the VPN connection log details.

   -  On the **VPN Connection** page, the **Export** and setting buttons are available above the gateway list.

      -  You can click **Export** in the upper left corner and select the data to be exported from the drop-down list.
      -  You can click |image7| in the upper right corner and set the columns to be displayed as required.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
.. |image3| image:: /_static/images/en-us_image_0000001841932888.png
.. |image4| image:: /_static/images/en-us_image_0000002212546056.png
.. |image5| image:: /_static/images/en-us_image_0000002247558165.png
.. |image6| image:: /_static/images/en-us_image_0000002277248177.png
.. |image7| image:: /_static/images/en-us_image_0000002392771213.png
