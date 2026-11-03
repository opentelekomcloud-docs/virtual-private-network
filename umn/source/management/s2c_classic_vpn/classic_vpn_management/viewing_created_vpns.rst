:original_name: vpn_04_0002.html

.. _vpn_04_0002:

Viewing Created VPNs
====================

Scenarios
---------

You can view details about an existing VPN.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network**.

   If Enterprise Edition VPN is available for the selected region, choose **Virtual Private Network** > **Classic**.

#. On the **Virtual Private Network** page, view the target VPN.

   If Enterprise Edition VPN is available for the selected region, view the target VPN on the **Classic** page.

   :ref:`Table 1 <en-us_topic_0000001542494026__en-us_topic_0013748707_table1573616693718>` describes the VPN status.

   .. _en-us_topic_0000001542494026__en-us_topic_0013748707_table1573616693718:

   .. table:: **Table 1** VPN status

      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Status        | Description                                                                                               |
      +===============+===========================================================================================================+
      | Normal        | The VPN is successfully created, and the on-premises data center can access the VPC properly.             |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Not connected | The VPN is successfully created but has not been used for communication with the on-premises data center. |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Creating      | The VPN is being created.                                                                                 |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Updating      | VPN information is being updated.                                                                         |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Deleting      | The VPN is being deleted.                                                                                 |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Abnormal      | The VPN is abnormal.                                                                                      |
      +---------------+-----------------------------------------------------------------------------------------------------------+
      | Frozen        | The VPN is frozen.                                                                                        |
      +---------------+-----------------------------------------------------------------------------------------------------------+


   .. figure:: /_static/images/en-us_image_0000001841947198.png
      :alt: **Figure 1** Viewing the created VPN

      **Figure 1** Viewing the created VPN

   |image3|

.. |image1| image:: /_static/images/en-us_image_0000001542015046.png
.. |image2| image:: /_static/images/en-us_image_0000002410094757.png
.. |image3| image:: /_static/images/en-us_image_0000001842101730.png
