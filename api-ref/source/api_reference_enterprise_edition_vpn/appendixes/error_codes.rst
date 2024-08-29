:original_name: vpn_api_0067.html

.. _vpn_api_0067:

Error Codes
===========

Description
-----------

If an error occurs when an API is called, error information is returned. This section describes the error information for VPN APIs (excluding native OpenStack APIs).

Response Format
---------------

.. code-block::

   {
       "code": "VPN.0001",
       "message": "invalid request:xxx"
   }

Error Code Description
----------------------

+--------+-------------+------------+----------------------------+---------------------------------+-------------------------------------------------------------------------------------------+
| Module | Status Code | Error Code | Error Information          | Description                     | Handling Measure                                                                          |
+========+=============+============+============================+=================================+===========================================================================================+
| Common | 400         | VPN.0001   | invalid request:xxx        | The input parameter is invalid. | Contact technical support.                                                                |
+--------+-------------+------------+----------------------------+---------------------------------+-------------------------------------------------------------------------------------------+
|        | 500         | VPN.0002   | server error: xxx          | Internal server error.          | Contact technical support.                                                                |
+--------+-------------+------------+----------------------------+---------------------------------+-------------------------------------------------------------------------------------------+
|        | 403         | VPN.0003   | Authentication failed: xxx | Access denied.                  | Obtain the required permissions.                                                          |
+--------+-------------+------------+----------------------------+---------------------------------+-------------------------------------------------------------------------------------------+
|        | 404         | VPN.0004   | resource not found         | Failed to find the resource.    | Check whether the resource ID is correct or whether the resource exists under the tenant. |
+--------+-------------+------------+----------------------------+---------------------------------+-------------------------------------------------------------------------------------------+
