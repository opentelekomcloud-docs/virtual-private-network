:original_name: vpn_04_0703.html

.. _vpn_04_0703:

Creating a Monitoring Alarm Rule
================================

Scenarios
---------

You can create monitoring alarm rules to customize monitored objects and notification policies, so that you can be well-informed of the VPN service status.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. In the upper left corner of the page, click |image2| and choose **Management & Deployment** > **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Rules**, and click **Create Alarm Rule**.

#. Select **Virtual Private Network** from the **Resource Type** drop-down list box, and configure alarm rules for different types of alarms.

   -  Alarms related to VPN gateways in S2C Enterprise Edition VPN: Click **S2C VPN Gateway**, and configure alarm rules.
   -  Alarms related to VPN connections in S2C Enterprise Edition VPN: Click **S2C VPN Connection**, and configure alarm rules.
   -  Alarms related to VPN connections in S2C Classic VPN: Click **VPN Connections**, and configure alarm rules.

#. Click **Create**.

   After the VPN monitoring alarm rule is configured, if you have enabled alarm notifications and configured related parameters, you will receive notifications once an alarm is triggered.

   .. note::

      For more information about VPN alarm rules, see the *Cloud Eye User Guide*.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002429419085.png
