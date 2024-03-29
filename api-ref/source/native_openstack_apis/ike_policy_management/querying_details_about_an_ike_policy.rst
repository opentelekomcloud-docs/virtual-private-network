:original_name: en_topic_0093011511.html

.. _en_topic_0093011511:

Querying Details About an IKE Policy
====================================

**Function**
------------

This interface is used to query details about an IKE policy.

URI
---

GET /v2.0/vpn/ikepolicies/{ikepolicy_id}

.. table:: **Table 1** Parameter description

   ============ ====== ========= ============================
   Parameter    Type   Mandatory Description
   ============ ====== ========= ============================
   ikepolicy_id String Yes       Specifies the IKE policy ID.
   ============ ====== ========= ============================

Request Message
---------------

None

Response Message
----------------

:ref:`Table 2 <en_topic_0093011511__table20119003>` describes the response parameters.

.. _en_topic_0093011511__table20119003:

.. table:: **Table 2** Response parameters

   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter               | Type                  | Description                                                                                                                                                           |
   +=========================+=======================+=======================================================================================================================================================================+
   | ikepolicy               | Object                | Specifies the IKE policy object.                                                                                                                                      |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description             | String                | Provides supplementary information about the IKE policy.                                                                                                              |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id               | String                | Specifies the project ID.                                                                                                                                             |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | auth_algorithm          | String                | Specifies the authentication hash algorithm. The value can be **md5**, **sha1**, **sha2-256**, **sha2-384**, or **sha2-512**.                                         |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                    | String                | Specifies the IKE policy name.                                                                                                                                        |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | encryption_algorithm    | String                | Specifies the encryption algorithm. The value can be **3des**, **aes-128**, **aes-192**, or **aes-256**. The default value is **aes-128**.                            |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | pfs                     | String                | Specifies the PFS. The value can be **group1**, **group2**, **group5**, **group14**, **group15**, **group16**, **group19**, **group20**, **group21**, or **disable**. |
   |                         |                       |                                                                                                                                                                       |
   |                         |                       | The default value is **group5**.                                                                                                                                      |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | value                   | Integer               | Specifies the lifetime value of the SA. The default unit is **seconds**. The default value is **3600**.                                                               |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | phase1_negotiation_mode | String                | Specifies the IKE mode The default value is **main**.                                                                                                                 |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | units                   | String                | Specifies the lifecycle unit. The default value is **seconds**.                                                                                                       |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lifetime                | Object                | Specifies the lifetime object of SA.                                                                                                                                  |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                      | String                | Specifies the IKE policy ID.                                                                                                                                          |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ike_version             | String                | Specifies the IKE version number. The value can be **v1** or **v2**. The default value is **v1**.                                                                     |
   +-------------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/vpn/ikepolicies/{ikepolicy_id}

-  Example Response

   .. code-block::

      {
        "ikepolicy" : {
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
        }
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
