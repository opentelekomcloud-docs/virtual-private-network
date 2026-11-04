:original_name: vpn_api_0153.html

.. _vpn_api_0153:

Upgrading a VPN Gateway
=======================

Function
--------

This API is used to upgrade a VPN gateway.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

POST /v5/{project_id}/vpn-gateways/{vgw_id}/upgrade

.. table:: **Table 1** Parameters in a request

   ========== ====== ===========================================
   Parameter  Type   Description
   ========== ====== ===========================================
   project_id String Specifies a project ID.
   vgw_id     String Specifies the ID of a VPN gateway instance.
   ========== ====== ===========================================

Request
-------

-  Request parameters

   .. table:: **Table 2** UpgradeRequestBody

      +-----------------+-----------------+-----------------+------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                        |
      +=================+=================+=================+====================================+
      | action          | String          | Yes             | -  Specifies an upgrade operation. |
      |                 |                 |                 | -  Value range:                    |
      |                 |                 |                 |                                    |
      |                 |                 |                 |    -  start                        |
      |                 |                 |                 |    -  finish                       |
      |                 |                 |                 |    -  rollback                     |
      +-----------------+-----------------+-----------------+------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v5/{project_id}/vpn-gateways/{vgw_id}/upgrade

      {
          "action": "start"
      }

Response
--------

-  Response parameters

   Returned status code 202: successful operation

   .. table:: **Table 3** Parameters in the response body

      ========== ====== =======================
      Parameter  Type   Description
      ========== ====== =======================
      job_id     String Specifies a task ID.
      request_id String Specifies a request ID.
      ========== ====== =======================

-  Example response

   .. code-block::

      {
          "job_id": "c7f1d3e3-0476-4a71-95a7-3ce8cbb969de",
          "request_id": "73f072d8-demo-a8df-va86-2a755d95636f"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
