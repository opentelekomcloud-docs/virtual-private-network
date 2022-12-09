:original_name: en_topic_0093011518.html

.. _en_topic_0093011518:

Querying VPN Endpoint Groups
============================

**Function**
------------

This interface is used to query VPN endpoint groups.

URI
---

GET /v2.0/vpn/endpoint-groups

Request Message
---------------

:ref:`Table 1 <en_topic_0093011518__en-us_topic_0053740015_table20501377>` describes the request parameters.

.. _en_topic_0093011518__en-us_topic_0053740015_table20501377:

.. table:: **Table 1** Request parameters

   +-----------+--------+-----------+--------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Mandatory | Description                                                                                                  |
   +===========+========+===========+==============================================================================================================+
   | fields    | String | No        | Controls which parameters are returned. If this parameter is not specified, all parameters will be returned. |
   +-----------+--------+-----------+--------------------------------------------------------------------------------------------------------------+

.. note::

   The **project_id** parameter is not supported.

Response Message
----------------

:ref:`Table 2 <en_topic_0093011518__en-us_topic_0053740015_table34728767>` describes the response parameters.

.. _en_topic_0093011518__en-us_topic_0053740015_table34728767:

.. table:: **Table 2** Response parameters

   +-------------+--------+--------------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                                    |
   +=============+========+================================================================================+
   | description | String | Provides supplementary information about the VPN endpoint group.               |
   +-------------+--------+--------------------------------------------------------------------------------+
   | tenant_id   | String | Specifies the project ID.                                                      |
   +-------------+--------+--------------------------------------------------------------------------------+
   | endpoints   | List   | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +-------------+--------+--------------------------------------------------------------------------------+
   | type        | String | Specifies the endpoint type. The value can be **subnet** or **cidr**.          |
   +-------------+--------+--------------------------------------------------------------------------------+
   | id          | String | Specifies the VPN endpoint group ID.                                           |
   +-------------+--------+--------------------------------------------------------------------------------+
   | name        | String | Specifies the VPN endpoint group name.                                         |
   +-------------+--------+--------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/vpn/endpoint-groups

-  Example Response

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

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
