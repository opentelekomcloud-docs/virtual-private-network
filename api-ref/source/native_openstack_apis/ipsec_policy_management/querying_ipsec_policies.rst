:original_name: en_topic_0093011506.html

.. _en_topic_0093011506:

Querying IPsec Policies
=======================

**Function**
------------

This interface is used to query IPsec policies.

URI
---

GET /v2.0/vpn/ipsecpolicies

Request Message
---------------

:ref:`Table 1 <en_topic_0093011506__table47787675>` describes the request parameters.

.. _en_topic_0093011506__table47787675:

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

:ref:`Table 2 <en_topic_0093011506__table3957675>` describes the response parameters.

.. _en_topic_0093011506__table3957675:

.. table:: **Table 2** Response parameters

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                           |
   +=======================+=======================+=======================================================================================================================================================================+
   | transform_protocol    | String                | Specifies the transform protocol used. The value can be **esp**, **ah**, or **ah-esp**. The default value is **esp**.                                                 |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                                             |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | String                | Specifies the IPsec policy ID.                                                                                                                                        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | encapsulation_mode    | String                | Specifies the encapsulation mode. The default value is **tunnel**.                                                                                                    |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | pfs                   | String                | Specifies the PFS. The value can be **group1**, **group2**, **group5**, **group14**, **group15**, **group16**, **group19**, **group20**, **group21**, or **disable**. |
   |                       |                       |                                                                                                                                                                       |
   |                       |                       | The default value is **group5**.                                                                                                                                      |
   |                       |                       |                                                                                                                                                                       |
   |                       |                       | The value **disable** indicates that the PFS function is disabled.                                                                                                    |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lifetime              | Object                | Specifies the lifetime object of SA.                                                                                                                                  |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the IPsec policy name.                                                                                                                                      |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | auth_algorithm        | String                | Specifies the authentication hash algorithm. The value can be **md5**, **sha1**, **sha2-256**, **sha2-384**, or **sha2-512**.                                         |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the IPsec policy.                                                                                                            |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ipsecpolicies         | List<Object>          | Specifies the IPsec policy list.                                                                                                                                      |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | encryption_algorithm  | String                | Specifies the encryption algorithm. The value can be **3des**, **aes-128**, **aes-192**, or **aes-256**. The default value is **aes-128**.                            |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                 | Integer               | Specifies the lifetime value of the SA. The default unit is **seconds.** The default value is **3600**.                                                               |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | units                 | String                | Specifies the lifecycle unit. The default value is **seconds**.                                                                                                       |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/vpn/ipsecpolicies

-  Example Response

   .. code-block::

      {
        "ipsecpolicies" : [ {
          "name" : "ipsecpolicy1",
          "transform_protocol" : "esp",
          "auth_algorithm" : "sha1",
          "encapsulation_mode" : "tunnel",
          "encryption_algorithm" : "aes-128",
          "pfs" : "group14",
          "project_id" : "ccb81365fe36411a9011e90491fe1330",
          "tenant_id" : "ccb81365fe36411a9011e90491fe1330",
          "lifetime" : {
            "units" : "seconds",
            "value" : 3600
          },
          "id" : "5291b189-fd84-46e5-84bd-78f40c05d69c",
          "description" : ""
        } ]
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
