:original_name: en-us_topic_0142368417.html

.. _en-us_topic_0142368417:

What Can I Do If the VPN Fails or the Network Speed of the VPN Is Slow?
=======================================================================

You can perform the following steps to handle the issues:

#. Check the ECS specifications. Rate limiting is not performed for the VPN ingress on the cloud, so the issue may be caused by the ECS specifications.
#. Rate limiting has been configured for the VPN egress on the cloud. Check whether your bandwidth has reached or exceeded the maximum limit allowed.
#. Check your local network to see whether the network speed is slow.
#. Check whether packets sent between the cloud and the customer data center have been lost.
