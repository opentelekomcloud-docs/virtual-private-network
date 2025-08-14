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

-  If the VPN gateway has connections, the connections will also be deleted.

-  An EIP bound to a VPN gateway will be released when the VPN gateway is deleted.

   To retain such a pay-per-use EIP, unbind it before deleting the VPN gateway. For details about how to unbind an EIP, see :ref:`Unbinding an EIP from a VPN Gateway <vpn_04_0807>`.

-  If a VPN gateway is bound to an EIP that shares bandwidth with other EIPs, the EIP will be released and the shared bandwidth will be reserved when the VPN gateway is deleted.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.
#. On the **S2C VPN Gateways** page, choose **More** > **Delete** or click **Delete** in the **Operation** column of the target VPN gateway.
#. In the **Delete VPN Gateway** dialog box, click **Auto Enter**.
#. Click **OK**.

   .. note::

      The impact of shared bandwidth freezing on EIPs is subject to the EIP documentation.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
