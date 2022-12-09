:original_name: en-us_topic_0122970067.html

.. _en-us_topic_0122970067:

(Optional) Create a Subnet for the VPC
======================================

Scenarios
---------

You can add subnets during VPC creation. If required, you can also create subnets for an existing VPC.

The created subnet is configured with DHCP by default. After an ECS using this VPC starts, the ECS automatically obtains an IP address using DHCP.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. In the navigation pane on the left, click **Virtual Private Cloud**.

#. On the **Virtual Private Cloud** page, locate the VPC for which a subnet is to be created and click the VPC name.

#. On the displayed **Subnets** tab, click **Create Subnet**.

#. In the **Create Subnet** area, set parameters as prompted.


   .. figure:: /_static/images/en-us_image_0161052509.png
      :alt: **Figure 1** Create Subnet

      **Figure 1** Create Subnet

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                           | Example Value         |
      +=======================+=======================================================================================================================================================================+=======================+
      | Name                  | Specifies the subnet name.                                                                                                                                            | Subnet                |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | CIDR Block            | Specifies the CIDR block for the subnet. This value must be within the VPC CIDR range.                                                                                | 192.168.0.0/24        |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway               | Specifies the gateway address of the subnet.                                                                                                                          | 192.168.0.1           |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | NTP Server Address    | Specifies the NTP server IP address. A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                      | 192.168.2.1           |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                   | Specifies the subnet tag, which consists of a key and value pair. You can add a maximum of ten tags to each subnet.                                                   | -  Key: subnet_key1   |
      |                       |                                                                                                                                                                       | -  Value: subnet-01   |
      |                       | The tag key and value must meet the requirements listed in :ref:`Table 2 <en-us_topic_0122970067__en-us_topic_0118498844_en-us_topic_0118498823_table4528555192814>`. |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | DNS Server Address    | The external DNS server address is used by default. If you need to change the DNS server address, ensure that the configured DNS server address is available.         | ``-``                 |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0122970067__en-us_topic_0118498844_en-us_topic_0118498823_table4528555192814:

   .. table:: **Table 2** Subnet tag key and value requirements

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

#. Click **OK**.

Precautions
-----------

After a subnet is created, five IP addresses in the subnet will be reserved and cannot be used. For example, in a subnet with CIDR block 192.168.0.0/24, the following IP addresses are reserved:

-  192.168.0.0: Network address.
-  192.168.0.1: Gateway address.
-  192.168.0.253: Reserved for the system interface. This IP address is used by the VPC for external communication.
-  192.168.0.254: DHCP service address.
-  192.168.0.255: Network broadcast address.

If you set **Advanced Settings** to **Custom** during subnet creation, the reserved IP addresses may be different from the preceding default ones. The system will reserve five IP addresses based on your subnet settings.

.. |image1| image:: /_static/images/en-us_image_0161052507.png
