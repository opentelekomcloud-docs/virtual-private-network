:original_name: vpn_api_1050.html

.. _vpn_api_1050:

Querying VPN Endpoint Groups
============================

Function
--------

This API is used to query VPN endpoint groups.

URI
---

GET /v2.0/vpn/endpoint-groups

Request
-------

:ref:`Table 1 <en-us_topic_0000001854089285__en-us_topic_0000001591736529_en-us_topic_0053740015_table20501377>` describes the request parameter.

.. _en-us_topic_0000001854089285__en-us_topic_0000001591736529_en-us_topic_0053740015_table20501377:

.. table:: **Table 1** Request parameter

   +-----------+--------+-----------+--------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Mandatory | Description                                                                                                  |
   +===========+========+===========+==============================================================================================================+
   | fields    | String | No        | Controls which parameters are returned. If this parameter is not specified, all parameters will be returned. |
   +-----------+--------+-----------+--------------------------------------------------------------------------------------------------------------+

.. note::

   Parameter **project_id** is not supported.

Response
--------

:ref:`Table 2 <en-us_topic_0000001854089285__en-us_topic_0000001591736529_en-us_topic_0053740015_table34728767>` describes the response parameters.

.. _en-us_topic_0000001854089285__en-us_topic_0000001591736529_en-us_topic_0053740015_table34728767:

.. table:: **Table 2** Response parameters

   +-----------------+--------------+--------------------------------------------------------------------------------+
   | Parameter       | Type         | Description                                                                    |
   +=================+==============+================================================================================+
   | description     | String       | Provides supplementary information about the VPN endpoint group.               |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | tenant_id       | String       | Specifies the project ID.                                                      |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | endpoints       | List         | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | type            | String       | Specifies the endpoint type, which can be **subnet** or **cidr**.              |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | id              | String       | Specifies the ID of the VPN endpoint group.                                    |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | name            | String       | Specifies the name of the VPN endpoint group.                                  |
   +-----------------+--------------+--------------------------------------------------------------------------------+
   | endpoint_groups | List<Object> | Specifies the object of the VPN endpoint groups.                               |
   +-----------------+--------------+--------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v2.0/vpn/endpoint-groups

-  Example response

   .. code-block::

      {
          "endpoint_groups": [
              {
                  "description": "",
                  "tenant_id": "4ad57e7ce0b24fca8f12b9834d91079d",
                  "endpoints": [
                      "a3da778c-adfb-46db-88b3-d2ce53290a89"
                  ],
                  "type": "subnet",
                  "id": "6bf34c7c-864c-4948-a6d4-db791669f9d4",
                  "name": "locals"
              },
              {
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
          ]
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
