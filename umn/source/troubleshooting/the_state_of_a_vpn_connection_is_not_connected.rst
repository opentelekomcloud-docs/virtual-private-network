:original_name: vpn_trouble_00001.html

.. _vpn_trouble_00001:

The State of a VPN Connection Is **Not connected**
==================================================

Symptom
-------

On the **Enterprise - VPN Connections** page of the VPN console, the state of a VPN connection is displayed as **Not connected**.

Possible Causes
---------------

-  The configurations at the two ends of the VPN connection are incorrect.
-  The security group configuration on the management console or the firewall configuration on the customer gateway device is incorrect.
-  The IPsec VPN connection negotiation fails or the connection is disconnected.

Procedure
---------

#. Check the configurations at the two ends of the VPN connections.

   a. Check whether the gateway IP addresses configured at the two ends of the VPN connection are reversed.

      #. To check the active and standby EIPs of the VPN gateway, choose **Virtual Private Network** > **Enterprise - VPN Gateways** and view the IP addresses in the **Gateway IP Address** column.
      #. To check the IP address of the customer gateway, choose **Virtual Private Network** > **Enterprise - Customer Gateways** and view the IP address in the **Identifier** column.

         -  If the gateway IP addresses at both ends are not reversed, modify the corresponding settings.
         -  If the gateway IP addresses at both ends are reversed, go to :ref:`b <en-us_topic_0000001542014490__li9739151822311>`.

   b. .. _en-us_topic_0000001542014490__li9739151822311:

      Check whether the IKE and IPsec policies at both ends are consistent.

      Choose **Virtual Private Network** > **Enterprise - VPN Connections**, locate the target VPN connection, and choose **More** > **Modify Policy Settings**. View the IKE and IPsec policy settings.

      If the negotiation parameters in the IKE or IPsec policy at both ends are inconsistent, modify the corresponding policy.

      If the negotiation parameters in the IKE and IPsec policies at both ends are consistent, go to :ref:`c <en-us_topic_0000001542014490__li5806232172317>`.

   c. .. _en-us_topic_0000001542014490__li5806232172317:

      Check whether the PSKs at both ends are the same.

      The PSK cannot be checked on the VPN console. If you are not sure whether the PSK configured on the VPN console is correct, you are advised to change it to be the same as that configured on the customer gateway device.

      To change the PSK on the VPN console, choose **Virtual Private Network** > **Enterprise - VPN Connections**, locate the target VPN connection, and choose **More** > **Reset PSK**.

   d. If the policy-based mode is used, check whether the source and destination CIDR blocks in the policy rules at the two ends of the VPN connection are reversed.

      To check policy rules on the VPN console, choose **Virtual Private Network** > **Enterprise - VPN Connections**, locate the target VPN connection, and click **Modify VPN Connection**.

   e. If the static routing mode is used and the NQA function is enabled on the VPN console, check whether tunnel interface IP addresses are correctly configured on the customer gateway device.

      -  To check whether NQA is enabled on the VPN console, choose **Virtual Private Network** > **Enterprise - VPN Connections**, click the name of the target VPN connection, and view the value of **Link Detection** on the **Summary** tab page.

      -  To check the tunnel interface IP addresses configured on the VPN console, choose **Virtual Private Network** > **Enterprise - VPN Connections**, click **Modify VPN Connection**, and view the values of **Local Interface IP Address** and **Customer Interface IP Address**.

         The local and remote interface IP addresses configured on the customer gateway device must be the same as the values of **Customer Interface IP Address** and **Local Interface IP Address** configured on the VPN console, respectively.

   f. If the BGP routing mode is used, check whether the BGP ASNs at the two ends of the VPN connection are reversed.

      -  To check the BGP ASN of the VPN gateway, choose **Virtual Private Network** > **Enterprise - VPN Gateways**, click the VPN gateway name, and view the BGP ASN in the **Basic Information** area.
      -  To check the BGP ASN of the customer gateway, choose **Virtual Private Network** > **Enterprise - Customer Gateways** and view the value in the **BGP ASN** column.

