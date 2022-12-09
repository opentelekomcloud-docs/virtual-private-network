:original_name: en_topic_0093011519.html

.. _en_topic_0093011519:

Updating a VPN Endpoint Group
=============================

**Function**
------------

This interface is used to update a VPN endpoint group.

URI
---

PUT /v2.0/vpn/endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   ================= ====== ========= ====================================
   Parameter         Type   Mandatory Description
   ================= ====== ========= ====================================
   endpoint_group_id String No        Specifies the VPN endpoint group ID.
   ================= ====== ========= ====================================

Request Message
---------------

:ref:`Table 2 <en_topic_0093011519__en-us_topic_0053740031_table16221316>` describes the request parameters.

.. _en_topic_0093011519__en-us_topic_0053740031_table16221316:

.. table:: **Table 2** Request parameters

   +-------------+--------+-----------+------------------------------------------------------------------+
   | Parameter   | Type   | Mandatory | Description                                                      |
   +=============+========+===========+==================================================================+
   | description | String | No        | Provides supplementary information about the VPN endpoint group. |
   +-------------+--------+-----------+------------------------------------------------------------------+
   | name        | String | No        | Specifies the VPN endpoint group name.                           |
   +-------------+--------+-----------+------------------------------------------------------------------+

.. note::

   #. The **endpoint_group_id** parameter must be specified.
   #. The value of **name** can contain 1 to 64 characters.
   #. The value of **description** can contain a maximum of 255 characters.
   #. The **project_id** parameter is not supported.

Response Message
----------------

:ref:`Table 3 <en_topic_0093011519__en-us_topic_0053740031_table45411103>` describes the response parameters.

.. _en_topic_0093011519__en-us_topic_0053740031_table45411103:

.. table:: **Table 3** Response parameters

   +-------------+------+--------------------------------------------------------------------------------+
   | Parameter   | Type | Description                                                                    |
   +=============+======+================================================================================+
   | description | Yes  | Provides supplementary information about the VPN endpoint group.               |
   +-------------+------+--------------------------------------------------------------------------------+
   | tenant_id   | Yes  | Specifies the project ID.                                                      |
   +-------------+------+--------------------------------------------------------------------------------+
   | endpoints   | Yes  | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +-------------+------+--------------------------------------------------------------------------------+
   | type        | Yes  | Specifies the endpoint type. The value can be **subnet** or **cidr**.          |
   +-------------+------+--------------------------------------------------------------------------------+
   | id          | Yes  | Specifies the VPN endpoint group ID.                                           |
   +-------------+------+--------------------------------------------------------------------------------+
   | name        | Yes  | Provides supplementary information about the VPN endpoint group.               |
   +-------------+------+--------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      PUT /v2.0/vpn/endpoint-groups/{endpoint_group_id}
      {
        "endpoint_group" : {
          "description" : "New description"
        }
      }

-  Example Response

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

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
