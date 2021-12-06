# TDA30_Asterisk_h323
How To guide for interfacing Asterisk SIP server to Panasonic KX-TDA30 with KX-TDA3480 IPGW4 card.

## Abstract

..

## Contents (incomplete)

[Dial plan](./content/Dialplan.md)

[Trunk Groups](./content/Trunk_Groups.md)

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



