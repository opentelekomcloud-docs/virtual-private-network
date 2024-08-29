:original_name: vpn_api_1016.html

.. _vpn_api_1016:

Querying VPNs by Tag
====================

Function
--------

This API is used to query VPNs by tag.

Tag Management Service (TMS) filters service resource instances by tag and displays them in a list.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/resource_instances/action

Request
-------

:ref:`Table 1 <en-us_topic_0000001807370524__en-us_topic_0000001591616789_table45111823181914>` describes the request parameters.

.. _en-us_topic_0000001807370524__en-us_topic_0000001591616789_table45111823181914:

.. table:: **Table 1** Request parameters

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                                                       |
   +=================+=================+=================+===================================================================================================================================================================================================================+
   | tags            | List<tag>       | No              | Specifies the list of tags.                                                                                                                                                                                       |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | -  Up to 10 keys are supported.                                                                                                                                                                                   |
   |                 |                 |                 | -  Each key can have a maximum of 10 tag values. **values** of each tag is mandatory and can be an empty array.                                                                                                   |
   |                 |                 |                 | -  The tag key cannot be left blank or be an empty string.                                                                                                                                                        |
   |                 |                 |                 | -  Each tag key must be unique, and each tag value in a tag must be unique.                                                                                                                                       |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | Integer         | No              | Specifies the maximum number of resources to be queried.                                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | -  If **action** is set to **count**, this parameter is not required.                                                                                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | -  If **action** is set to **filter**, the default value of **limit** is **1000**.                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 |    Supported range: 1 to 1000                                                                                                                                                                                     |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | Integer         | No              | Specifies the index position. The query starts from the next data record indexed by this parameter.                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | -  You do not need to specify this parameter when querying resources on the first page.                                                                                                                           |
   |                 |                 |                 | -  When you query resources on subsequent pages, set **offset** to the location returned in the response body for the previous query.                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 |    -  If **action** is set to **count**, this parameter is not required.                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 |    -  If **action** is set to **filter**, the default value is **0**.                                                                                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 |       The offset must be a number and cannot be negative.                                                                                                                                                         |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | String          | Yes             | Specifies the operation identifier.                                                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | The identifier can be **filter** or **count**.                                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                                                   |
   |                 |                 |                 | -  **filter**: Query data in pages.                                                                                                                                                                               |
   |                 |                 |                 | -  **count**: returns the total number of records that meet specified conditions.                                                                                                                                 |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | List<match>     | No              | Specifies the search criteria. The tag key is the field to match. Currently, only **resource_name** is supported. The tag value indicates the value to be matched. The **key** field is a fixed dictionary value. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Description of field **tag**

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
   | Name            | Type            | Mandatory       | Description                                                                                      |
   +=================+=================+=================+==================================================================================================+
   | key             | String          | Yes             | Specifies the tag key.                                                                           |
   |                 |                 |                 |                                                                                                  |
   |                 |                 |                 | -  A key can contain a maximum of 127 Unicode characters.                                        |
   |                 |                 |                 | -  **Key** cannot be left blank.                                                                 |
   |                 |                 |                 | -  (This parameter is not verified in the search process.)                                       |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+
   | values          | List<String>    | Yes             | Specifies the list of tag values.                                                                |
   |                 |                 |                 |                                                                                                  |
   |                 |                 |                 | -  Each value can contain a maximum of 255 Unicode characters.                                   |
   |                 |                 |                 |                                                                                                  |
   |                 |                 |                 |    If **values** is an empty list, it indicates **any_value**.                                   |
   |                 |                 |                 |                                                                                                  |
   |                 |                 |                 | -  The resources containing one or more values listed in **values** will be found and displayed. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Description of field **match**

   +-----------------+-----------------+-----------------+-------------------------------------------------------------+
   | Name            | Type            | Mandatory       | Description                                                 |
   +=================+=================+=================+=============================================================+
   | key             | String          | Yes             | Specifies the tag key.                                      |
   |                 |                 |                 |                                                             |
   |                 |                 |                 | The tag key can only be the resource name.                  |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------+
   | value           | String          | Yes             | Specifies the tag value.                                    |
   |                 |                 |                 |                                                             |
   |                 |                 |                 | Each value can contain a maximum of 255 Unicode characters. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------+

Response
--------

:ref:`Table 4 <en-us_topic_0000001807370524__en-us_topic_0000001591616789_table669961372515>` describes the response parameters.

.. _en-us_topic_0000001807370524__en-us_topic_0000001591616789_table669961372515:

.. table:: **Table 4** Response parameters

   =========== ============== ======================================
   Name        Type           Description
   =========== ============== ======================================
   resources   List<resource> N/A
   total_count int            Specifies the total number of records.
   =========== ============== ======================================

.. table:: **Table 5** Description of field **resource**

   +-----------------------+-----------------------+----------------------------------------------------------------------------+
   | Name                  | Type                  | Description                                                                |
   +=======================+=======================+============================================================================+
   | resource_id           | String                | Specifies the resource ID.                                                 |
   +-----------------------+-----------------------+----------------------------------------------------------------------------+
   | resource_detail       | Object                | Specifies the resource details.                                            |
   |                       |                       |                                                                            |
   |                       |                       | The details are left blank by default.                                     |
   +-----------------------+-----------------------+----------------------------------------------------------------------------+
   | tags                  | List<resource_tag>    | Specifies the list of tags.                                                |
   |                       |                       |                                                                            |
   |                       |                       | If there is no tag in the list, **tags** is taken as an empty array.       |
   +-----------------------+-----------------------+----------------------------------------------------------------------------+
   | resource_name         | String                | Specifies the resource name.                                               |
   |                       |                       |                                                                            |
   |                       |                       | If there is no resource name, the parameter is an empty string by default. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------+

Example
-------

-  Request example

   .. code-block:: text

      POST /v2.0/{project_id}/ipsec-site-connections/resource_instances/action

-  Request body

   -  **action** is set to **filter**.

      .. code-block::

         {
             "offset": "0",
             "limit": "100",
             "action": "filter",
             "matches": [
                 {
                     "key": "resource_name",
                     "value": "resource1"
                 }
             ],
             "tags": [
                 {
                     "key": "key1",
                     "values": [
                         "*value1",
                         "value2"
                     ]
                 }
             ]
         }

   -  **action** is set to **count**.

      .. code-block::

         {
             "action": "count",
             "tags": [
                 {
                     "key": "key1",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 },
                 {
                     "key": "key2",
                     "values": [
                         "value1",
                         "value2"
                     ]
                 }
             ],
             "matches": [
                 {
                     "key": "resource_name",
                     "value": "resource1"
                 }
             ]
         }

-  Example response

   -  **action** is set to **filter**.

      .. code-block::

         {
               "resources": [
                  {
                     "resource_detail": null,
                     "resource_id": "cdfs_cefs_wesas_12_dsad",
                     "resource_name": "resource1",
                     "tags": [
                         {
                            "key": "key1",
                            "value": "value1"
                         },
                         {
                            "key": "key2",
                            "value": "value1"
                         }
                      ]
                  }
                ],
               "total_count": 1000
         }


   -  **action** is set to **count**.

      .. code-block::

         {
                "total_count": 1000
         }
