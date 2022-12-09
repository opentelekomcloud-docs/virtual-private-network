:original_name: en_topic_0093011516.html

.. _en_topic_0093011516:

Creating a VPN Endpoint Group
=============================

**Function**
------------

This interface is used to create a VPN endpoint group.

URI
---

POST /v2.0/vpn/endpoint-groups

Request Message
---------------

:ref:`Table 1 <en_topic_0093011516__en-us_topic_0053740037_table31025868>` describes the request parameters.

.. _en_topic_0093011516__en-us_topic_0053740037_table31025868:

.. table:: **Table 1** Request parameters

   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | Parameter   | Type         | Mandatory | Description                                                                    |
   +=============+==============+===========+================================================================================+
   | endpoints   | List<String> | Yes       | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | type        | String       | Yes       | Specifies the endpoint type. The value can be **subnet** or **cidr**.          |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | name        | String       | No        | Specifies the VPN endpoint group name.                                         |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | tenant_id   | String       | No        | Specifies the project ID.                                                      |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | description | String       | No        | Provides supplementary information about the VPN endpoint group.               |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+

.. note::

   #. The **project_id** parameter is not supported.
   #. The value of **tenant_id** can contain a maximum of 255 characters.
   #. The value of **name** can contain 1 to 64 characters.
   #. The value of **description** can contain a maximum of 255 characters.
   #. The value of **type** can only be **subnet** or **cidr**.

Response Message
----------------

:ref:`Table 2 <en_topic_0093011516__en-us_topic_0053740037_table50787128>` describes the response parameters.

.. _en_topic_0093011516__en-us_topic_0053740037_table50787128:

.. table:: **Table 2** Response parameters

   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | Parameter   | Type         | Mandatory | Description                                                                    |
   +=============+==============+===========+================================================================================+
   | description | String       | No        | Provides supplementary information about the VPN endpoint group.               |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | tenant_id   | String       | Yes       | Specifies the project ID.                                                      |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | endpoints   | List<String> | Yes       | Specifies the endpoint list. The endpoints in a list must be of the same type. |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | type        | String       | Yes       | Specifies the endpoint type. The value can be **subnet** or **cidr**.          |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | id          | String       | Yes       | Specifies the VPN endpoint group ID.                                           |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+
   | name        | String       | No        | Specifies the VPN endpoint group name.                                         |
   +-------------+--------------+-----------+--------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      POST /v2.0/vpn/endpoint-groups
      {
        "endpoint_group" : {
          "endpoints" : [ "10.2.0.0/24", "10.3.0.0/24" ],
          "type" : "cidr",
          "name" : "peers"
        }
      }

-  Example Response

   .. code-block::

      {
        "endpoint_group" : {
          "description" : "",
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
