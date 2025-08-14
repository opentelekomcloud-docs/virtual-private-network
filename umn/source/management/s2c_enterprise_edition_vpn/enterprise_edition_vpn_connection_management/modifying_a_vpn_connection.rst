:original_name: vpn_ug_00014.html

.. _vpn_ug_00014:

Modifying a VPN Connection
==========================

Scenario
--------

A VPN connection is an encrypted communications channel established between a VPN gateway in a VPC and a customer gateway in your on-premises data center. You can modify a VPN connection when required.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.
#. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.
#. On the **VPN Connection** page, locate the VPN connection to modify, and click **Modify VPN Connection** or **Modify Policy Settings**.
#. Modify VPN connection parameters as prompted.

   -  For a VPN connection in BGP routing mode, you can enable or disable branch Interconnection on the **Modify VPN Connection** page.

#. Click **OK**.


.. figure:: /_static/images/en-us_image_0000001888093441.png
   :alt: **Figure 1** Modifying a VPN connection

   **Figure 1** Modifying a VPN connection

.. caution::

   If you change the PSK or modify the IKE or IPsec policy of a VPN connection, ensure that the new configurations are consistent with those on the customer gateway. Otherwise, the VPN connection will be interrupted.

Only some of the parameters take effect immediately after being modified, as described in :ref:`Table 1 <en-us_topic_0000001592773861__table19349926165716>`.

.. _en-us_topic_0000001592773861__table19349926165716:

.. table:: **Table 1** Time when new parameter settings take effect

   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | Item            | Parameter                   | When New Settings Take Effect                                                                   | How to Modify                                                                                                                        |
   +=================+=============================+=================================================================================================+======================================================================================================================================+
   | ``-``           | PSK                         | -  When IKEv1 is used, the new setting takes effect in the next negotiation period.             | -  When IKEv1 is used:                                                                                                               |
   |                 |                             | -  When IKEv2 is used, the new setting takes effect after the VPN connection is re-established. |                                                                                                                                      |
   |                 |                             |                                                                                                 |    Locate the VPN connection to modify, choose **More** > **Reset PSK** in the **Operation** column, and change the PSK as prompted. |
   |                 |                             |                                                                                                 |                                                                                                                                      |
   |                 |                             |                                                                                                 | -  When IKEv2 is used:                                                                                                               |
   |                 |                             |                                                                                                 |                                                                                                                                      |
   |                 |                             |                                                                                                 |    #. Delete the current VPN connection.                                                                                             |
   |                 |                             |                                                                                                 |    #. Create a new VPN connection.                                                                                                   |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IKEv1 policy    | -  Encryption Algorithm     | The new settings take effect in the next negotiation period.                                    | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   |                 | -  Authentication Algorithm |                                                                                                 |                                                                                                                                      |
   |                 | -  DH Algorithm             |                                                                                                 |                                                                                                                                      |
   |                 | -  Negotiation Mode         |                                                                                                 |                                                                                                                                      |
   |                 | -  Local ID                 |                                                                                                 |                                                                                                                                      |
   |                 | -  Customer ID              |                                                                                                 |                                                                                                                                      |
   |                 | -  Lifetime (s)             |                                                                                                 |                                                                                                                                      |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IKEv1 policy    | Version                     | The new setting takes effect immediately.                                                       | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IKEv2 policy    | -  Encryption Algorithm     | The new settings take effect in the next negotiation period.                                    | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   |                 | -  Authentication Algorithm |                                                                                                 |                                                                                                                                      |
   |                 | -  DH Algorithm             |                                                                                                 |                                                                                                                                      |
   |                 | -  Lifetime (s)             |                                                                                                 |                                                                                                                                      |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IKEv2 policy    | Version                     | The new setting takes effect immediately.                                                       | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IKEv2 policy    | -  Local ID                 | The new settings take effect after the VPN connection is re-established.                        | #. Delete the current VPN connection.                                                                                                |
   |                 | -  Customer ID              |                                                                                                 | #. Create a new VPN connection.                                                                                                      |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IPsec policy    | -  Encryption Algorithm     | The new settings take effect in the next negotiation period.                                    | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   |                 | -  Authentication Algorithm |                                                                                                 |                                                                                                                                      |
   |                 | -  PFS                      |                                                                                                 |                                                                                                                                      |
   |                 | -  Lifetime (s)             |                                                                                                 |                                                                                                                                      |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+
   | IPsec policy    | Transfer Protocol           | This parameter cannot be modified on the management console.                                    | Locate the VPN connection to delete, and choose **More** > **Modify Policy Settings** in the **Operation** column.                   |
   +-----------------+-----------------------------+-------------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------+

:ref:`Table 2 <en-us_topic_0000001592773861__table135441110101713>` describes the parameters related to VPN connection modification.

.. _en-us_topic_0000001592773861__table135441110101713:

.. table:: **Table 2** Parameters related to VPN connection modification

   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Parameter                         | Description                                                                                                                                          | Modifiable or Not     |
   +===================================+======================================================================================================================================================+=======================+
   | Name                              | VPN connection name. The value can contain only letters, digits, underscores (_), hyphens (-), and periods (.).                                      | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Customer Gateway                  | Gateway used for communicating with a VPC through VPN.                                                                                               | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Customer Subnet                   | Subnet in the on-premises data center that needs to access the VPC.                                                                                  | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Policy Settings                   | There are IKE and IPsec policies.                                                                                                                    | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | PSK                               | The PSKs configured for the VPN gateway and customer gateway must be the same.                                                                       | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Local Tunnel Interface Address    | Tunnel interface IP address configured on the VPN gateway.                                                                                           | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Customer Tunnel Interface Address | Tunnel interface IP address configured on the customer gateway device.                                                                               | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Branch Interconnection            | This parameter is available only when **VPN Type** is set to **BGP routing**.                                                                        | Y                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | EIP                               | This parameter is available only when **Network Type** is set to **Public network**.                                                                 | N                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Private IP address                | This parameter is available only when **Network Type** is set to **Private network**.                                                                | N                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | VPN Gateway                       | VPN gateway that has been created.                                                                                                                   | N                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Identifier                        | IP address used by the customer gateway to communicate with the VPN gateway. The value must be a static address.                                     | N                     |
   |                                   |                                                                                                                                                      |                       |
   |                                   | Ensure that UDP port 4500 is permitted in a firewall rule on the customer gateway in your on-premises data center or private network.                |                       |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
   | Interface IP Address Assignment   | Mode in which IP addresses of the local and customer interfaces are assigned. The options include **Manually specify** and **Automatically assign**. | N                     |
   +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
