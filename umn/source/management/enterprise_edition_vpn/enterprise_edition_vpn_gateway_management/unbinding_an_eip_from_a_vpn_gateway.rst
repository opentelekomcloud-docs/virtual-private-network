:original_name: vpn_04_0807.html

.. _vpn_04_0807:

Unbinding an EIP from a VPN Gateway
===================================

Scenario
--------

After a VPN gateway is created, you can unbind an EIP from it.

Notes and Constraints
---------------------

An EIP that is in use by a VPN connection cannot be unbound from a VPN gateway.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.

#. Locate the row that contains the target VPN gateway, and click **Unbind EIP** or choose **More** > **Unbind EIP** in the **Operation** column.

   -  If the VPN gateway uses the active-active mode, the active EIP and active EIP 2 can be unbound from the VPN gateway.
   -  If the VPN gateway uses the active/standby mode, the active EIP and standby EIP can be unbound from the VPN gateway.


   .. figure:: /_static/images/en-us_image_0000001987537886.png
      :alt: **Figure 1** Unbinding an EIP from the VPN gateway

      **Figure 1** Unbinding an EIP from the VPN gateway

#. In the displayed dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000001923096425.png
