:original_name: classic_vpn_0056.html

.. _classic_vpn_0056:

Introduction
============

You can use Identity and Access Management (IAM) for fine-grained permissions management of your VPN resources. If your account does not need individual IAM users, you can skip this section.

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

You can grant users permissions using and . Roles are provided by IAM to define service-based permissions that match users' job responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   Policy-based authorization is useful if you want to allow or deny the access to an API.

An account has permissions to call all APIs. An IAM user under the account can call specific APIs only after being assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user wants to query the VPN gateway list using an API, the user must be granted permissions that allow the **vpn:vpnGateways:list** action.

**Supported Actions**

VPN provides system-defined policies that can be directly used in IAM. You can also create custom policies to supplement system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions controlling the operations that users can perform
-  APIs called by policies
-  Actions supported by policies. They are specific operations that are allowed or denied.
-  IAM or enterprise projects on which actions take effect. Policies that contain actions supporting both IAM and enterprise projects can be used and take effect in both IAM and Enterprise Management. Policies that contain actions supporting only IAM projects can be assigned to user groups and take effect only in IAM. Such policies will not take effect if they are assigned to user groups in Enterprise Management. For details about the differences between IAM and enterprise management, see .

VPN supports the following actions that can be defined in custom policies:

[Example] :ref:`VPN gateway <en-us_topic_0000001807370456>`, including actions supported by VPN gateway APIs, such as the APIs for creating, querying, updating, and deleting VPN gateways.
