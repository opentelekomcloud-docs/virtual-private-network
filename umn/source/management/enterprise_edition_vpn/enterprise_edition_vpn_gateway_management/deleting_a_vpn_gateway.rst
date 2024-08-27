:original_name: vpn_ug_00007.html

.. _vpn_ug_00007:

Deleting a VPN Gateway
======================

Scenario
--------

You can delete a VPN gateway that is no longer required.

Notes and Constraints
---------------------

-  The delete operation is not supported for a VPN gateway that is being created, updated, or deleted.

-  If a VPN gateway has VPN connections configured, you need to delete all the VPN connections before deleting the VPN gateway.

   For details about how to delete a VPN connection, see :ref:`Deleting a VPN Connection <vpn_04_1003>`.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner of the page, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.

#. If the number of bound EIPs is less than or equal to 1, choose **More** > **Delete** in the **Operation** column of the target VPN gateway.

   If the number of bound EIPs is greater than 1, click **Delete** in the **Operation** column of the target VPN gateway.

#. In the displayed dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000001923096425.png
