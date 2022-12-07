:original_name: en-us_topic_0030969470.html

.. _en-us_topic_0030969470:

Adding a Security Group Rule
============================

Scenarios
---------

After a security group is created, you can add rules to the security group. A rule applies either to inbound traffic (ingress) or outbound traffic (egress). After ECSs are added to the security group, they are protected by the rules of that group.

-  Inbound rules control incoming traffic to ECSs associated with the security group.
-  Outbound rules control outgoing traffic from ECSs associated with the security group.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

#. On the **Security Groups** page, locate the target security group and click **Manage Rule** in the **Operation** column to switch to the page for managing inbound and outbound rules.

#. On the inbound rule tab, click **Add Rule**. In the displayed dialog box, set required parameters to add an inbound rule.

   You can click **+** to add more inbound rules.


   .. figure:: /_static/images/en-us_image_0210485645.png
      :alt: **Figure 1** Add Inbound Rule

      **Figure 1** Add Inbound Rule

   .. table:: **Table 1** Inbound rule parameter description

      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                              | Example Value         |
      +=======================+==========================================================================================================================================================+=======================+
      | Protocol/Application  | Specifies the network protocol. Currently, the value can be **All**, **TCP**, **UDP**, **ICMP**, **GRE**, or others.                                     | TCP                   |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Port & Source         | **Port**: specifies the port or port range over which the traffic can reach your ECS. The value ranges from 1 to 65535.                                  | 22 or 22-30           |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Source**: specifies the source of the security group rule. The value can be another security group, a CIDR block, or a single IP address. For example: | 0.0.0.0/0             |
      |                       |                                                                                                                                                          |                       |
      |                       | -  xxx.xxx.xxx.xxx/32 (IPv4 address)                                                                                                                     | default               |
      |                       | -  xxx.xxx.xxx.0/24 (subnet CIDR block)                                                                                                                  |                       |
      |                       | -  0.0.0.0/0 (any IP address)                                                                                                                            |                       |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the security group rule. This parameter is optional.                                                            | N/A                   |
      |                       |                                                                                                                                                          |                       |
      |                       | The security group rule description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                  |                       |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. On the outbound rule tab, click **Add Rule**. In the displayed dialog box, set required parameters to add an outbound rule.

   You can click **+** to add more outbound rules.


   .. figure:: /_static/images/en-us_image_0210486152.png
      :alt: **Figure 2** Add Outbound Rule

      **Figure 2** Add Outbound Rule

   .. table:: **Table 2** Outbound rule parameter description

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                        | Example Value         |
      +=======================+====================================================================================================================================================================+=======================+
      | Protocol/Application  | Specifies the network protocol. Currently, the value can be **All**, **TCP**, **UDP**, **ICMP**, **GRE**, or others.                                               | TCP                   |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Port & Destination    | **Port**: specifies the port or port range over which the traffic can leave your ECS. The value ranges from 1 to 65535.                                            | 22 or 22-30           |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Destination**: specifies the destination of the security group rule. The value can be another security group, a CIDR block, or a single IP address. For example: | 0.0.0.0/0             |
      |                       |                                                                                                                                                                    |                       |
      |                       | -  xxx.xxx.xxx.xxx/32 (IPv4 address)                                                                                                                               | default               |
      |                       | -  xxx.xxx.xxx.0/24 (subnet CIDR block)                                                                                                                            |                       |
      |                       | -  0.0.0.0/0 (any IP address)                                                                                                                                      |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the security group rule. This parameter is optional.                                                                      | N/A                   |
      |                       |                                                                                                                                                                    |                       |
      |                       | The security group rule description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                            |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
