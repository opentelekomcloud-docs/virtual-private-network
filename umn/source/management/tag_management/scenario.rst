:original_name: vpn_08_1514.html

.. _vpn_08_1514:

Scenario
========

VPN tags are used to identify VPN resources, facilitating VPN resource identification and management. You can add tags for a VPN resource when you create the VPN resource. Alternatively, you add tags for an existing VPN resource on the resource details page. A maximum of 20 tags can be added for each VPN resource.

A tag consists of a key and a value. :ref:`Table 1 <en-us_topic_0000001917695266__en-us_topic_0000001936159521_en-us_topic_0000001591737181_en-us_topic_0013859511_table1794599823119>` describes the requirements on the keys and values of VPN tags.

.. _en-us_topic_0000001917695266__en-us_topic_0000001936159521_en-us_topic_0000001591737181_en-us_topic_0013859511_table1794599823119:

.. table:: **Table 1** Requirements on the keys and values of VPN tags

   +-----------------------+---------------------------------------------+-----------------------+
   | Parameter             | Requirement                                 | Example Value         |
   +=======================+=============================================+=======================+
   | Key                   | -  Cannot be left blank.                    | vpn_key1              |
   |                       | -  Must be unique for the same VPN.         |                       |
   |                       | -  Can contain a maximum of 128 characters. |                       |
   +-----------------------+---------------------------------------------+-----------------------+
   | Value                 | -  Can contain a maximum of 255 characters. | vpn-01                |
   +-----------------------+---------------------------------------------+-----------------------+
