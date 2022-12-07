:original_name: en-us_topic_0030969471.html

.. _en-us_topic_0030969471:

Deleting a Security Group Rule
==============================

Scenarios
---------

If the source of an inbound security group rule or destination of an outbound security group rule needs to be changed, you need to first delete the security group rule and add a new one.

.. note::

   Security group rules use whitelists. Deleting a security group rule may result in ECS access failures. Exercise caution when deleting security group rules.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. On the console homepage, under **Network**, click **Virtual Private Cloud**.
#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.
#. On the **Security Groups** page, click the security group name.
#. If you do not need a security group rule, locate the row that contains the target rule, and click **Delete**.
#. Click **Yes** in the displayed dialog box.

**Deleting Multiple Security Group Rules at Once.**

You can also select multiple security group rules and click **Delete** above the security group rule list to delete multiple rules at a time.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
