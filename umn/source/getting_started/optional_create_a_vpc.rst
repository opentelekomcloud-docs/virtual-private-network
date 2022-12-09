:original_name: en-us_topic_0122970066.html

.. _en-us_topic_0122970066:

(Optional) Create a VPC
=======================

Scenarios
---------

A VPC provides an isolated virtual network for ECSs. You can configure and manage the network as required.

Create a VPC by following the procedure provided in this section. Then, create subnets, security groups, and VPNs, and assign EIPs by following the procedure provided in subsequent sections based on your actual network requirements.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. Click **Create VPC**.

#. On the **Create VPC** page, set parameters as prompted.

   During VPC creation, a default subnet will be created and you can also click **Add Subnet** to create more subnets for the VPC.

   .. _en-us_topic_0122970066__en-us_topic_0118499007_en-us_topic_0118498861_table1168883712472:

   .. table:: **Table 1** VPC parameter description

      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Category          | Parameter          | Description                                                                                                                                                                                                                                                              | Example Value       |
      +===================+====================+==========================================================================================================================================================================================================================================================================+=====================+
      | Basic Information | Region             | Specifies the desired region. Regions are geographic areas isolated from each other. Resources are region-specific and cannot be used across regions through internal network connections. For low network latency and quick resource access, select the nearest region. | eu-de               |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | Name               | Specifies the VPC name.                                                                                                                                                                                                                                                  | VPC-001             |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | CIDR Block         | Specifies the CIDR block for the VPC. The CIDR block of a subnet can be the same as the CIDR block for the VPC (for a single subnet in the VPC) or a subset (for multiple subnets in the VPC).                                                                           | 192.168.0.0/16      |
      |                   |                    |                                                                                                                                                                                                                                                                          |                     |
      |                   |                    | The following CIDR blocks are supported:                                                                                                                                                                                                                                 |                     |
      |                   |                    |                                                                                                                                                                                                                                                                          |                     |
      |                   |                    | 10.0.0.0 - 10.255.255.255                                                                                                                                                                                                                                                |                     |
      |                   |                    |                                                                                                                                                                                                                                                                          |                     |
      |                   |                    | 172.16.0.0 - 172.31.255.255                                                                                                                                                                                                                                              |                     |
      |                   |                    |                                                                                                                                                                                                                                                                          |                     |
      |                   |                    | 192.168.0.0 - 192.168.255.255                                                                                                                                                                                                                                            |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | Tag                | Specifies the VPC tag, which consists of a key and value pair. You can add a maximum of ten tags to each VPC.                                                                                                                                                            | -  Key: vpc_key1    |
      |                   |                    |                                                                                                                                                                                                                                                                          | -  Value: vpc-01    |
      |                   |                    | The tag key and value must meet the requirements listed in :ref:`Table 2 <en-us_topic_0122970066__en-us_topic_0118499007_en-us_topic_0118498861_table248245914136>`.                                                                                                     |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Name               | Specifies the subnet name.                                                                                                                                                                                                                                               | Subnet              |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | CIDR Block         | Specifies the CIDR block for the subnet. This value must be within the VPC CIDR range.                                                                                                                                                                                   | 192.168.0.0/24      |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Gateway            | Specifies the gateway address of the subnet.                                                                                                                                                                                                                             | 192.168.0.1         |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | DNS Server Address | The external DNS server address is used by default. If you need to change the DNS server address, ensure that the configured DNS server address is available.                                                                                                            | 192.168.1.0         |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | NTP Server Address | Specifies the NTP server IP address. A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                         | 192.168.2.1         |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Tag                | Specifies the subnet tag, which consists of a key and value pair. You can add a maximum of ten tags to each subnet.                                                                                                                                                      | -  Key: subnet_key1 |
      |                   |                    |                                                                                                                                                                                                                                                                          | -  Value: subnet-01 |
      |                   |                    | The tag key and value must meet the requirements listed in :ref:`Table 3 <en-us_topic_0122970066__en-us_topic_0118499007_en-us_topic_0118498861_table6536185812515>`.                                                                                                    |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+

   .. _en-us_topic_0122970066__en-us_topic_0118499007_en-us_topic_0118498861_table248245914136:

   .. table:: **Table 2** VPC tag key and value requirements

      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                               | Example Value         |
      +=======================+============================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                                   | vpc_key1              |
      |                       | -  Must be unique for the same VPC and can be the same for different VPCs. |                       |
      |                       | -  Can contain a maximum of 36 characters.                                 |                       |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                                 | vpc-01                |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0122970066__en-us_topic_0118499007_en-us_topic_0118498861_table6536185812515:

   .. table:: **Table 3** Subnet tag key and value requirements

      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                        | Example Value         |
      +=======================+=====================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                            | subnet_key1           |
      |                       | -  Must be unique for each subnet.                                  |                       |
      |                       | -  Can contain a maximum of 36 characters.                          |                       |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                          | subnet-01             |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+

#. The external DNS server address is used by default. If you need to change the DNS server address, select **Custom** for **Advanced Settings** and configure the DNS server addresses. You must ensure that the configured DNS server addresses are available.

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
