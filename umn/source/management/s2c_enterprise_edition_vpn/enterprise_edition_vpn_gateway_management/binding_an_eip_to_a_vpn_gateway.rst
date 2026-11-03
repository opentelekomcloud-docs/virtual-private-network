:original_name: vpn_ug_00004.html

.. _vpn_ug_00004:

Binding an EIP to a VPN Gateway
===============================

Scenario
--------

You can bind EIPs to a VPN gateway that has been created.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.
#. On the **S2C VPN Gateways** page, click **Bind EIP** in the **Operation** column of the target VPN gateway.

   -  If the VPN gateway uses the active-active mode, the VPN gateway can have an active EIP and active EIP 2 bound.
   -  If the VPN gateway uses the active/standby mode, the VPN gateway can have an active EIP and a standby EIP bound.

#. Select the desired EIP and click **OK**.


.. figure:: /_static/images/en-us_image_0000001852883004.png
   :alt: **Figure 1** Binding the active EIP in active-active mode

   **Figure 1** Binding the active EIP in active-active mode


.. figure:: /_static/images/en-us_image_0000001899247569.png
   :alt: **Figure 2** Binding active EIP 2 in active-active mode

   **Figure 2** Binding active EIP 2 in active-active mode


.. figure:: /_static/images/en-us_image_0000001987358196.png
   :alt: **Figure 3** Binding the active EIP in active/standby mode

   **Figure 3** Binding the active EIP in active/standby mode


.. figure:: /_static/images/en-us_image_0000002023918497.png
   :alt: **Figure 4** Binding the standby EIP in active/standby mode

   **Figure 4** Binding the standby EIP in active/standby mode

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
