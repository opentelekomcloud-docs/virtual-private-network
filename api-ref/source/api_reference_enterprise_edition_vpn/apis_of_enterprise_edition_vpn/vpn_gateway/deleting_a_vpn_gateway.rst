:original_name: vpn_api_0018.html

.. _vpn_api_0018:

Deleting a VPN Gateway
======================

Function
--------

This API is used to delete a VPN gateway with a specified gateway ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

DELETE /v5/{project_id}/vpn-gateways/{vgw_id}

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | vgw_id     | String | Yes       | Specifies the ID of a VPN gateway instance.                                                                                           |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/vpn-gateways/{vgw_id}

Response
--------

-  Response parameters

   Returned status code 204: successful deletion

-  Example response

   Response returned when a VPN gateway being created fails to be deleted

   .. code-block::

      {
          "error_code":"VPN.0003",
          "error_msg":"resource (type=GATEWAY, ID=ff9bdca6-demo-a8df-va86-e4bcc1ea52bc) is not ready, currently CREATING",
          "request_id": "1d94a4e8-fdc2-7bfd-943e-19bfa9b234ac"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
