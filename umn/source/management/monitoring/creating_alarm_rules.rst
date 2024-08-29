:original_name: vpn_04_0703.html

.. _vpn_04_0703:

Creating Alarm Rules
====================

Scenarios
---------

You can configure alarm rules on the Cloud Eye console to keep track of your VPN status at any time.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner of the management console, and choose **Management & Deployment** > **Cloud Eye**.

#. Choose **Cloud Service Monitoring** > **Virtual Private Network**, click **Create Alarm Rule**, and configure alarm rules for different types of alarms as required.

   -  Alarms related to Enterprise Edition VPN gateways: Choose **S2C VPN Gateway** from the right drop-down list box, click the **Resources** tab, and choose **More** > **Create Alarm Rule** in the **Operation** column of a VPN gateway.
   -  Alarms related to Enterprise Edition VPN connections: Choose **S2C VPN Connection** from the right drop-down list box, click the **Resources** tab, and choose **More** > **Create Alarm Rule** in the **Operation** column of a VPN connection.
   -  Alarms related to Classic VPN connections: Choose **VPN Connections** from the right drop-down list box, click the **Resources** tab, and choose **More** > **Create Alarm Rule** in the **Operation** column of a VPN connection.

#. Click **Create**.

   After the alarm rule is created, if you have enabled **Alarm Notification** and configured required parameters, you will receive notifications once an alarm is triggered.

   .. note::

      For more information about VPN alarm rules, see the *Cloud Eye User Guide*.

.. |image1| image:: /_static/images/en-us_image_0000001542334206.png
.. |image2| image:: /_static/images/en-us_image_0000001878270362.png
