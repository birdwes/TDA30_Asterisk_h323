# Essential terminology and Glossary

[Site Home](../README.md)

## Essential terminology 

### Legs

·     **‘A’ and ‘B’ leg**. A telephone line is not earthed. It is a balanced circuit, to reduce external interference. The ‘legs’ are the two conductors of the telephone cable between the terminal and the exchange. Commonly, the ‘A’ leg is more positive than the ‘B’ leg. Sometimes the exchange or PBX polarity is reversed. On some circuits it may also be reversed when the call transitions from one state to another. In other regions, the ‘A’ conductor is sometimes called the ‘Tip’, the ‘B’ the ‘Ring’, referring to the jack plugs utilised.

### Call State

·     **On hook**. The telephone is dormant and ready to receive a call. The voltage between the ‘A’ and ‘B’ legs is typically in the range 24v-60v. Note that these voltages were often multiples of a 12v lead acid accumulator. 

·     **Off hook**. The telephone has been answered, or is about to dial a number. The voltage between the ‘A’ and ‘B’ legs is typically in the range 8v-12.5v. It should never be more than 15v.

·     **Ring**. An AC current is supplied at a voltage of up to 90v RMS. The ‘On hook’ DC bias voltage may still be superimposed. The frequency is typically in the range 20Hz-30Hz.

### Common dial signalling systems in the UK

·     **Loop Disconnect**. The number is dialled by applying disconnect pulses in sequence, between the A and B legs. This may be accomplished using a rotating dial, or an electronic switch such as a relay.

·     **DTMF**. Dual Tone Multi Frequency. Each digit in the dialled number generates a combination of two frequencies, which should be recognized by the receiving equipment.


## Glossary


| Abbreviation | Description                                                  |
| ------------ | ------------------------------------------------------------ |
|              |                                                              |
| ARS          | "Automatic Route Selection".                                 |
| ATA          | "Analogue Terminal Adapter".  A device which emulates a POTS CO line, enabling the making and receiving of calls to a SIP VoIP server. |
| CCU          | "Central Control Unit".  Synonymous with a small PBX.        |
| CLI          | "Calling Line Identity".  The caller's number is transmitted to be optionally displayed at the receiving terminal. |
| CO line      | "Central Office" line.  A telephone circuit which connects the PBX to the PSTN, or another branch office.  This could be as simple as single residential POTS line. |
| CODEC        | "**Co**der/**Dec**oder".  An algorithm which encodes audio (or video) into a binary format at the transmitter and decodes it back at the receiver. |
| COS          | "Class Of Service".  An algorithm provided by the PBX to determine which numbers are permitted be dialled.  Each extension may be assigned a differing class of service, e.g. to bar calls to international or premium rate numbers. |
| CPS          | "Carrier Pre Selection".  The PSTN exchange is programmed with a "Carrier Code" to enable calls to be billed to you, by a carrier other than your PSTN line provider. |
| DDI          | "Direct Dial Inwards".  Synonymous with DIL                  |
| DIL          | "Direct Inward Line".  Facility which enables a call from a CO line to a single extension, or extension group within a PBX setup. |
| DLC          | Panasonic Proprietary "Digital Loop Carrier".                |
| DTMF         | Dual Tone Multi Frequency, a method of transmitting digits over an analogue channel.  Commonly used by newer analogue POTS syle telephones. |
| h.323        |                                                              |
| IDA          | "Indirect Access".  The subscriber may manually dial, or have programmed into their PBX, a code which selects billing from a carrier other than the PSTN line provider. |
| IPSEC        | IP Security.  A means of securely connecting two networks together, over a public IP connection. |
| LAN          | Local Area Network,                                          |
| LD           | Loop Disconnect.  A means of dialing a number, but applying a series of pulsed disconnects across a POTS style line. |
| LLU          | "Local Loop Unbundling".                                     |
| MSN          | "Multiple Subscriber Number".  An ISDN facility which enables multiple numbers to be received by opne or more ISDN lines.  The PBX can distiguish the dialled number, and reroute the call accordingly. |
| PABX         | "Private Automated Branch Exchange".                         |
| PBX          | "Private Branch Exchange".                                   |
| POTS         | "Plain Old Telephony System".  The PSTN version of an analogue line, provided from your local exchange and line provider.  POTS is being phased out in the UK. |
| PSTN         | "Public Switched Telecommunications Network".                |
| PT           | Panasonic Digital "Proprietary Telephone", for use with a DLC card. |
| RTP          |                                                              |
| SIP          |                                                              |
| SLC          | "Subscriber Loop Carrier".  Panasonic Analogue Line Card.  Provides an extension to a PBX, which is electrically compatible with a POTS line. |
| SLT          | Telephone, compatible with SLC port.  "Single Line Telephone". |
| SoGEA        | "Single Order Generic Ethernet Access".  [https://www.btwholesale.com/news-and-resources/features-and-campaigns/sogea.html](https://www.btwholesale.com/news-and-resources/features-and-campaigns/sogea.html) |
| TIE          | A private circuit which connects two or more PBXs together.  |
| TRS          | "Trunk Route Selection".                                     |
| UPS          | "Uninterruptible Power Supply".                              |
| VoIP         | "Voice over IP".                                             |
| VPN          | "Virtual Private Network".                                   |
| WLR          | "Wholesale Line Rental".  The family of products provided by Openreach and other LLU line providers, which includes POTS, ISDN-BRI and ISDN-PRI (amongst others). |



---

[Dial plan](./Dialplan.md)

[Automatic Route Selection](./ARS.md) - Required for external Asterisk routing with the IPGW4 card.

[IPGW4 Configuration](./IPGW4.md) 

[Essential Terminology](./Terminology.md) 

[Wiring Notes](./WiringNotes.md) 

[Emergency Considerations](./OtherConsiderations.md) 

[Third Party Resources](../Third%20Party%20Resources/README.md) - Various specifications describing dialling, ringing and other signalling.

