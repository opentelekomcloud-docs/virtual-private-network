:original_name: vpn_04_1201.html

.. _vpn_04_1201:

Creating a User and Granting VPN Permissions
============================================

Use the `Identity and Access Management (IAM) <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__ service to implement fine-grained permissions control over your VPN resources. With IAM, you can:

-  Create IAM users for employees based on your enterprise's organizational structure. Each IAM user will have their own security credentials for accessing VPN resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Grant the permission to perform professional and efficient O&M on your VPN resources to other accounts or cloud services.

If your account meets your permissions requirements, you can skip this section.

This section describes the procedure for granting permissions (see :ref:`Figure 1 <en-us_topic_0000001921096265__en-us_topic_0000001542174234_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719>`).

Prerequisites
-------------

You have learned about the permissions supported by VPN, and determined the permissions to be granted to a user group. Before granting permissions of other services, learn about all `permissions <https://docs.otc.t-systems.com/identity-access-management/permissions/permissions.html>`__ supported by IAM.

Process Flow
------------

.. _en-us_topic_0000001921096265__en-us_topic_0000001542174234_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719:

.. figure:: /_static/images/en-us_image_0000001976650417.png
   :alt: **Figure 1** Process of granting VPN permissions

   **Figure 1** Process of granting VPN permissions

#. .. _en-us_topic_0000001921096265__en-us_topic_0000001542174234_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_li10269636890:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__ to it.

   Create a user group on the IAM console and attach the **VPN Administrator** policy to the group.

#. `Create a user and add it to the user group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__.

   Create a user on the IAM console and add the user to the group created in :ref:`1 <en-us_topic_0000001921096265__en-us_topic_0000001542174234_en-us_topic_0173533526_en-us_topic_0173481716_en-us_topic_0172268189_li10269636890>`.

#. `Log in <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   Log in to the management console as the created user. Switch to the authorized region and verify the permissions.

   -  Click **Service List** and choose **Networking** > **Virtual Private Network**. On the **Enterprise - VPN Gateways** page, click **Create VPN Gateway** in the upper right corner. If the VPN gateway is successfully created, the **VPN Administrator** policy has already taken effect.
   -  Choose any other service in **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **VPN Administrator** policy has already taken effect.

   .. note::

      Classic VPN: For details about how to create a user and grant VPC permissions to the user, see `Creating a User and Granting VPC Permissions <https://docs.otc.t-systems.com/virtual-private-cloud/umn/permissions_management/creating_a_user_and_granting_vpc_permissions.html>`__.
