:original_name: vpn_api_1018.html

.. _vpn_api_1018:

Creating Tags for a VPN
=======================

Function
--------

This API is used to create tags for a VPN.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags

.. note::

   In the URI, **project_id** indicates the project ID, and **resource_id** indicates the ID of the target resource.

Request
-------

:ref:`Table 1 <en-us_topic_0000001854089249__en-us_topic_0000001591841849_en-us_topic_0103470566_table14751112719406>` describes the request parameter.

.. _en-us_topic_0000001854089249__en-us_topic_0000001591841849_en-us_topic_0103470566_table14751112719406:

.. table:: **Table 1** Request parameter

   ========= ================== ========= ==================
   Parameter Type               Mandatory Description
   ========= ================== ========= ==================
   tag       List<resource_tag> Yes       Specifies the tag.
   ========= ================== ========= ==================

.. table:: **Table 2** Description of field **resource_tag**

   +-----------------+-----------------+-----------------+----------------------------------------------------+
   | Name            | Type            | Mandatory       | Description                                        |
   +=================+=================+=================+====================================================+
   | key             | String          | Yes             | Specifies the tag key.                             |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | The key                                            |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | -  Must be unique for a resource.                  |
   |                 |                 |                 | -  Cannot be left blank.                           |
   |                 |                 |                 | -  Can contain a maximum of 36 characters.         |
   |                 |                 |                 | -  Can contain only the following character types: |
   |                 |                 |                 |                                                    |
   |                 |                 |                 |    -  Uppercase letters                            |
   |                 |                 |                 |    -  Lowercase letters                            |
   |                 |                 |                 |    -  Digits                                       |
   |                 |                 |                 |    -  Hyphens (-) and underscores (_)              |
   +-----------------+-----------------+-----------------+----------------------------------------------------+
   | value           | String          | Yes             | Specifies the tag value.                           |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | The value                                          |
   |                 |                 |                 |                                                    |
   |                 |                 |                 | -  Can contain a maximum of 43 characters.         |
   |                 |                 |                 | -  Can contain only the following character types: |
   |                 |                 |                 |                                                    |
   |                 |                 |                 |    -  Uppercase letters                            |
   |                 |                 |                 |    -  Lowercase letters                            |
   |                 |                 |                 |    -  Digits                                       |
   |                 |                 |                 |    -  Hyphens (-) and underscores (_)              |
   +-----------------+-----------------+-----------------+----------------------------------------------------+

Response
--------

None

Example
-------

-  Example request

   .. code-block:: text

      POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags
      {
          "tag": {
              "key": "key1",
              "value": "value1"
          }
      }

-  Example response

   None

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
