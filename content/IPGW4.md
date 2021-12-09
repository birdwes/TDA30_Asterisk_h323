# KX-TDA3480 IPGW4 Configuration

[Site Home](../README.md)

The IPGW4 card provides h.323 communication for four channels to the KX-TDA15/30 PABX systems.  This may be interfaced with Asterisk using the ooh323 driver.

Extensive configuration information is provided in the manuals "4-Channel VoIP Gateway Card - Getting Started" and "4-Channel VoIP Gateway Card - Programming Guide".

If your card requires restoring to factory defaults, the reset procedure is described in "Getting Started" appendix C.

Once the card is reset to factory defaults, it has the following settings, to access it:

|  | Value |
|----|----|
| IP Address | 192.168.1.200 |
| Subnet Mask | 255.255.255.0 |
| Username | Administrator |
| Password | Administrator |

## Configuration Warning
DO NOT expose the IP address of the IPGW4 card to any public IP address.  If you were to, you would undoubtedly be attacked within minutes, and become a victim of "toll fraud".

The IPGW4 does not provide any IP security, not even for configuration.  If you plan to use these cards on multiple network segments, you MUST provide a privately routed secure network such as IPSEC tunnel or other VPN solution.  Avoid NAT if possible.  This solution has not been tested with NAT.

It is strongly suggested that if your Asterisk server is exposed on a public IP address, that the h.323 listener is bound to an internal IP address, which is not public.

## IP Address Configuration 

Choose 1.1 Network Settings, General and select an appropriate IP address, subnet and gateway settings.

1.2 

![](images/3480_h323.png)

![](images/3480_VoiceComms.png)

[Site Home](../README.md)

[Dial Plan](Dialplan.md)

[Automatic Route Selection](ARS.md)

[KX-TDA3480 IPGW4 Configuration](IPGW4.md)

[Home](README.md)