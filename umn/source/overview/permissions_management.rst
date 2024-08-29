:original_name: vpn_01_0011.html

.. _vpn_01_0011:

Permissions Management
======================

If you need to assign different permissions to personnel in your enterprise to access your VPN resources created on the cloud service platform, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, helping you securely manage access to your resources.

With IAM, you can use your account to create IAM users, and assign permissions to the users to control their access to specific cloud resources. For example, some software developers in your enterprise need to use VPN resources but should not be allowed to delete them or perform any high-risk operations. In this scenario, you can create IAM users for the software developers and grant them only the permissions required for using VPN resources.

If your account does not need individual IAM users for permissions management, skip this section, which has no impact on using functions of VPN.

IAM is a free service. You only pay for the resources in your account.

For more information about IAM, see `IAM Service Overview <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__.

VPN Permissions
---------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

VPN is a project-level service deployed for specific regions. When you set **Scope** to **Region-specific projects** and select the specified projects in the specified regions, the users only have permissions for VPN in the selected projects. If you set **Scope** to **All resources**, users have permissions for VPN in all region-specific projects. When accessing VPN, the users need to switch to the authorized region.

You can grant permissions by using roles or policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. There are only a limited number of roles for granting permissions to users. Some roles depend other roles to take effect. When you assign such roles to users, remember to assign the roles they depend on. However, roles are not an ideal choice for fine-grained authorization and secure access control.
-  Policies: a type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, administrators can grant IAM users only permissions to manage VPN resources of a certain type.

:ref:`Table 1 <en-us_topic_0000001965006205__en-us_topic_0000001542014682_en-us_topic_0173524723_en-us_topic_0173475706_en-us_topic_0170232209_table481412518317>` lists all system-defined permissions for VPN.

.. _en-us_topic_0000001965006205__en-us_topic_0000001542014682_en-us_topic_0173524723_en-us_topic_0173475706_en-us_topic_0170232209_table481412518317:

.. table:: **Table 1** System-defined permissions for VPN

   +-------------------------------------+-------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
   | System Role/Policy Name             | Description                                                                                                             | Dependency                                                                                                                                            |
   +=====================================+=========================================================================================================================+=======================================================================================================================================================+
   | VPN Administrator (not recommended) | Administrator permissions for VPN. Users with these permissions can perform all operations on VPN.                      | ``-``                                                                                                                                                 |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     | Users with these permissions have the **VPC Administrator** and **Tenant Guest** permissions by default.                |                                                                                                                                                       |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     | -  **VPC Administrator**: project-level policy, which is selected in the same project as **VPN Administrator**.         |                                                                                                                                                       |
   |                                     | -  **Tenant Guest**: project-level policy, which is selected in the same project as **VPN Administrator**.              |                                                                                                                                                       |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN FullAccess (recommended)        | Full permissions for VPN.                                                                                               | The actions of global services and the region-level actions cannot be configured in the same policy. As such, the following global actions are added: |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "tms:predefineTags:list"                                                                                                                              |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "scm:cert:list"                                                                                                                                       |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "scm:cert:get"                                                                                                                                        |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "scm:cert:download"                                                                                                                                   |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
   | VPN ReadOnlyAccess                  | Read-only permissions on VPN resources. Users who have these permissions can only view information about VPN resources. | The actions of global services and the region-level actions cannot be configured in the same policy. As such, the following global actions are added: |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "tms:predefineTags:list"                                                                                                                              |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "scm:cert:list"                                                                                                                                       |
   |                                     |                                                                                                                         |                                                                                                                                                       |
   |                                     |                                                                                                                         | "scm:cert:get"                                                                                                                                        |
   +-------------------------------------+-------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

:ref:`Table 2 <en-us_topic_0000001965006205__en-us_topic_0000001542014682_table13641113421711>` lists the common operations supported by system-defined permissions for VPN.

.. _en-us_topic_0000001965006205__en-us_topic_0000001542014682_table13641113421711:

.. table:: **Table 2** Common operations supported by system-defined permissions for VPN

   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Operation                                | VPN Administrator (Not Recommended) | VPN FullAccess (Recommended) | VPN ReadOnlyAccess |
   +==========================================+=====================================+==============================+====================+
   | Creating a VPN gateway                   | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Viewing a VPN gateway                    | Y                                   | Y                            | Y                  |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Querying the VPN gateway list            | Y                                   | Y                            | Y                  |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Updating a VPN gateway                   | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Deleting a VPN gateway                   | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Creating a VPN connection                | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: Y            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Viewing a VPN connection                 | Y                                   | Y                            | Y                  |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Querying the VPN connection list         | Y                                   | Y                            | Y                  |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Updating a VPN connection                | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: Y            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Deleting a VPN connection                | Y                                   | -  Enterprise Edition VPN: x | x                  |
   |                                          |                                     | -  Classic VPN: Y            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Creating a customer gateway              | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: N/A          |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Viewing a customer gateway               | Y                                   | -  Enterprise Edition VPN: Y | Y                  |
   |                                          |                                     | -  Classic VPN: N/A          |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Querying the customer gateway list       | Y                                   | -  Enterprise Edition VPN: Y | Y                  |
   |                                          |                                     | -  Classic VPN: N/A          |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Updating a customer gateway              | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: N/A          |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Deleting a customer gateway              | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: N/A          |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Creating a VPN connection monitor        | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Querying a VPN connection monitor        | Y                                   | -  Enterprise Edition VPN: Y | Y                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Querying the VPN connection monitor list | Y                                   | -  Enterprise Edition VPN: Y | Y                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+
   | Deleting a VPN connection monitor        | Y                                   | -  Enterprise Edition VPN: Y | x                  |
   |                                          |                                     | -  Classic VPN: x            |                    |
   +------------------------------------------+-------------------------------------+------------------------------+--------------------+

.. note::

   Classic VPN: For details about how to create a user and grant VPC permissions to the user, see `Creating a User and Granting VPC Permissions <https://docs.otc.t-systems.com/virtual-private-cloud/umn/permissions_management/creating_a_user_and_granting_vpc_permissions.html>`__.

Helpful Links
-------------

-  `IAM Service Overview <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__
