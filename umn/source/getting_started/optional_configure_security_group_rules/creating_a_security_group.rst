:original_name: en-us_topic_0013748715.html

.. _en-us_topic_0013748715:

Creating a Security Group
=========================

Scenarios
---------

To improve ECS access security, you can create a security group, define security group rules, and add ECSs in the VPC to the security group. We recommend that you allocate ECSs that have different Internet access policies to different security groups.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

#. On the **Security Groups** page, click **Create Security Group**.

#. In the **Create Security Group** area, set the parameters as prompted. :ref:`Table 1 <en-us_topic_0013748715__en-us_topic_0118534004_table65377617111335>` lists the parameters to be configured.


   .. figure:: /_static/images/en-us_image_0118534037.png
      :alt: **Figure 1** Create Security Group

      **Figure 1** Create Security Group

   .. _en-us_topic_0013748715__en-us_topic_0118534004_table65377617111335:

   .. table:: **Table 1** Parameter description

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                          | Example Value         |
      +=======================+======================================================================================================================================================================================+=======================+
      | Name                  | Specifies the security group name. This parameter is mandatory.                                                                                                                      | sg-318b               |
      |                       |                                                                                                                                                                                      |                       |
      |                       | The security group name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces. |                       |
      |                       |                                                                                                                                                                                      |                       |
      |                       | .. note::                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                      |                       |
      |                       |    You can change the security group name after a security group is created. It is recommended that you use different names for different security groups.                           |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the security group. This parameter is optional.                                                                                             | N/A                   |
      |                       |                                                                                                                                                                                      |                       |
      |                       | The security group description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                   |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
