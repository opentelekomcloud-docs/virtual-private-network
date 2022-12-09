:original_name: en_topic_0093011486.html

.. _en_topic_0093011486:

Creating a Tag for a VPN Resource
=================================

**Function**
------------

This interface is used to create a tag for a VPN resource.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags

.. note::

   In the URI, **project_id** indicates the project ID, and **resource_id** indicates the target resource ID.

Request Message
---------------

:ref:`Table 1 <en_topic_0093011486__en-us_topic_0103470566_table14751112719406>` describes the request parameters.

.. _en_topic_0093011486__en-us_topic_0103470566_table14751112719406:

.. table:: **Table 1** Request parameters

   ========= ================== ========= ==================
   Parameter Type               Mandatory Description
   ========= ================== ========= ==================
   tag       List<resource_tag> Yes       Specifies the tag.
   ========= ================== ========= ==================

Description of field **resource_tag**

+-----------------+-----------------+-----------------+---------------------------------------------------------------------+
| Name            | Type            | Mandatory       | Description                                                         |
+=================+=================+=================+=====================================================================+
| key             | String          | Yes             | Specifies the tag key.                                              |
|                 |                 |                 |                                                                     |
|                 |                 |                 | The parameter constraints are as follows:                           |
|                 |                 |                 |                                                                     |
|                 |                 |                 | -  Must be unique for a resource.                                   |
|                 |                 |                 | -  Cannot be left blank.                                            |
|                 |                 |                 | -  Can contain a maximum of 36 characters.                          |
|                 |                 |                 | -  Can contain only the following character types:                  |
|                 |                 |                 |                                                                     |
|                 |                 |                 |    -  Uppercase letters                                             |
|                 |                 |                 |    -  Lowercase letters                                             |
|                 |                 |                 |    -  Digits                                                        |
|                 |                 |                 |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------+-----------------+-----------------+---------------------------------------------------------------------+
| value           | String          | Yes             | Specifies the tag value.                                            |
|                 |                 |                 |                                                                     |
|                 |                 |                 | The parameter constraints are as follows:                           |
|                 |                 |                 |                                                                     |
|                 |                 |                 | -  Can contain a maximum of 43 characters.                          |
|                 |                 |                 | -  Can contain only the following character types:                  |
|                 |                 |                 |                                                                     |
|                 |                 |                 |    -  Uppercase letters                                             |
|                 |                 |                 |    -  Lowercase letters                                             |
|                 |                 |                 |    -  Digits                                                        |
|                 |                 |                 |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------+-----------------+-----------------+---------------------------------------------------------------------+

Response Message
----------------

None

Example
-------

-  Example Request

.. code-block:: text

   POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags
   {
       "tag": {
           "key": "key1",
           "value": "value1"
       }
   }

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
