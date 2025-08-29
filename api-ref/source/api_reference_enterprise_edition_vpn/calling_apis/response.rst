:original_name: vpn_api_0011.html

.. _vpn_api_0011:

Response
========

**Status Code**

After sending a request, you can receive a response, including a status code, response header, and response body.

A status code is a group of digits, ranging from 1xx to 5xx. It indicates the status of a response. For more information, see :ref:`Status Codes <en-us_topic_0000001807370508>`.

If status code 201 is returned after the API used to create an IAM user as an administrator is called, the request is successful.

**Response Header**

Like a request, a response also has a header, for example, **Content-Type**.

The response header shown in :ref:`Figure 1 <en-us_topic_0000001854089177__en-us_topic_0000001543673232_fig10238149134019>` is returned for the API used to create an IAM user as an administrator.

.. _en-us_topic_0000001854089177__en-us_topic_0000001543673232_fig10238149134019:

.. figure:: /_static/images/en-us_image_0000001594578277.png
   :alt: **Figure 1** Response header for the API used to create an IAM user as an administrator

   **Figure 1** Response header for the API used to create an IAM user as an administrator

**Response Body**

The response body is optional. A response body is generally returned in a structured format (for example, JSON or XML), which is specified by **Content-Type** in the response header. It is used to transfer content other than the response header.

The following provides part of the response body returned for the API used to create an IAM user as an administrator.

.. code-block::

   {
       "user": {
           "id": "c131886aec...",
           "name": "IAMUser",
           "description": "IAM User Description",
           "areacode": "",
           "phone": "",
           "email": "***@***.com",
           "status": null,
           "enabled": true,
           "pwd_status": false,
           "access_mode": "default",
           "is_domain_owner": false,
           "xuser_id": "",
           "xuser_type": "",
           "password_expires_at": null,
           "create_time": "2024-05-21T09:03:41.000000",
           "domain_id": "d78cbac1..........",
           "xdomain_id": "30086000........",
           "xdomain_type": "",
           "default_project_id": null
       }
   }

If an error occurs during API calling, an error code and an error message will be displayed. The following is an example of an error response body.

.. code-block::

   {
       "error_msg": "Request body is invalid.",
       "error_code": "IAM.0011"
   }

**error_code** specifies an error code, and **error_msg** describes the error.
