:original_name: vpn_api_0010.html

.. _vpn_api_0010:

.. _en-us_topic_0000001854169129:

Authentication
==============

Requests for calling an API can be authenticated using either of the following methods:

-  Token authentication: Requests are authenticated using tokens.
-  AK/SK authentication: Requests are encrypted using AK/SK pairs. AK/SK authentication is recommended as it is more secure than token authentication.

**Token Authentication**

.. note::

   A token is valid for 24 hours. When using a token for authentication, cache it to avoid frequent calling.

A token is used to acquire temporary permissions. During API authentication using a token, the token is added to the request header to get permissions for calling the API. You can obtain a token by calling the API used to obtain a user token.

A cloud service can be deployed as either a project-level service or global service.

-  For a project-level service, you need to obtain a project-level token by setting **auth.scope** in the request body to **project**.
-  For a global service, you need to obtain a global token by setting **auth.scope** in the request body to **domain**.

A project-level token is required for calling APIs of the VPN service. As such, set **auth.scope** in the request body to **project** when you call the API for obtaining a user token.

::

   {
       "auth": {
           "identity": {
               "methods": [
                   "password"
               ],
               "password": {
                   "user": {
                       "name": "username",
                       "password": "********",
                       "domain": {
                           "name": "domainname"
                       }
                   }
               }
           },
           "scope": {
               "project": {
                   "name": "xxxxxxxx"
               }
           }
       }
   }

After obtaining a token, add the **X-Auth-Token** field specifying the token to the request header when calling other APIs. For example, when the token is **ABCDEFG....**, add **X-Auth-Token: ABCDEFG....** to the request header as follows:

.. code-block:: text

   POST https://iam.eu-de.otc.t-systems.com/v3/auth/tokens


   Content-Type: application/json
   X-Auth-Token: ABCDEFG....

**AK/SK Authentication**

.. note::

   AK/SK authentication supports API requests with a body size not larger than 12 MB. For API requests with larger sizes, use token authentication.

In AK/SK-based authentication, AK/SK is used to sign requests, and the signature is then added to the request header for authentication.

-  AK: access key, which is a unique identifier used together with an SK to sign requests cryptographically.
-  SK: secret access key, which is used together with an AK to sign requests cryptographically. It identifies a request sender and prevents the requests from being modified.

In AK/SK authentication, you can use an AK/SK to sign requests based on the signature algorithm or using the signing SDK.

.. note::

   Different from the SDKs provided by services, the signing SDK is used only for signing.
