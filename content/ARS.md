# ARS (Automatic Route Selection)

[Site Home](../README.md)

The Asterisk server is set up with a dial plan context, which allows access to the Asterisk extensions.

This causes an issue if the IPGW4 is intended to be also used as a CO line.  To overcome this problem, the ARS feature of the TDA30 is used to allow calls from Asterisk to break out into a different context, which simulates the behaviour of a single CO line, i.e. numbers dialled are all external PSTN numbers.

For the UK, Ofcom provides the [national-numbering-plan](https://www.ofcom.org.uk/__data/assets/pdf_file/0013/102613/national-numbering-plan.pdf) and [national numbering data](https://www.ofcom.org.uk/phones-telecoms-and-internet/information-for-industry/numbering/numbering-data).  IDA (indirect access) carrier access numbers are in the range 124-140, 143-146, 148-149, 160-169 and 181 to 189.

To avoid any conflict with an existing service code, should the call mistakenly escape to the PSTN via another CO line, we have chosen a range which is currently unused: 18930 to 18959.

## ARS on Asterisk

Within the Asterisk extension dialling context (`extensions.conf`) we place the line:

```
[sip_extensions]
exten => _1893[0-2]X.,1,Goto(sip_uk_transparent,${EXTEN:5},1)
...
```

The above assumes that your default extension dial context is `[sip_extensions]`

We use three carrier access codes, to eliminate some interdigit timeout delays, if this was all handled by 18930.  This corresponds to part of the DN2IP table of the IPGW4, which specifies the maximum number of dialled digits, for each leading number.

| Carrier Access Code | Purpose                                       |
| ------------------- | --------------------------------------------- |
| 18930               | up to 20 digits, e.g. international calls     |
| 18931               | up to 11 digits, i.e. national dialling       |
| 18932               | up to 6 digits, i.e. local area code dialling |
|                     |                                               |

This concept could also be modified to provide access to multiple SIP providers.

```
[globals]
LOCAL_STD=01632
...

[sip_uk_transparent]
exten => _0.,1,Dial(SIP/${EXTEN}@sipgate-proxy,360)
exten => _[2345678].,1,Dial(SIP/${LOCAL_STD}${EXTEN}@sipgate-proxy,360)
exten => 999,1,Dial(SIP/999@sipgate-proxy,10000)
...
```



This accepts dialled numbers prefixed with 1893[0-2], strips the first five digits, and redirects them to the context `sip_uk_transparent`.  This context behaves as if it is on the local PSTN, i.e. numbers in the range 2 to 8 are prefixed with the local area code.

### Exceptions
The national numbering plan prohibits local number dialling, without a code in the following regions.

| Code | Area |
|----|----|
| 01202 | Bournemouth |
| 01224 | Aberdeen |
| 01273 | Brighton |
| 01274 | Bradford |
| 01642 | Middlesbrough |
| 01908 | Milton Keynes |



## ARS on the TDA30

### Carrier

Set up the Carriers.  8.5 Carrier

| Carrier Name  | Purpose                                                      |
| :-----------: | :----------------------------------------------------------- |
|    C-PSTN     | PSTN CO line(s)                                              |
|   C-SIP-ATA   | SIP ATA VoIP CO line(s)                                      |
| SIP-Internal  | H.323 without access code, to access Asterisk internal extensions. |
| H323-20-digit | International H.323                                          |
| H323-11-digit | National H.323                                               |
| H323-6-digit  | Local exchange area calls, H.323                             |

![](images/TDA30_Carrier.png)


Select the TRG1-16 tab and choose the correct carrier for each trunk group.  Apply.

![](images/TDA30_TrunkCarrier.png)

### Routing Plan

8.4 Routing Plan Priority

| Routing Plan |  Priority 1   |  Priority 2   |
| :----------: | :-----------: | :-----------: |
|      1       |    C-PSTN     | H323-20-digit |
|      2       |   C-SIP-ATA   |       -       |
|      3       | SIP-Internal  |       -       |
|      4       | H323-20-digit |    C-PSTN     |
|      5       | H323-11-digit |    C-PSTN     |
|      6       | H323-6-digit  |    C-PSTN     |

Setting this up is a little tedious, as each day of the week must be set up, for each plan.  It is possible to right click and select a priority row, and copy-paste it to another day.

![](images/TDA30_RoutingPlanPriority.png)

Set up the leading numbers.  8.2 Leading Number

You can import this table by choosing from the Menu Tool->Import->ARS - Leading Digit from this file: [arsl.csv](files/TDA30/arsl.csv)

The file may be edited in popular spreadsheet software.

Place exception codes at the top of the list, e.g. in this example I want 999 and 112 emergency calls to always try the PSTN first (plan 1).  I also want 123 to try the Asterisk server first (plan 4).

![](images/TDA30_TrunkLeadingNumber.png)

8.1 System Setting

Enable ARS Mode

![](images/TDA30_EnableARS.png)

---

[Dial plan](./Dialplan.md)

[Automatic Route Selection](./ARS.md) - Required for external Asterisk routing with the IPGW4 card.

[IPGW4 Configuration](./IPGW4.md) 

[Essential Terminology](./Terminology.md) 

[Wiring Notes](./WiringNotes.md) 

[Emergency Considerations](./OtherConsiderations.md) 

[Third Party Resources](../Third%20Party%20Resources/README.md) - Various specifications describing dialling, ringing and other signalling.

