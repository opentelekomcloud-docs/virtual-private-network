:original_name: vpn_api_0009.html

.. _vpn_api_0009:

Request
=======

This section describes the structure of a REST API request, and uses the IAM API for creating an IAM user as an administrator as an example to demonstrate how to call an API. The user token obtained by this API can then be used to authenticate the calling of other APIs.

**Request URI**

A request URI is in the following format:

**{URI-scheme}://{Endpoint}/{resource-path}?{query-string}**

Although a request URI is included in the request header, most programming languages or frameworks require the request URI to be separately transmitted.

.. table:: **Table 1** Parameters in a URI

   +---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter     | Description                                                                                                                                                                                                                                                            |
   +===============+========================================================================================================================================================================================================================================================================+
   | URI-scheme    | Protocol used to transmit requests. All APIs use HTTPS.                                                                                                                                                                                                                |
   +---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Endpoint      | Domain name or IP address of the server bearing the REST service. The endpoint varies between services in different regions.                                                                                                                                           |
   +---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | resource-path | Resource path of an API. Obtain the path from the URI of an API. For example, the **resource-path** of the API for obtaining a user token is **/v3/auth/tokens**.                                                                                                      |
   +---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | query-string  | (Optional) Query parameter. Ensure that a question mark (?) is included in front of each query parameter, which is in the format of *Parameter name*\ **=**\ *Parameter value*. For example, **?limit=10** indicates that a maximum of 10 data records can be queried. |
   +---------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. note::

   To simplify the URI display, this document provides only the **resource-path** and request method in the URI of each API. The **URI-scheme** of all APIs is **https**, and the endpoints in a region are the same.

**Request Methods**

The HTTP protocol defines the following request methods for sending requests to a server.

.. table:: **Table 2** HTTP methods

   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | Method                            | Description                                                                                        |
   +===================================+====================================================================================================+
   | GET                               | Requests a server to return specified resources.                                                   |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | PUT                               | Requests a server to update specified resources.                                                   |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | POST                              | Requests a server to add resources or perform special operations.                                  |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | DELETE                            | Requests a server to delete a specified resource (for example, an object).                         |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | HEAD                              | Requests resource headers from a server.                                                           |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+
   | PATCH                             | Requests a server to update part of specified resources.                                           |
   |                                   |                                                                                                    |
   |                                   | If the requested resource does not exist, the server may create a resource using the PATCH method. |
   +-----------------------------------+----------------------------------------------------------------------------------------------------+

For example, in the URI used to obtain a user token, the request method is POST. The request is as follows:

.. code-block::

   POST https://iam.eu-de.docs.otc.t-systems.com/v3.0/OS-USER/users
   POST https://iam.eu-de.otc.t-systems.com/v3/auth/tokens

**Request Header**

You can add additional fields, such as the fields required by a specified URI or HTTP method, to a request header. For example, to request authentication information, you can add **Content-Type** to specify the type of the request body.

For details about common request headers, see :ref:`Table 3 <en-us_topic_0000002441716421__en-us_topic_0000002430499185_table1510219261292>`.

.. _en-us_topic_0000002441716421__en-us_topic_0000002430499185_table1510219261292:

.. table:: **Table 3** Common fields in request headers

   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | Parameter       | Description                                                                                                                                                                                                                                                                     | Mandatory                                                                                                                           | Example                                    |
   +=================+=================================================================================================================================================================================================================================================================================+=====================================================================================================================================+============================================+
   | Host            | Specifies the server to which a request is sent, which can be obtained from the URL of the service API. The value is in the format of *Host name:Port number*. If the port number is not specified, the default port is used. The default port number for **https** is **443**. | No                                                                                                                                  | code.test.com                              |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     |                                            |
   |                 |                                                                                                                                                                                                                                                                                 | This field is mandatory for access key (AK)/secret access key (SK) authentication.                                                  | or                                         |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     |                                            |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     | code.test.com:443                          |
   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | Content-Type    | Specifies the type (or format) of a message body. The default value *application/json* is recommended. Other values will be described in the specific APIs.                                                                                                                     | Yes                                                                                                                                 | application/json                           |
   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | Content-Length  | Specifies the length of a request body, in bytes.                                                                                                                                                                                                                               | No                                                                                                                                  | 3495                                       |
   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | X-Project-Id    | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`.                                                                                                                                           | No                                                                                                                                  | e9993fc7************baa340f9c0f4           |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     |                                            |
   |                 |                                                                                                                                                                                                                                                                                 | This field is mandatory for requests that use AK/SK authentication in the Dedicated Cloud (DeC) scenario or multi-project scenario. |                                            |
   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | X-Auth-Token    | Specifies a user token.                                                                                                                                                                                                                                                         | No                                                                                                                                  | The following is part of an example token: |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     |                                            |
   |                 | A user token is carried in a response to the API for obtaining a user token. This API is the only one that does not require authentication.                                                                                                                                     | This field is mandatory for token authentication.                                                                                   | MIIPAgYJKoZIhvcNAQcCo...ggg1BBIINPXsidG9rZ |
   |                 |                                                                                                                                                                                                                                                                                 |                                                                                                                                     |                                            |
   |                 | The value of **X-Subject-Token** in the response header is the token.                                                                                                                                                                                                           |                                                                                                                                     |                                            |
   +-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+

.. note::

   APIs also support AK/SK authentication, which uses SDKs to sign a request. During the signature, the **Authorization** (signature authentication) and **X-Sdk-Date** (time when a request is sent) headers are automatically added to the request.

   For details about AK/SK authentication, see :ref:`Authentication <en-us_topic_0000001854169129>`.

The API for obtaining a user token does not require authentication. As such, only the **Content-Type** field needs to be added to the requests for calling this API. An example of such requests is as follows:

.. code-block::

   POST https://iam.eu-de.otc.t-systems.com/v3/auth/tokensContent-Type:application/json

**Request Body**

This part is optional. A request body is generally sent in a structured format (for example, JSON or XML), which is specified by **Content-Type** in the request header. It is used to transfer content other than the request header. If the request body contains full-width characters, these characters must be coded in UTF-8.

Request bodies vary according to APIs. Some APIs do not require a request body, such as the APIs called using the GET and DELETE methods.

For the API used to obtain a user token, you can obtain the request parameters and parameter description from the API request. The following provides an example request with a body included. Replace **username**, **domainname**, **\*******\*** (login password), and **xxxxxxxxxxxxxxxxxx** (project name, for example, **eu-de-01**) with the actual values.

.. note::

   The **scope** field specifies where a token takes effect. In the following example, the token takes effect only for the resources in a specified project. You can set **scope** to an account or a project under an account. In the following example, the token takes effect only in a specified project.

.. code-block:: text

   POST https://iam.eu-de.otc.t-systems.com/v3/auth/tokensContent-Type:application/json
   POST https://iam.eu-de.otc.t-systems.com/v3/auth/tokensContent-Type:application/json
   {
       "auth":{
           "identity":{
               "methods":[
                   "password"
               ],
               "password":{
                   "user":{
                       "name":"username",
                       "password":"********",
                       "domain":{
                           "name":"domainname"
                       }
                   }
               }
           },
           "scope":{
               "project":{
                   "name":"xxxxxxxxxxxxxxxxxx"
               }
           }
       }
   }

If all data required by an API request is available, you can send the request to call the API through `curl <https://curl.haxx.se/>`__, `Postman <https://www.getpostman.com/>`__, or coding. In the response to the API for obtaining a user token, **x-subject-token** carries a user token. You can use this token to authenticate the calling of other APIs.
