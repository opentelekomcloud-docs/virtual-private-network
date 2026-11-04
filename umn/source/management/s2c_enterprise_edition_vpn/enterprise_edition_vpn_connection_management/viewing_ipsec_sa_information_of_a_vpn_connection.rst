:original_name: vpn_04_4213.html

.. _vpn_04_4213:

Viewing IPsec SA Information of a VPN Connection
================================================

Scenario
--------

After a VPN connection is established, you can view its IPsec SA information.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.

#. On the **VPN Connection** page, click the name of a VPN connection. The VPN connection details page is displayed.

#. Click the **IPsec SA** tab, and view IPsec SA information of the VPN connection.

   The IPsec SA information of a VPN connection is displayed only when the VPN connection is in normal state. The IPsec SA information includes the SA ID, source IP address, destination IP address, number of received packets, number of sent packets, received traffic (bytes), sent traffic (bytes), and collection time.

   .. note::

      -  If an IPsec SA of a VPN connection is interrupted, the SA information can still be queried, but the number of received packets, number of sent packets, received traffic (bytes), and sent traffic (bytes) are all **0**.
      -  If an IPsec SA fails to be negotiated, the SA information cannot be queried.

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
