:original_name: vpn_08_0614.html

.. _vpn_08_0614:

How Do I Configure DPD for Interconnection with the Cloud?
==========================================================

By default, DPD is enabled on the cloud side and cannot be disabled.

Configure DPD as follows:

-  DPD-type: on-demand
-  DPD idle-time: 30s
-  DPD retransmit-interval: 15s
-  DPD retry-limit: 3
-  DPD msg: seq-hash-notify

The **DPD msg** format at both ends of the VPN connection must be the same, but the DPD type, idle time, retransmission interval, and retry limit can be different.
