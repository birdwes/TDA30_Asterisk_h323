# Interfacing the Panasonic KX-TDA30 to Asterisk, with h.323
How To guide for interfacing Asterisk VoIP server to Panasonic KX-TDA30 with KX-TDA3480 IPGW4 card.

## Abstract

This configuration guide is a "How To" for those wishing to connect an Asterisk VoIP server to the Panasonic KX-TDA30 PABX, using the IPGW4 (KX-TDA3480) h.323 expansion card.

### Motivation

With the transition to modern VoIP services already happening, concerns are being raised by a number of people operating "Heritage Telecoms" equipment, which depends upon Loop Disconnect dialling.  The configuration described here, allows a number of LD telephones to be seamlessly connected to modern VoIP services, and retain access to the PSTN.  Additionally, they may join an existing Asterisk VoIP setup, which already has other VoIP extensions.

The KX-TDA30 permits cards which support analogue terminal equipment to be fitted.  In addition, there are four built in hybrid ports, which support analogue and digital terminal equipment.

By not using VoIP extensions, we avoid the need to provide mains power at every extension.

The card required to interface the TDA30 to Asterisk, by h.323 is the "IPGW4" (KX-TDA3480).

The cards required for the TDA30 to support analogue terminal equipment are of the "SLC4" and/or the "SLC8" type.  Their line characteristics correspond closely with the existing POTS PSTN (at the time of writing).  These cards support both LD and DTMF dialling.

If you optionally wish to use SIP-ATA adaptors, you will also need a "LCOT4" card.  We shall not describe that configuration here.

### Advantages of using h.323 over SIP

The IPGW4 card is configured in the TDA30 as a "Private Circuit" or "TIE line".  This allows seamless extension to extension between VoIP and analogue extensions, in addition to providing access to the PSTN via the Asterisk server.  Trying to set up a similar configuration with SIP ATAs is messy and the author has found it to be unreliable too.  Additionally, because the TDA30 employs a digital backplane, once the ADC conversion is done in the LCOT card, it stays in the digital domain, right up until the exchange serving the dialled device, be it local, or across the globe.  Using SIP ATAs with a LCOT card requires three conversions instead of one.

### Prerequisites

You must have 

- access to the "Panasonic PBX Unified Maintenance Console" software, and manuals, which are provided to Panasonic dealers and installers.

- KX-TDA15 or KX-TDA30 PABX

- KX-TDA3480 IPGW4 card

- SLC4 and/or SLC8 cards

- a working Asterisk server 
  - if the server is externally hosted, you must provide a routed IPSEC tunnel or similar VPN solution, between the private LAN segment on which the IPGW4 card is to be located, and the Asterisk server.


## Contents (incomplete)

[Dial plan](./content/Dialplan.md)

[Automatic Route Selection](./content/ARS.md) - Required for external Asterisk routing with the IPGW4 card.

[IPGW4 Configuration](./content/IPGW4.md) 

[Essential Terminology](./content/Terminology.md) 

[Third Party Resources](./Third%20Party%20Resources/README.md) - Various specifications describing dialling, ringing and other signalling.




