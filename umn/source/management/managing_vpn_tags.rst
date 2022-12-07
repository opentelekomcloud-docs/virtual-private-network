:original_name: en-us_topic_0107396413.html

.. _en-us_topic_0107396413:

Managing VPN Tags
=================

Application Scenarios
---------------------

A VPN tag identifies a VPN. Tags can be added to VPNs to facilitate VPN identification and administration. You can add a tag to a VPN when creating the VPN. Alternatively, you can add a tag to a created VPN on the VPN details page. A maximum of ten tags can be added to each VPN.

A tag consists of a key and value pair. :ref:`Table 1 <en-us_topic_0107396413__en-us_topic_0013859511_table1794599823119>` lists the tag key and value requirements.

.. _en-us_topic_0107396413__en-us_topic_0013859511_table1794599823119:

.. table:: **Table 1** VPN tag key and value requirements

   +-----------------------+----------------------------------------------------------------------------+-----------------------+
   | Parameter             | Requirement                                                                | Example Value         |
   +=======================+============================================================================+=======================+
   | Key                   | -  Cannot be left blank.                                                   | vpn_key1              |
   |                       | -  Must be unique for the same VPN and can be the same for different VPNs. |                       |
   |                       | -  Contains a maximum of 36 characters.                                    |                       |
   |                       | -  Can contain only the following character types:                         |                       |
   |                       |                                                                            |                       |
   |                       |    -  Uppercase letters                                                    |                       |
   |                       |    -  Lowercase letters                                                    |                       |
   |                       |    -  Digits                                                               |                       |
   |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
   +-----------------------+----------------------------------------------------------------------------+-----------------------+
   | Value                 | -  Can contain a maximum of 43 characters.                                 | vpn-01                |
   |                       | -  Can contain only the following character types:                         |                       |
   |                       |                                                                            |                       |
   |                       |    -  Uppercase letters                                                    |                       |
   |                       |    -  Lowercase letters                                                    |                       |
   |                       |    -  Digits                                                               |                       |
   |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
   +-----------------------+----------------------------------------------------------------------------+-----------------------+

**Procedure**
-------------

**Search for VPNs by Tag Key and Value on the Page Showing the VPN List.**

#. Log in to the management console.

#. Click |image1| in the upper left corner and select a region and project.

#. On the console homepage, under **Network**, click **Virtual Private Network**.

#. In the upper right corner of the VPN list, click **Search by Tag**.

#. In the displayed area, enter the tag key and value of the VPN you are looking for.

   Both the tag key and value must be specified.

#. Click **+** to add the entered tag key and value.

   You can add multiple tag keys and values to refine your search results. If you add more than one tag to search for VPCs, the VPCs containing all specified tags will be displayed.

#. Click **Search**.

   The system displays the VPNs you are looking for based on the entered tag keys and values.

**Add, Delete, Edit, and View Tags on the Tags Tab of a VPN.**

#. Log in to the management console.

#. Click |image2| in the upper left corner and select a region and project.

#. On the console homepage, under **Network**, click **Virtual Private Network**.

#. On the **Virtual Private Network** page, locate the VPN whose tags are to be managed and click the VPN name.

   The page showing details about the particular VPN is displayed.

#. Click the **Tags** tab and perform desired operations on tags.

   -  View tags.

      On the **Tags** tab, you can view details about tags added to the current VPN, including the number of tags and the key and value of each tag.

   -  Add a tag.

      Click **Add Tag** in the upper left corner. In the displayed dialog box, enter the key and value of the tag to be added, and click **OK**.

   -  Edit a tag.

      Locate the row that contains the tag to be edited and click **Edit** in the **Operation** column. In the **Edit Tag** dialog box, change the tag value and click **OK**.

   -  Delete a tag.

      Locate the row that contains the tag to be deleted, and click **Delete** in the **Operation** column. In the displayed **Delete Tag** dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0107432228.png
.. |image2| image:: /_static/images/en-us_image_0107432228.png
