# Dial-plan / Numbering Plan

[Site Home](../README.md)

The choice of "Dial Plan" or "Numbering Plan" is possibly the most important decision process before attempting any further work.  Getting this wrong, will cause problems and pain, at a later date.  Note that PSTN elements of this dialplan relate to the UK.

## Internal Dialplan

In this example:

| Leading Digits | Purpose                 | Asterisk                             | TDA30 Site-A  | TDA30 Site-B  |
| -------------- | ----------------------- | ------------------------------------ | ------------- | ------------- |
| 0              |                         | Geographic or International PSTN DN. | Site Operator | Site Operator |
| 1xx.           | Special system numbers  |                                      |               |               |
| 2xx            | Extensions              |                                      | X             |               |
| 3xx            | Extensions              | X                                    |               |               |
| 4xx            | Extensions              |                                      |               | X             |
| 5xx            | Voicemail               |                                      | X             | X             |
| 6xx            | Ring/hunt Groups        | 660-699                              | 600-629       | 630-659       |
| 7xx            | N/A                     |                                      |               |               |
| 8xx            | Trunk Access (specific) | X                                    | X             | X             |
| 9              | Trunk Access (general)  | X                                    | X             | X             |

## PSTN Dialplan (UK)

For the UK, Ofcom provides the [national-numbering-plan](https://www.ofcom.org.uk/__data/assets/pdf_file/0013/102613/national-numbering-plan.pdf) and [national numbering data](https://www.ofcom.org.uk/phones-telecoms-and-internet/information-for-industry/numbering/numbering-data).



| Leading digits| Purpose | Min remaining digits | Max remaining digits |
| -------------- |---| -------------------- | -------------------- |
| 00             |International| Unknown | Unknown |
| 01             |Geographic| 9                    | 10                   |
| 02             |Geographic| 10                   | 10                   |
| 03             |National| 10                   | 10                   |
| 04             |N/A| N/A                  | N/A                  |
| 05             |Corporate| 10                   | 10                   |
| 06             |N/A| N/A                  | N/A                  |
| 07             |Personal Numbers, Radiopaging Service & Mobile Service numbers| 10                   | 10                   |
| 08             | Non-Geographic                                               | 7                    | 10                   |
| 09             |Non-Geographic| 10                   | 10                   |
| 1              |Access codes| 2                    | 6                    |
| 2-8            |Local PSTN (not available in some areas)| 5                    | 6                    |
| 9              |Emergency| 2                    | 2                    |



## Programming the Dial Plan on the KX-TDA30
Decide on the number range for your extensions.  Renumber any spare extensions, so that they are all in that range.

![](images/TDA30_Extensions.png)

If you want to groups in one range, across all devices, it will first be necessary to delete the "Floating Extension Number" for all Incoming call groups.  Select the column, right click to delete:

![](images/TDA30_Groups.png)

Apply, and then click "Extension List View".

![](images/TDA30_Extension_List.png)

You will see that in the 600 range, 600 and 699 remain.

Navgate to 5.2 - Optional device, and renumber the Pager extension to e.g. 498.

Navigate to 11.1 - Maintenance, and renumber the ISDN remote extension to e.g. 499.

Refresh the Extension List View, and the 600 range should now be empty.

Navigate to 2.6.1 - System, Numbering Plan, Main.  You may now remove unused ranges, e.g. 2XX and 6XX.

You may now re-add e.g. 63X, 64X and 65X.  Apply.

![](images/TDA30_NumberPlan.png)

Click on the "Other PBX Extension" tab, and add the leading number ranges of Asterisk and your other TDA30 systems. e.g.

![](images/TDA30_NumberingPlan_OtherPBX.png)

Return to Groups, Incoming Call Distribution Group, and re-add the necessary groups required, along with a suitable name:

![](images/TDA30_Groups2.png)

Note the group "PSTN to Asterisk".  This will be used to divert the PSTN into Asterisk, when Night or Break Service is selected.

Navigate to Trunk Groups, choose suitable names, and ensure that a suitable COS (Class of Service) is selected for each.

![](images/TDA30_TrunkGroup.png)

Navigate to 10.1 CO Line Settings, and select the appropriate Trunk Group Number for each line.  Choose a suitable name for each one.

![](images/TDA30_CO_Lines.png)

Navigate to 10.2 DIL Table.  Choose an appropriate destination for each incoming call, e.g.

![](images/TDA30_10.2_CO_DIL.png)

Navigate to 9.1 Private Network, TIE Table.

Enter the leading digits for other PBXs in the setup and choose the correct Trunk Group, e.g.

![](images/TDA30_TIE_Table.png)

Own PBX code should be left blank.

---

[Dial plan](./Dialplan.md)

[Automatic Route Selection](./ARS.md) - Required for external Asterisk routing with the IPGW4 card.

[IPGW4 Configuration](./IPGW4.md) 

[Essential Terminology](./Terminology.md) 

[Wiring Notes](./WiringNotes.md) 

[Emergency Considerations](./OtherConsiderations.md) 

[Third Party Resources](../Third%20Party%20Resources/README.md) - Various specifications describing dialling, ringing and other signalling.





