:original_name: vpn_api_0025.html

.. _vpn_api_0025:

Deleting a Customer Gateway
===========================

Function
--------

This API is used to delete a customer gateway with a specified gateway ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

DELETE /v5/{project_id}/customer-gateways/{customer_gateway_id}

.. table:: **Table 1** Parameter description

   +---------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Type   | Mandatory | Description                                                                                                                           |
   +=====================+========+===========+=======================================================================================================================================+
   | project_id          | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +---------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | customer_gateway_id | String | Yes       | Specifies a customer gateway ID.                                                                                                      |
   +---------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/customer-gateways/{customer_gateway_id}

Response
--------

-  Response parameters

   Returned status code 204: successful deletion

-  Example response

   Response returned when a customer gateway that has been created and has VPN connections fails to be deleted

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/customer-gateways/{customer_gateway_id}
      {
          "error_code": "VPN.0001",
          "error_msg": "invalid request: customer gateway 575c1722-demo-a8df-va86-dd7f41876332 has connection",
          "request_id": "c923ac44-1890-48d5-a004-5be6432cf361"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
