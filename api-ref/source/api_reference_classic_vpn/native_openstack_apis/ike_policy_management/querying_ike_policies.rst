:original_name: vpn_api_1044.html

.. _vpn_api_1044:

Querying IKE Policies
=====================

Function
--------

This API is used to query IKE policies.

URI
---

GET /v2.0/vpn/ikepolicies

Request
-------

:ref:`Table 1 <en-us_topic_0000001807370556__en-us_topic_0000001591896537_table61502840>` describes the request parameter.

.. _en-us_topic_0000001807370556__en-us_topic_0000001591896537_table61502840:

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

:ref:`Table 2 <en-us_topic_0000001807370556__en-us_topic_0000001591896537_table49507636>` describes the response parameters.

.. _en-us_topic_0000001807370556__en-us_topic_0000001591896537_table49507636:

.. table:: **Table 2** Response parameters

   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Type                  | Description                                                                                                                                                       |
   +=========================+=======================+===================================================================================================================================================================+
   | ikepolicies             | List<Object>          | Specifies the IKE policy list.                                                                                                                                    |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description             | String                | Provides supplementary information about the IKE policy.                                                                                                          |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id               | String                | Specifies the project ID.                                                                                                                                         |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | auth_algorithm          | String                | Specifies the authentication hash algorithm, which can be **md5**, **sha1**, **sha2-256**, **sha2-384**, or **sha2-512**.                                         |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                    | String                | Specifies the IKE policy name.                                                                                                                                    |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | encryption_algorithm    | String                | Specifies the encryption algorithm, which can be **3des**, **aes-128**, **aes-192**, or **aes-256**. The default algorithm is **aes-128**.                        |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | pfs                     | String                | Specifies the PFS, which can be **group1**, **group2**, **group5**, **group14**, **group15**, **group16**, **group19**, **group20**, **group21**, or **disable**. |
   |                         |                       |                                                                                                                                                                   |
   |                         |                       | The default PFS is **group5**.                                                                                                                                    |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                   | Integer               | Specifies the lifetime value of the SA, which is **3600** by default. The default unit is **seconds**.                                                            |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | phase1_negotiation_mode | String                | Specifies the IKE mode, which is **main** by default.                                                                                                             |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | units                   | String                | Specifies the lifecycle unit, which is **seconds** by default.                                                                                                    |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lifetime                | Object                | Specifies the lifetime object of SA.                                                                                                                              |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                      | String                | Specifies the IKE policy ID.                                                                                                                                      |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ike_version             | String                | Specifies the IKE version, which can be **v1** or **v2**. The default value is **v1**.                                                                            |
   +-------------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      GET /v2.0/vpn/ikepolicies

-  Example response

   .. code-block::

      {
        "ikepolicies" : [ {
          "name" : "ikepolicy1",
          "tenant_id" : "ccb81365fe36411a9011e90491fe1330",
          "auth_algorithm" : "sha1",
          "encryption_algorithm" : "aes-256",
          "pfs" : "group5",
          "phase1_negotiation_mode" : "main",
          "lifetime" : {
            "units" : "seconds",
            "value" : 3600
          },
          "ike_version" : "v1",
          "id" : "5522aff7-1b3c-48dd-9c3c-b50f016b73db",
          "description" : ""
        } ]
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