#. Check the security group configuration on the management console and the ACL configuration on the customer gateway device.

   a. Check whether the default security group on the management console permits the ports corresponding to the public IP addresses of the customer gateway.
   b. To check the default security group on the management console, perform the following steps:

      #. Choose **Virtual Private Network** > **Enterprise - VPN Gateways**, and click the name of the VPC associated with the VPN gateway.
      #. On the **Virtual Private Cloud** page, click the number in the **Route Tables** column.
      #. On the **Route Tables** page, click the name of the route table.
      #. Locate and click the next hop of the active or standby EIP of the VPN gateway.
      #. On the **Associated Security Groups** tab page, check whether the security group permits traffic of the ports.

   c. Verify that an ACL on the customer gateway device permits the ports corresponding to the active and standby EIPs of the VPN gateway.

#. Check IPsec connection logs.

   a. Log in to the management console.

   b. Click |image1| in the upper left corner and select the desired region and project.

   c. Click |image2| in the upper left corner, and choose **Network** > **Virtual Private Network**.

   d. In the navigation pane on the left, choose **Virtual Private Network** > **Enterprise - VPN Connections**.

   e. On the **VPN Connection** page, locate the target VPN connection, and click **View Logs** to view connection logs.

      Check IPsec connection logs, and locate the fault based on the log keywords and error codes listed in :ref:`Table 1 <en-us_topic_0000001542014490__table1295195516519>`.

      .. _en-us_topic_0000001542014490__table1295195516519:

      .. table:: **Table 1** Common causes of VPN disconnection

         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         | Category                           | Error Code                                   | Description                                                                                       |
         +====================================+==============================================+===================================================================================================+
         | IPsec VPN negotiation failure      | phase1 proposal mismatch                     | IKE proposal parameters on both ends do not match.                                                |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | phase2 proposal or pfs mismatch              | IPsec proposal parameters, PFS algorithms, or security ACLs on both ends do not match.            |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | responder dh mismatch                        | The DH algorithm of the responder does not match that of the initiator.                           |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | initiator dh mismatch                        | The DH algorithm of the initiator does not match that of the responder.                           |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | encapsulation mode mismatch                  | Encapsulation modes on both ends do not match.                                                    |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | flow mismatch                                | Security ACLs on both sides do not match.                                                         |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | version mismatch                             | IKE versions on both ends do not match.                                                           |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | peer address mismatch                        | IKE peer addresses on both ends do not match.                                                     |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | config ID mismatch                           | No IKE peer with the specified ID is found.                                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | exchange mode mismatch                       | Negotiation modes on both ends do not match.                                                      |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | authentication fail                          | The identity authentication fails.                                                                |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | construct local ID fail                      | A local ID fails to be constructed.                                                               |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | rekey no find old sa                         | The old SA fails to be found during renegotiation.                                                |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | rekey fail                                   | The old SA is going offline during renegotiation.                                                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | first packet limited                         | First packets are rate limited.                                                                   |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | unsupported version                          | The IKE version is not supported.                                                                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | malformed message                            | There is a malformed message.                                                                     |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | malformed payload                            | There is a malformed payload.                                                                     |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | critical drop                                | The critical payload is not recognized.                                                           |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | cookie mismatch                              | The cookies do not match.                                                                         |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | invalid cookie                               | The cookie is invalid.                                                                            |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | invalid length                               | The packet length is invalid.                                                                     |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | unknown exchange type                        | The negotiation mode is unknown.                                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | short packet                                 | Packets are ultra-short.                                                                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | unknown exchange type                        | The negotiation mode is unknown.                                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | uncritical drop                              | The non-critical payload is not identified.                                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | route limit                                  | The number of imported routes reaches the upper limit.                                            |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | ip assigned fail                             | IP address assignment fails.                                                                      |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | eap authentication timeout                   | EAP authentication times out.                                                                     |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | eap authentication fail                      | EAP authentication fails.                                                                         |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | xauth authentication fail                    | XAUTH authentication fails.                                                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | xauth authentication timeout                 | XAUTH authentication times out.                                                                   |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | license or specification limited             | There is license control.                                                                         |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | local address mismatch                       | The local IP address and interface IP address in IKE negotiation do not match.                    |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | dynamic peers number reaches limitation      | The number of IKE peers reaches the upper limit.                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | ipsec tunnel number reaches limitation       | The number of IPsec tunnels reaches the upper limit.                                              |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | netmask mismatch                             | The mask does not match the configured one after the IPsec mask filtering function is enabled.    |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | flow confict                                 | A data flow conflict exists.                                                                      |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | proposal mismatch or use sm in ikev2         | IPsec proposals on both ends do not match or IKEv2 uses an SM algorithm.                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | ikev2 not support sm in ipsec proposal ikev2 | IKEv2 does not support the SM algorithm used in the IPsec proposal.                               |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | no policy applied on interface               | No policy is applied to an interface.                                                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | nat detection fail                           | NAT detection fails.                                                                              |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | fragment packet limit                        | The number of fragments exceeds the upper limit.                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | fragment packet reassemble timeout           | Fragment reassembly times out.                                                                    |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | peer cert is expired                         | The peer certificate has expired.                                                                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | peer cert is revoked by CRL                  | The peer certificate is revoked.                                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | sa with same user exists                     | The SA is the same as that of another user.                                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | max transmit reached                         | The number of retransmitted packets reaches the maximum.                                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         | IPsec VPN connection disconnection | dpd timeout                                  | DPD detection times out.                                                                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | peer request                                 | The remote end sends a message, asking the local end to tear down a tunnel.                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | config modify or manual offline              | The SA is automatically deleted due to configuration modification, or is manually deleted.        |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | phase1 hard expiry                           | In phase 1, hard timeout (no new SA negotiation succeeds) occurs.                                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | phase2 hard expiry                           | A hard timeout occurs in phase 2.                                                                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | heartbeat timeout                            | Heartbeat detection times out.                                                                    |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | re-auth timeout                              | The SA is deleted because the re-authentication times out.                                        |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | aaa cut user                                 | The SA is deleted because the AAA module logs out the user.                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | ip address syn failed                        | IP addresses fail to be synchronized.                                                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | hard expiry triggered by port mismatch       | Hard timeout occurs due to a NAT port number mismatch.                                            |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | kick old sa with same flow                   | The old SA is deleted when the same flow is transmitted.                                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | cpu table updated                            | When an SPU is removed and inserted, the SAs of CPUs other than the one on the SPU are deleted.   |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | flow overlap                                 | The IP address in the encrypted data flow conflicts with the remote IP address.                   |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | spi conflict                                 | An SPI conflict occurs.                                                                           |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | admin down                                   | The VPN tunnel status is admin down.                                                              |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | peer address switch                          | The peer address is changed.                                                                      |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | forward down                                 | The fwd group goes down.                                                                          |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | sa with same user exists                     | The SA is the same as that of another user.                                                       |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | reset sa by ike user                         | A user resets the SA.                                                                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | phase1 sa replace                            | A new IKE SA replaces the old one.                                                                |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | phase2 sa replace                            | A new IPsec SA replaces the old one.                                                              |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | manual offline                               | The connection is manually torn down.                                                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | nhrp notify                                  | The NHRP module notifies the device of SA deletion.                                               |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | receive backup delete info                   | The standby device receives an SA backup deletion message from the active device.                 |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | eap delete old sa                            | When the peer device performs EAP authentication repeatedly, the local device deletes the old SA. |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | receive invalid spi notify                   | The device receives an invalid SPI notification.                                                  |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | dns resolution status change                 | The DNS resolution status is changed.                                                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | ikev1 phase1-phase2 sa dependent offline     | The device deletes the associated IPsec SA when deleting an IKEv1 SA.                             |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | exchange timeout                             | Packet exchange times out.                                                                        |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+
         |                                    | hash gene adjusted                           | The hash factor is adjusted, causing the IPsec tunnel to be deleted.                              |
         +------------------------------------+----------------------------------------------+---------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001628070572.png
.. |image2| image:: /_static/images/en-us_image_0000002394353329.png
