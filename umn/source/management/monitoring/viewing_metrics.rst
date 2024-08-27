:original_name: vpn_04_0704.html

.. _vpn_04_0704:

Viewing Metrics
===============

Scenarios
---------

View the VPN connection status and usages of bandwidth and EIP. You can view data of the last 1, 3, 12, or 24 hours, or last 7 days.

Viewing VPN Gateway Metrics
---------------------------

-  Viewing metrics on the Cloud Eye console

   #. Log in to the management console.

   #. Click |image1| in the upper left corner and select the desired region and project.

   #. Click **Service List** and choose **Management & Deployment** > **Cloud Eye**.

   #. Choose **Cloud Service Monitoring** > **Virtual Private Network**.

   #. On the **Enterprise - VPN Gateways** page, locate the target VPN gateway, and click **View Metric** in the **Operation** column.

      You can view data of the last 1, 3, 12, or 24 hours, or last 7 days.

Viewing VPN Connection Metrics
------------------------------

-  Viewing metrics on the VPN console

   #. Log in to the management console.
   #. Click |image2| in the upper left corner and select the desired region and project.
   #. Click |image3| in the upper left corner of the management console, and choose **Networking** > **Virtual Private Network**.
   #. View metrics.

      -  Choose **Virtual Private Network** > **Enterprise - VPN Connections**, and click |image4| **View Metric** under the name of a VPN connection.

         The metrics include the following:

         -  VPN Connection Status

         -  Average Link RTT, Maximum Link RTT, Link Packet Loss Rate

            These metrics are displayed only after the health check function is enabled. To enable this function, click the name of a VPN connection and add health check items on the **Summary** tab page.

         -  Average Tunnel RTT, Maximum Tunnel RTT, Tunnel Packet Loss Rate

            These metrics are displayed only when **VPN Type** is set to **Static routing** and the NQA function is enabled.

-  Viewing metrics on the Cloud Eye console

   #. Log in to the management console.
   #. Click |image5| in the upper left corner and select the desired region and project.
   #. Click **Service List** and choose **Management & Deployment** > **Cloud Eye**.
   #. Choose **Cloud Service Monitoring** > **Virtual Private Network**.
   #. View metrics. The operations vary according to the VPN type.

      -  Enterprise Edition VPN: On the **Enterprise - VPN Gateways** page, locate the target VPN connection, and click **View Metric** in the **Operation** column to view the VPN connection status.

      -  Classic VPN: Click the **VPN Connections** tab, locate the target VPN connection, and click **View Metric** in the **Operation** column to view the VPN connection status.

         You can view data of the last 1, 3, 12, or 24 hours, or last 7 days.

.. |image1| image:: /_static/images/en-us_image_0000001592773953.png
.. |image2| image:: /_static/images/en-us_image_0000001542494126.png
.. |image3| image:: /_static/images/en-us_image_0000001924344277.png
.. |image4| image:: /_static/images/en-us_image_0000001878346114.png
.. |image5| image:: /_static/images/en-us_image_0000001542174442.png
