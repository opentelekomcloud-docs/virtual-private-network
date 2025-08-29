:original_name: vpn_04_0704.html

.. _vpn_04_0704:

Viewing Metrics
===============

Scenarios
---------

View the VPN connection status and usages of bandwidth and EIP. You can view data of the last 15 minutes, last 30 minutes, last 1 hour, last 2 hours, last 3 hours, last 12 hours, last 24 hours, last 7 days, last 30 days, or a custom time range.

Viewing VPN Gateway Metrics
---------------------------

-  Viewing metrics on the VPN console

   #. Log in to the management console.

   #. Click |image1| in the upper left corner and select the desired region and project.

   #. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

   #. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.

   #. Locate the target VPN connection, and click |image3| in the **Gateway IP Address** column.

      You can view data of the last 15 minutes, last 30 minutes, last 1 hour, last 2 hours, last 3 hours, last 12 hours, last 24 hours, last 7 days, last 30 days, or a custom time range.

-  Viewing metrics on the Cloud Eye console

   #. Log in to the management console.

   #. Click |image4| in the upper left corner and select the desired region and project.

   #. In the upper left corner of the page, click |image5| and choose **Management & Deployment** > **Cloud Eye**.

   #. Choose **Cloud Service Monitoring** > **Virtual Private Network**.

   #. On the **S2C VPN Gateway** tab page, click **View Metric** in the **Operation** column of the target VPN gateway to view its status.

      You can view data of the last 15 minutes, last 30 minutes, last 1 hour, last 2 hours, last 3 hours, last 12 hours, last 24 hours, last 7 days, last 30 days, or a custom time range.

Viewing VPN Connection Metrics
------------------------------

-  Viewing metrics on the VPN console

   #. Log in to the management console.
   #. Click |image6| in the upper left corner and select the desired region and project.
   #. Click |image7| in the upper left corner, and choose **Network** > **Virtual Private Network**.
   #. View metrics.

      -  S2C Enterprise Edition VPN: Choose **Virtual Private Network** > **Enterprise - VPN Connections**, and click |image8| in the **Monitoring** column of a VPN connection.

         You can view data of the last 15 minutes, last 30 minutes, last 1 hour, last 2 hours, last 3 hours, last 12 hours, last 24 hours, last 7 days, last 30 days, or a custom time range.

         The metrics include the following:

         -  VPN Connection Status

         -  Average Link RTT, Maximum Link RTT, Link Packet Loss Rate

            These metrics are displayed only after the health check function is enabled. To enable this function, click the name of a VPN connection and add health check items on the **Summary** tab page.

         -  Average Tunnel RTT, Maximum Tunnel RTT, Tunnel Packet Loss Rate

            These metrics are displayed only when **VPN Type** is set to **Static routing** and the NQA function is enabled.

-  Viewing metrics on the Cloud Eye console

   #. Log in to the management console.
   #. Click |image9| in the upper left corner and select the desired region and project.
   #. In the upper left corner of the page, click |image10| and choose **Management & Deployment** > **Cloud Eye**.
   #. Choose **Cloud Service Monitoring** > **Virtual Private Network**.
   #. View metrics. The operations vary according to the VPN type.

      -  On the **S2C VPN Connection** tab page, click **View Metric** in the **Operation** column of the target VPN connection to view its status.

         You can view data of the last 15 minutes, last 30 minutes, last 1 hour, last 2 hours, last 3 hours, last 12 hours, last 24 hours, last 7 days, last 30 days, or a custom time range.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
.. |image3| image:: /_static/images/en-us_image_0000002088746373.png
.. |image4| image:: /_static/images/en-us_image_0000001628070572.png
.. |image5| image:: /_static/images/en-us_image_0000002381773998.png
.. |image6| image:: /_static/images/en-us_image_0000001628070572.png
.. |image7| image:: /_static/images/en-us_image_0000002394353329.png
.. |image8| image:: /_static/images/en-us_image_0000002361571346.png
.. |image9| image:: /_static/images/en-us_image_0000001628070572.png
.. |image10| image:: /_static/images/en-us_image_0000002381774546.png
