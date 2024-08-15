:original_name: vpn_api_1049.html

.. _vpn_api_1049:

Querying Details About a VPN Endpoint Group
===========================================

Function
--------

This API is used to query details about a VPN endpoint group.

URI
---

GET /v2.0/vpn/endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   +-------------------+--------+-----------+---------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                 |
   +===================+========+===========+=============================================+
   | endpoint_group_id | String | Yes       | Specifies the ID of the VPN endpoint group. |
   +-------------------+--------+-----------+---------------------------------------------+

Request
-------

None

Response
--------

:ref:`Table 2 <en-us_topic_0000001854169233__en-us_topic_0000001591896521_en-us_topic_0053740027_table58761073>` describes the response parameters.

.. _en-us_topic_0000001854169233__en-us_topic_0000001591896521_en-us_topic_0053740027_table58761073:

.. table:: **Table 2** Response parameters

   +----------------+--------+--------------------------------------------------------------------------------+
   | Parameter      | Type   | Description                                                                    |
   +================+========+================================================================================+
   | description    | Object | Provides supplementary information about the VPN endpoint group.               |
   +----------------+--------+--------------------------------------------------------------------------------+
   | tenant_id      | String | Specifies the project ID.                                                      |
   +----------------+--------+--------------------------------------------------------------------------------+
   | endpoints      | List   | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +----------------+--------+--------------------------------------------------------------------------------+
   | type           | String | Specifies the endpoint type, which can be **subnet** or **cidr**.              |
   +----------------+--------+--------------------------------------------------------------------------------+
   | id             | String | Specifies the ID of the VPN endpoint group.                                    |
   +----------------+--------+--------------------------------------------------------------------------------+
   | name           | String | Specifies the name of the VPN endpoint group.                                  |
   +----------------+--------+--------------------------------------------------------------------------------+
   | endpoint_group | Object | Specifies the object of the VPN endpoint group.                                |
   +----------------+--------+--------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v2.0/vpn/endpoint-groups/{endpoint_group_id}

-  Example response

   .. code-block::

      {
          "endpoint_group": {
              "description": "",
              "tenant_id": "4ad57e7ce0b24fca8f12b9834d91079d",
              "endpoints": [
                  "10.2.0.0/24",
                  "10.3.0.0/24"
              ],
              "type": "cidr",
              "id": "6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a",
              "name": "peers"
          }
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
