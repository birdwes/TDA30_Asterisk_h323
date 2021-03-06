# Other Considerations

[Site Home](../README.md)

## Emergency calls - general

As well as the PSTN, some SIP providers permit emergency calls to be dialled, e.g. [https://www.sipgate.co.uk].  You may have to "opt-in" and register your geographic address, to allow emergency response teams to locate you.  This of course presents a problem with your Asterisk dialplan, if you permit emergency numbers to be dialled from a "non-home" location.  Be cautious about this.

The emergency number table of the TDA30 (TRS 7.4) specifies numbers that bypass COS restrictions.  You need to ensure that your ARS selection only permits emergency numbers to be routed out via trunks that can accept such a call.

## Power Failure and Emergency Calls

The TDA30 supports a lookup table of emergency call numbers.

If the TDA30 has a LCOT4 POTS card, in the event of a power failure (and optional battery failure)  to the CCU, analogue ports XDP1 and XDP2 (of the built in DHLC4 card) are physically connected directly to LCOT ports 1 and 2.  If you are placing the unit into service in any location where emergency calls might be made, consideration should be taken of the location and type of telephones connected to these extensions.  In my case for example, the local PSTN still supports LD dialling.  This will vary by your location.  You may have to consider fitting a DTMF telephone(s) to that extension.

When 21CN VoIP via SOGEA access, is finally rolled out to the whole of the UK (for more information see [Openreach Stop Sell List](https://www.openreach.co.uk/cpportal/products/product-withdrawal/stop-sells-updates)), this will present the problem of emergency numbers being dependent upon power to the router or ATA that Openreach provide to replace your POTS line access.

I use a UPS system to protect my PBX, router and Raspberry Pi (IPSEC router).

If you have only one PSTN line, such as in a residential situation you might want to consider connecting both LCOT ports 1 and 2 to the single line, in parallel.  This will allow power failure emergency calls to be dialled from either of two extensions, instead of one.

## CO Lines that are unavailable

To avoid sending an emergency call to a CO line that is unavailable, it is important to ensure that all unused and faulty CO lines are excluded from availability:

- 1.1 Configuration, Slot.  Right click on each CO card and select "Port Property".  Each port will be listed as either "INS" (In Service) or "OUS" (out of service).  Ensure that only connected and functioning ports are INS.  All other ports should be OUS.

The TDA30 provides a facility to automatically monitor LCO port availability and switch their INS/OUS status, depending on presence of a loop current.  This may help if you are using SIP ATAs, should one of them develop a fault.

- 2.9 System, System Options, Tab Option 5.  Busy Out->Busy Out for Analogue CO.  Consider enabling this.


---

[Dial plan](./Dialplan.md)

[Automatic Route Selection](./ARS.md) - Required for external Asterisk routing with the IPGW4 card.

[IPGW4 Configuration](./IPGW4.md) 

[Essential Terminology](./Terminology.md) 

[Wiring Notes](./WiringNotes.md) 

[Emergency Considerations](./OtherConsiderations.md) 

[Third Party Resources](../Third%20Party%20Resources/README.md) - Various specifications describing dialling, ringing and other signalling.

