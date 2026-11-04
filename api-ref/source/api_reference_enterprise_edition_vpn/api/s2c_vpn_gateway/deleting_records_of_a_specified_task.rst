:original_name: vpn_api_0155.html

.. _vpn_api_0155:

Deleting Records of a Specified Task
====================================

Function
--------

This API is used to delete records of a task with a specified ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

DELETE /v5/{project_id}/vpn-gateways/jobs/{job_id}

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | job_id     | String | Yes       | Specifies a task ID.                                                                                                                  |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/vpn-gateways/jobs/{job_id}

Response
--------

-  Response parameters

   Returned status code 204: successful deletion

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
