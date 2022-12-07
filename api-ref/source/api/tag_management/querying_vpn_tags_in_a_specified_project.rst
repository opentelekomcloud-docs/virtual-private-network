:original_name: en_topic_0093011489.html

.. _en_topic_0093011489:

Querying VPN Tags in a Specified Project
========================================

**Function**
------------

This interface is used to query all tags of a VPN in a specified region.

URI
---

GET /v2.0/{project_id}/ipsec-site-connections/tags

.. note::

   In the URI, **project_id** indicates the project ID.

Request Message
---------------

None

Response Message
----------------

:ref:`Table 1 <en_topic_0093011489__en-us_topic_0103470571_table18958160152014>` describes the response parameters.

.. _en_topic_0093011489__en-us_topic_0103470571_table18958160152014:

.. table:: **Table 1** Response parameter

   ========= ========= =======================
   Parameter Type      Description
   ========= ========= =======================
   tags      List<tag> Specifies the tag list.
   ========= ========= =======================

-  Description of field **tag**

+-----------------------+-----------------------+---------------------------------------------------------------------+
| Name                  | Type                  | Description                                                         |
+=======================+=======================+=====================================================================+
| key                   | String                | Specifies the tag key.                                              |
|                       |                       |                                                                     |
|                       |                       | The parameter constraints are as follows:                           |
|                       |                       |                                                                     |
|                       |                       | -  Cannot be left blank.                                            |
|                       |                       | -  Can contain a maximum of 36 characters.                          |
|                       |                       | -  Can contain only the following character types:                  |
|                       |                       |                                                                     |
|                       |                       |    -  Uppercase letters                                             |
|                       |                       |    -  Lowercase letters                                             |
|                       |                       |    -  Digits                                                        |
|                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------------+-----------------------+---------------------------------------------------------------------+
| values                | List<String>          | Specifies the tag value list.                                       |
|                       |                       |                                                                     |
|                       |                       | The parameter constraints are as follows:                           |
|                       |                       |                                                                     |
|                       |                       | -  Can contain a maximum of 43 characters.                          |
|                       |                       | -  Can contain only the following character types:                  |
|                       |                       |                                                                     |
|                       |                       |    -  Uppercase letters                                             |
|                       |                       |    -  Lowercase letters                                             |
|                       |                       |    -  Digits                                                        |
|                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------------+-----------------------+---------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/{project_id}/ipsec-site-connections/tags

-  Example Response

   .. code-block::

      {
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
          ]
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
