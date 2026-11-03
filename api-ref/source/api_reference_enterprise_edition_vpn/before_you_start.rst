:original_name: vpn_api_0006.html

.. _vpn_api_0006:

Before You Start
================

Overview
--------

A Virtual Private Network (VPN) establishes an encrypted, Internet-based communication tunnel between your network and a Virtual Private Cloud (VPC). By default, Elastic Cloud Servers (ECSs) in a VPC cannot communicate with devices in your on-premises data center or private network. To enable communication between them, you can enable a VPN. S2C VPN allows you to establish secure, reliable, and cost-effective encrypted connections between your on-premises network or data center and a virtual cloud network.

This document describes how to use application programming interfaces (APIs) to perform operations on VPNs, such as creating, querying, deleting, and updating VPNs. For details about all supported operations, see :ref:`API Overview <en-us_topic_0000001854089173>`.

If you plan to use APIs of the VPN service, ensure that you are familiar with concepts of VPN.

API Calling
-----------

VPN supports Representational State Transfer (REST) APIs, allowing you to call APIs using HTTPS. For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

Endpoints
---------

An endpoint is the request address for calling an API. Endpoints vary according to services and regions.

Constraints
-----------

The number of VPN resources that you can create is determined by your quota. You can view or increase the quota.

For more constraints, see description of each API.

Basic Concepts
--------------

-  Account

   An account is created upon successful registration. The account has full access permissions on all of its cloud services and resources. It can be used to reset user passwords and grant user permissions. The account is a payment entity, and using it to perform routine management is not recommended. Instead, you are advised to create Identity and Access Management (IAM) users and grant routine management permissions to the users.

-  User

   You can use your account to create IAM users for routine management of specific cloud services. These users have their own identity credentials (such as passwords and access keys).

   To view your account ID and IAM user ID, log in to the console, click your account in the upper right corner, and choose **My Credentials**. The account name, username, and password will be required for API authentication.

-  Region

   Regions are divided based on geographical locations and network latency. Public services, such as ECS, Elastic Volume Service (EVS), Object Storage Service (OBS), VPC, Elastic IP (EIP), and Image Management Service (IMS), are shared within the same region.

   Regions are classified into universal regions and dedicated regions.

   -  A universal region provides universal cloud services for common tenants.
   -  A dedicated region provides specific services for specific tenants.

-  Availability zone (AZ)

   An AZ comprises one or more physical data centers equipped with independent cooling, fire extinguishing, moisture-proof, and electricity facilities. Compute, network, storage, and other resources in an AZ are logically divided into multiple clusters. AZs within a region are connected using high-speed optical fibers, allowing you to build highly available systems across AZs.

-  Project

   Projects group and isolate resources (including compute, storage, and network resources) across physical regions. A default project is provided for each region. Users can be granted permissions to access all resources in a specific project. If you need more refined access control, create subprojects under a default project and create resources in subprojects. Then, you can assign users the permissions to access resources only in the specific subprojects.


   .. figure:: /_static/images/en-us_image_0000001594352997.png
      :alt: **Figure 1** Project isolation model

      **Figure 1** Project isolation model

   To view a project ID, log in to the console, click your account in the upper right corner, and choose **My Credentials**.

-  Enterprise project

   Enterprise projects group and manage resources across regions. Resources in different enterprise projects are logically isolated. An enterprise project can contain resources across multiple regions, and resources can be added to or removed from enterprise projects.
