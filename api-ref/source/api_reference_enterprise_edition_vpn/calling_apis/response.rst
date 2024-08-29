:original_name: vpn_api_0011.html

.. _vpn_api_0011:

Response
========

**Status Code**

After sending a request, you can receive a response, including a status code, response header, and response body.

A status code is a group of digits, ranging from 1xx to 5xx. It indicates the status of a response. For more information, see :ref:`Status Codes <en-us_topic_0000001807370508>`.

For example, if status code **201** is returned after you call the API for obtaining a user token, the request is successful.

**Response Header**

Like a request, a response also has a header, for example, **Content-Type**.

:ref:`Figure 1 <en-us_topic_0000001854089177__en-us_topic_0000001543673232_fig10238149134019>` shows the response header for the API used to obtain a user token. The **x-subject-token** field carries a user token. You can use this token to authenticate the calling of other APIs.

.. _en-us_topic_0000001854089177__en-us_topic_0000001543673232_fig10238149134019:

.. figure:: /_static/images/en-us_image_0000001594578277.png
   :alt: **Figure 1** Response header for the API used to obtain a user token

   **Figure 1** Response header for the API used to obtain a user token

**Response Body**

This part is optional. A response body is generally returned in a structured format (for example, JSON or XML), which is specified by **Content-Type** in the response header. It is used to transfer content other than the response header.

The following is part of a response body for the API used to obtain a user token.

::

   {
       "token": {
           "expires_at": "2022-09-10T06:52:13.855000Z",
           "methods": [
               "password"
           ],
           "catalog": [
               {
                   "endpoints": [
                       {
   ......

If an error occurs during API calling, an error code and an error message will be displayed. The following is an example of an error response body.

::

   {
       "error_msg": "The format of message is error",
       "error_code": "AS.0001"
   }

**error_code** specifies an error code, and **error_msg** describes the error.
