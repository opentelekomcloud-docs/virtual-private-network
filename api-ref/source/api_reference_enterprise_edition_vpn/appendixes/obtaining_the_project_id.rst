:original_name: vpn_api_0051.html

.. _vpn_api_0051:

.. _en-us_topic_0000001807530332:

Obtaining the Project ID
========================

Scenario
--------

A project ID is required by some URLs used for calling APIs. You can obtain the project ID using either of the following methods:

-  Obtaining the project ID by calling an API
-  Obtaining the project ID from the console

Obtaining the Project ID by Calling an API
------------------------------------------

You can obtain the project ID by calling the API used to query project information.

The API for obtaining the project ID is **GET https://{IAM endpoint}/v3/projects**. For details about API authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

The following is an example response. The value of **id** is the project ID.

::

   {
       "projects": [
           {
               "domain_id": "65382450e8f64ac0870cd180d14e684b",
               "is_domain": false,
               "parent_id": "65382450e8f64ac0870cd180d14e684b",
               "name": "project_name",
               "description": "",
               "links": {
                   "next": null,
                   "previous": null,
                   "self": "https://www.example.com/v3/projects/a4a5d4098fb4474fa22cd05f897d6b99"
               },
               "id": "a4a5d4098fb4474fa22cd05f897d6b99",
               "enabled": true
           }
       ],
       "links": {
           "next": null,
           "previous": null,
           "self": "https://www.example.com/v3/projects"
       }
   }

Obtaining the Project ID from the Console
-----------------------------------------

Perform the following operations:

#. Log in to the management console.

#. Click your username in the upper right corner, and choose **My Credentials**.

   On the **API Credentials** page, view the project ID in the project list.
