:original_name: vpn_ug_00024.html

.. _vpn_ug_00024:

Upgrading a Gateway
===================

Overview
--------

You can determine whether a VPN gateway can be upgraded by checking whether the upgrade button is available in the **Operation** column of the VPN gateway.

-  If no upgrade button is available, the VPN gateway cannot be upgraded.
-  If the upgrade button is available, the VPN gateway can be upgraded.

You can determine whether to perform a rollback when the gateway status is **Upgrade to be committed**.

Upgrade Impact
--------------

-  During the upgrade, VPN connections will be interrupted. Typically, the interruption lasts less than 10 minutes, and the entire upgrade takes less than 30 minutes.
-  You cannot perform operations on a VPN gateway or its VPN connections during the upgrade.

Rollback
--------

After the upgrade, you need to check whether services are normal. If there are any exceptions, you can roll back the upgrade. If services are normal, you can commit the upgrade, after which a rollback is not supported.

Procedure
---------


.. figure:: /_static/images/en-us_image_0000002273800150.png
   :alt: **Figure 1** Upgrade flowchart

   **Figure 1** Upgrade flowchart

#. Upgrade a gateway.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select the desired region and project.
   c. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
   d. On the **S2C VPN Gateways** page, locate the target VPN gateway, and click **Upgrade Gateway** in the **Operation** column.
   e. In the dialog box that is displayed, read the upgrade impact and rollback information, select **I understand the above information**, and click **OK**.
   f. Check the upgrade status. During the upgrade, you can click **View task** in the **Status** column of the VPN gateway to view the upgrade progress.

      -  If the upgrade is successful, the gateway status changes to **Upgrade to be committed**. Go to :ref:`2 <en-us_topic_0000002298523549__li12041349193518>`.
      -  If the upgrade fails, a rollback is automatically performed. You can view the failure information in the upper right corner of the VPN gateway list.

#. .. _en-us_topic_0000002298523549__li12041349193518:

   Check whether services are normal.

   a. If services are normal, click **Commit Upgrade** in the **Operation** column to commit the upgrade.

      .. important::

         After you commit the upgrade, a rollback is not supported. Exercise caution when performing this operation.

   b. If services are abnormal, click **Roll Back** in the **Operation** column, and submit a service ticket to contact technical support.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
