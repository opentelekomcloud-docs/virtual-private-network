:original_name: vpn_ug_00025.html

.. _vpn_ug_00025:

Viewing Failure Information
===========================

Scenario
--------

If a VPN gateway fails to be created or upgraded, you can view the failure cause.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Gateways**.
#. On the **S2C VPN Gateways** page, click **Failure records** in the upper right corner to view the failure cause.

   .. table:: **Table 1** Common failure causes

      +------------------------------+-----+---------------------------------------------------------+
      | Category                     | No. | Error Information                                       |
      +==============================+=====+=========================================================+
      | VPN gateway creation failure | 1   | Internal error.                                         |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 2   | Failed to create underlying resources. Try again later. |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 3   | No IAM permission: {{0}}.                               |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 4   | Tag {{0}} is not supported by EIP.                      |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 5   | Failed to create the VPC subnet. Try again later.       |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 6   | No available EIP.                                       |
      +------------------------------+-----+---------------------------------------------------------+
      | Gateway upgrade failure      | 1   | Configuration delivery timed out.                       |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 2   | Failed to create a worker.                              |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 3   | Failed to create an NGP gateway instance.               |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 4   | Failed to attach the network interface.                 |
      +------------------------------+-----+---------------------------------------------------------+
      |                              | 5   | Failed to detach the network interface.                 |
      +------------------------------+-----+---------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
