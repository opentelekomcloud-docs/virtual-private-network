:original_name: en_topic_0093011484.html

.. _en_topic_0093011484:

Querying VPN Resource Instances by Tag
======================================

**Function**
------------

This interface is used to query VPN resource instances by tag.

Tag Management Service (TMS) uses this API to filter out service resources and display them in a list. These services must have the query capabilities.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/resource_instances/action

Request Message
---------------

:ref:`Table 1 <en_topic_0093011484__table45111823181914>` describes the request parameters.

.. _en_topic_0093011484__table45111823181914:

.. table:: **Table 1** Request parameters

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   +=================+=================+=================+=============================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | tags            | List<tag>       | No              | Specifies the included tags. Each tag contains a maximum of 10 keys, and each key contains a maximum of 10 values. The structure body cannot be missing, and the key cannot be left blank or set to an empty string. Each tag key must be unique, and each tag value in a tag must be unique.                                                                                                                                                                                                                                               |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit           | Integer         | No              | Sets the page size. This parameter is not available when **action** is set to **count**. The default value is **1000** when **action** is set to **filter**. The maximum value is **1000**, and the minimum value is **1**. The value cannot be a negative number.                                                                                                                                                                                                                                                                          |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | offset          | Integer         | No              | Specifies the index position. The query starts from the next piece of data indexed by this parameter. This parameter is not required when you query data on the first page. The value in the response returned for querying data on the previous page will be included in this parameter for querying data on subsequent pages. This parameter is not available when **action** is set to **count**. If **action** is set to **filter**, the value must be a number, and the default value is **0**. The value cannot be a negative number. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action          | String          | Yes             | Specifies the operation to perform. The value can only be **filter** (filtering) or **count** (querying the total number).                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |                 |                 |                 | The value **filter** indicates pagination query. The value **count** indicates that the total number of query results meeting the search criteria will be returned.                                                                                                                                                                                                                                                                                                                                                                         |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | matches         | List<match>     | No              | Specifies the search criteria. The tag key is the field to match. Currently, only **resource_name** is supported. The tag value indicates the value to be matched. The **key** field is a fixed dictionary value.                                                                                                                                                                                                                                                                                                                           |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Description of field **tag**

+--------+--------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Name   | Type         | Mandatory | Description                                                                                                                                                                                                                               |
+========+==============+===========+===========================================================================================================================================================================================================================================+
| key    | String       | Yes       | Specifies the tag key. It contains a maximum of 127 Unicode characters. It cannot be left blank. (This parameter is not verified in the search process.)                                                                                  |
+--------+--------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| values | List<String> | Yes       | Specifies the tag value list. Each value can contain a maximum of 255 Unicode characters. An empty list for **values** indicates any value. The resources containing one or more values listed in **values** will be found and displayed. |
+--------+--------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Description of field **match**

+-------+--------+-----------+--------------------------------------------------------------------------------------+
| Name  | Type   | Mandatory | Description                                                                          |
+=======+========+===========+======================================================================================+
| key   | String | Yes       | Specifies the tag key. Currently, the tag key can only be the resource name.         |
+-------+--------+-----------+--------------------------------------------------------------------------------------+
| value | String | Yes       | Specifies the tag value. Each value can contain a maximum of 255 Unicode characters. |
+-------+--------+-----------+--------------------------------------------------------------------------------------+

Response Parameter
------------------

:ref:`Table 2 <en_topic_0093011484__table1135702419184>` describes the response parameters.

.. _en_topic_0093011484__table1135702419184:

**Table 2** Response Parameter

=========== ============== ======================================
Name        Type           Description
=========== ============== ======================================
resources   List<resource> N/A
total_count int            Specifies the total number of records.
=========== ============== ======================================

.. table:: **Table 3** Description of field **resource**

   +----------------+--------------------+------------------------------------------------------------------------------------------------------------------------------+
   | Name           | Type               | Description                                                                                                                  |
   +================+====================+==============================================================================================================================+
   | resource_id    | String             | Specifies the resource ID.                                                                                                   |
   +----------------+--------------------+------------------------------------------------------------------------------------------------------------------------------+
   | resouce_detail | Object             | Specifies the resource details. The value is a resource object, used for extension. This parameter is left blank by default. |
   +----------------+--------------------+------------------------------------------------------------------------------------------------------------------------------+
   | tags           | List<resource_tag> | Specifies the tag list. This parameter is an empty array by default if there is no tag.                                      |
   +----------------+--------------------+------------------------------------------------------------------------------------------------------------------------------+
   | resource_name  | String             | Specifies the resource name. This parameter is an empty string by default if there is no resource name.                      |
   +----------------+--------------------+------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Request Example

   .. code-block:: text

      POST /v2.0/{project_id}/ipsec-site-connections/resource_instances/action

-  Request Body

   -  Request body when **action** is set to **filter**

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

   -  Request body when **action** is set to **count**

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

-  Example Response

   -  Response body when **action** is set to **filter**

   .. code-block::

      {
            "resources": [
               {
                  "resource_detail": null,
                  "resource_id": "cdfs_cefs_wesas_12_dsad",
                  "resource_name": "resouece1",
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


   -  Response body when **action** is set to **count**

   .. code-block::

      {
             "total_count": 1000
      }
