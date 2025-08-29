:original_name: vpn_01_0027.html

.. _vpn_01_0027:

Region and AZ
=============

Concepts
--------

Regions and availability zones (AZs) identify the locations of data centers. You can create resources in regions and AZs.

-  A region is a physical data center location. Each region is completely independent, maximizing the fault tolerance capability and stability. After you create resources in a region, the region cannot be changed.
-  An AZ is a physical location with independent power supplies and network in a region. A region can contain multiple AZs that are physically isolated but internally interconnected. Faults that occur in one AZ will not affect other AZs. The inter-AZ connections are low-latency and unexpensive.

:ref:`Figure 1 <en-us_topic_0000001592693965__en-us_topic_0184026189_fig8747114281212>` shows the relationship between regions and AZs.

.. _en-us_topic_0000001592693965__en-us_topic_0184026189_fig8747114281212:

.. figure:: /_static/images/en-us_image_0000001542015014.png
   :alt: **Figure 1** Regions and AZs

   **Figure 1** Regions and AZs

Selecting a Region
------------------

-  Resource price

   Resource prices may vary in different regions.


Selecting a Region
------------------

You are advised to select a region close to you or your target users to reduce network latency and improve the access speed.

Selecting an AZ
---------------

When selecting a region to deploy resources, consider your applications' requirements on disaster recovery (DR) and network latency.

-  For robust DR, deploy resources in different AZs within the same region.
-  For a low network latency, deploy resources in the same AZ.

Regions and Endpoints
---------------------

Before you use an API to call resources, specify its region and endpoint. For more information, see `Regions and Endpoints <https://docs.otc.t-systems.com/regions-and-endpoints/index.html>`__.
