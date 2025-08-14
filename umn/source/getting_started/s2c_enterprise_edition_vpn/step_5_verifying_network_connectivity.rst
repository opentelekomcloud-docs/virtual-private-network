:original_name: vpn_03_0337.html

.. _vpn_03_0337:

Step 5: Verifying Network Connectivity
======================================

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Compute** > **Elastic Cloud Server**.

#. Log in to an ECS.

   Login using VNC on the management console is used as an example.

#. Run the following command on the ECS:

   **ping 172.16.0.100**

   172.16.0.100 is the IP address of a server in the on-premises data center. Replace it with an actual server IP address.

   If information similar to the following is displayed, the VPC on the cloud and the on-premises data center can communicate with each other.

   .. code-block::

      Reply from xx.xx.xx.xx: bytes=32 time=28ms TTL=245
      Reply from xx.xx.xx.xx: bytes=32 time=28ms TTL=245
      Reply from xx.xx.xx.xx: bytes=32 time=28ms TTL=245
      Reply from xx.xx.xx.xx: bytes=32 time=27ms TTL=245

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002410094213.png
