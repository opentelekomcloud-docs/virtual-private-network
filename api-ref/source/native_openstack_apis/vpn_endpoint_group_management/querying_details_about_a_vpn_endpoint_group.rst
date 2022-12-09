:original_name: en_topic_0093011517.html

.. _en_topic_0093011517:

Querying Details About a VPN Endpoint Group
===========================================

**Function**
------------

This interface is used to query details about a VPN endpoint group.

URI
---

GET /v2.0/vpn/endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   ================= ====== ========= ====================================
   Parameter         Type   Mandatory Description
   ================= ====== ========= ====================================
   endpoint_group_id String No        Specifies the VPN endpoint group ID.
   ================= ====== ========= ====================================

Request Message
---------------

None

Response Message
----------------

:ref:`Table 2 <en_topic_0093011517__en-us_topic_0053740027_table58761073>` describes the response parameters.

.. _en_topic_0093011517__en-us_topic_0053740027_table58761073:

.. table:: **Table 2** Response parameters

   +-------------+--------+--------------------------------------------------------------------------------+
   | Parameter   | Type   | Description                                                                    |
   +=============+========+================================================================================+
   | description | Object | Provides supplementary information about the VPN endpoint group.               |
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

      GET /v2.0/vpn/endpoint-groups/{endpoint_group_id}

-  Example Response

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

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
