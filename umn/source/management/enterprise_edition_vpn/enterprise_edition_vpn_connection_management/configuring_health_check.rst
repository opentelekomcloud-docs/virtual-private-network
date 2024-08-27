:original_name: vpn_ug_00023.html

.. _vpn_ug_00023:

Configuring Health Check
========================

Scenario
--------

After VPN connections are created, you can configure health check to enable the VPN gateway to send probe packets to the customer gateway to collect statistics about the round-trip time and packet loss rate of physical links. The statistics help you learn about the VPN connection quality. The Cloud Eye service monitors the round-trip time and packet loss rate of VPN links. For details, see :ref:`Metrics (Enterprise Edition VPN) <vpn_04_0702>`.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.
#. On the **VPN Connections** page, click the name of the target VPN connection. On the **Summary** tab page, click **Add** in the **Health Check** area.
#. In the **Add Health Check** dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000001923096425.png
