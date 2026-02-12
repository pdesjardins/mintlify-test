---
title: "Adding a prep station"
id: adminAddPrepStation
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration"
previousSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
previousSectionTitle: "Kitchen configuration"
nextSectionFile: adminGuide-platformKDSCreatingAssemblyLines.md
nextSectionTitle: "Creating an assembly line"
excerpt: "When you add a prep..."
keywords: ["adding", "prep", "station"]
procedures: 1
codeExamples: 0
---

When you add a prep station, you have the option of choosing whether items are also sent to the expediter using the Send to Expediter setting. With this setting, items are sent to both the prep station and the expediter. This applies to both KDS and printed tickets.



> **Note**
> 
> The limited release Send to setting allows you to choose whether items for that prep station go to that prep station, the expediter, or both. The options are:
- Prep station and expediter: Items are sent to the prep station and the expediter.


- Expediter only: Items are only sent to the expediter. Items are not sent to the prep station.

If you choose to require fulfillment at prep station KDS devices before expediter KDS devices using the Sequenced KDS fulfillment setting, items assigned a prep station with the Send to setting set to Expediter only do not require fulfillment at prep stations, because they are not sent to the prep station at all.

They also do not appear as an option when assigning prep stations to a KDS device. For more information, see [Assigning a KDS device to a prep station](adminGuide-adminAssignPrepStationKDS).


- Prep station only: Items are only sent to the prep station. Items are not sent to the expediters.





When you add a prep station, you also assign a printer to it.

- If you use kitchen printers, assign kitchen printers to each prep station when you add the prep station.


- If you use KDS devices, assign a single, backup printer to every prep station.



To add a prep station, you must have the 6. Web Setup \> 6.2 Kitchen / Dining Room Setup access permission.

**Procedure 10.1. To add a prep station**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Kitchen \> Kitchen stations \> Prep stations.


3. Select the + Add button. The Toast platform adds a row to the interactive grid.


4. Enter an identifying name for the prep station.


5. To print or display the prep station's tickets at an expediter printer or KDS, check Send to Expediter.

For example, your expediter needs the tickets for your Hot and Cold stations, but not for your Bar station. You check Send to Expediter for the Hot and Cold prep stations, but not for the Bar. For more information, see [Configure the expediter workflow](adminGuide-adminUsingExpo#adminConfigureExpediter).



> **Note**
> 
> If you have the limited release Send tosetting, you will see this instead of the Send to Expediter setting. Choose to send items to prep station, expediter, or both.



6. To monitor items sent to another station or stations by printing them on kitchen tickets, select the Other Stations. This option affects printed kitchen tickets only. For more information, see [Monitoring items at other prep stations](adminGuide-adminMonitoringTicketsOtherPrepStations).


7. Select the kitchen printer that you want to print this prep station's tickets.

- If the prep station uses a [KDS](adminGuide-adminRoutingOrdersKitchen), assign the backup printer.


- If the prep station is a [virtual or "no print" prep station](adminGuide-adminPreventingTicketsFromPrinting#adminNoPrintPrepStation), do not select a printer.




8. If the prep station primarily uses a kitchen printer, check Always Print Tickets. Every ticket sent to this prep station prints at the specified printer.

If the prep station uses a KDS, clear Always Print Tickets. Tickets print only when the system is in offline mode.


9. Save and publish your changes.



Repeat these steps to add your other prep stations.

After you set up your prep stations, you can [assign KDS devices](adminGuide-adminAssignPrepStationKDS) to them (if applicable) and [add them to your menus](adminGuide-adminRoutingToPrepStations#adminAssignPrepStationMenu).

