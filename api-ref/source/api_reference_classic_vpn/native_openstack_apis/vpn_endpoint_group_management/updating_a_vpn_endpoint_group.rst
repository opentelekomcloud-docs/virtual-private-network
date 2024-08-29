:original_name: vpn_api_1051.html

.. _vpn_api_1051:

Updating a VPN Endpoint Group
=============================

Function
--------

This API is used to update a VPN endpoint group.

URI
---

PUT /v2.0/vpn/endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   +-------------------+--------+-----------+---------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                 |
   +===================+========+===========+=============================================+
   | endpoint_group_id | String | Yes       | Specifies the ID of the VPN endpoint group. |
   +-------------------+--------+-----------+---------------------------------------------+

Request
-------

:ref:`Table 2 <en-us_topic_0000001807530392__en-us_topic_0000001591736533_en-us_topic_0053740031_table16221316>` describes the request parameters.

.. _en-us_topic_0000001807530392__en-us_topic_0000001591736533_en-us_topic_0053740031_table16221316:

.. table:: **Table 2** Request parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                      |
   +=================+=================+=================+==================================================================+
   | description     | String          | No              | Provides supplementary information about the VPN endpoint group. |
   |                 |                 |                 |                                                                  |
   |                 |                 |                 | The description can contain up to 255 characters.                |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------+
   | name            | String          | No              | Specifies the name of the VPN endpoint group.                    |
   |                 |                 |                 |                                                                  |
   |                 |                 |                 | The name can contain 1 to 64 characters.                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------+
   | endpoint_group  | Object          | Yes             | Specifies the endpoint group.                                    |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------+

.. note::

   Parameter **project_id** is not supported.

Response
--------

:ref:`Table 3 <en-us_topic_0000001807530392__en-us_topic_0000001591736533_en-us_topic_0053740031_table45411103>` describes the response parameters.

.. _en-us_topic_0000001807530392__en-us_topic_0000001591736533_en-us_topic_0053740031_table45411103:

.. table:: **Table 3** Response parameters

   +----------------+--------+--------------------------------------------------------------------------------+
   | Parameter      | Type   | Description                                                                    |
   +================+========+================================================================================+
   | description    | String | Provides supplementary information about the VPN endpoint group.               |
   +----------------+--------+--------------------------------------------------------------------------------+
   | tenant_id      | String | Specifies the project ID.                                                      |
   +----------------+--------+--------------------------------------------------------------------------------+
   | endpoints      | List   | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +----------------+--------+--------------------------------------------------------------------------------+
   | type           | String | Specifies the endpoint type, which can be **subnet** or **cidr**.              |
   +----------------+--------+--------------------------------------------------------------------------------+
   | id             | String | Specifies the ID of the VPN endpoint group.                                    |
   +----------------+--------+--------------------------------------------------------------------------------+
   | name           | String | Provides supplementary information about the VPN endpoint group.               |
   +----------------+--------+--------------------------------------------------------------------------------+
   | endpoint_group | Object | Specifies the object of the VPN endpoint group.                                |
   +----------------+--------+--------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      PUT /v2.0/vpn/endpoint-groups/{endpoint_group_id}
      {
        "endpoint_group" : {
          "description" : "New description"
        }
      }

-  Example response

   .. code-block::

      {
        "endpoint_group" : {
          "description" : "New description",
          "tenant_id" : "4ad57e7ce0b24fca8f12b9834d91079d",
          "endpoints" : [ "10.2.0.0/24", "10.3.0.0/24" ],
          "type" : "cidr",
          "id" : "6ecd9cf3-ca64-46c7-863f-f2eb1b9e838a",
          "name" : "peers"
        }
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
