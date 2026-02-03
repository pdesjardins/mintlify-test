---
title: "Preventing tickets from printing or displaying"
id: adminPreventingTicketsFromPrinting
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
parentSectionTitle: "Item and order routing"
previousSectionFile: adminGuide-adminMonitoringTicketsOtherPrepStations.md
previousSectionTitle: "Monitoring items at other prep stations"
nextSectionFile: adminGuide-platformKOPacingTimingOmitChunkFromSearchIndex.md
nextSectionTitle: "Pacing and timing"
excerpt: "Certain types of items and prep stations do not need to use kitchen tickets to facilitate fulfillment. In these situations, you can prevent tickets from being printed. You can do this by either:"
keywords: ["preventing", "tickets", "printing", "displaying"]
procedures: 0
codeExamples: 0
---

Certain types of items and prep stations do not need to use kitchen tickets to facilitate fulfillment. In these situations, you can prevent tickets from being printed. You can do this by either:

- *Creating a virtual prep station to send items to.* This is useful for specific menu items that do not have to be fulfilled by the kitchen. For example, if a restaurant sells merchandise, employees in the kitchen are not responsible for fulfilling them and do not need to see a kitchen ticket. This method applies to both KDS and printed tickets.


- *Configuring a device to not print its own tickets.* This is useful for specific devices in areas where entering and preparing an order is done by the same employee. For example, a bar employee might input the order on the Toast POS device and make the order, and also fulfill orders made by other employees. In this case, the employee is already aware of the order they created, but needs to be informed about orders coming in from other employees. This method is specific to printed tickets.



#### Routing items to a virtual prep station

For items that do not require any effort to prepare, you can route the items to a virtual **No Print** prep station. The **No Print** prep station can then be used as a destination for items you do not want kitchen tickets for. For example, your restaurant might sell bottled drinks that guests fulfill for themselves. When guests request these items, none of the employees working at actual kitchen prep stations are involved in fulfilling them and do not need to see the associated ticket.

**Procedure 10.19. To set up a virtual prep station and route menu items to it**

1. [Add a prep station](adminAddPrepStation.html).

- Name the prep station No Print.


- Clear the Send to Expediteroption.



> **Note**
> 
> If you have the limited release Send to setting instead, you must select the Prep station only option.



- Do not select any Other Stations.


- Do not select a Ticket Printer.


- Clear the Always Print Ticketsoption.



![The Prep Stations page with a No Print prep station example emphasized.](https://doc.toasttab.com/doc/media/kitchen-noprint-prepstation.png)


2. Verify that all prep station KDS devices do not have the **No Print** prep station [assigned](adminAssignPrepStationKDS.html).


3. [Assign the **No Print** prep station to menu items](adminRoutingToPrepStations.html#adminAssignPrepStationMenu).

![The Advanced Properties page with bottled drink items routed to the No Print prep station.](https://doc.toasttab.com/doc/media/prep_station_no_print.png)


4. Save and publish your changes. The items routed to the **No Print** prep station do not appear on KDS or printed tickets at any of your other prep stations.



#### Configure a device to not print its own tickets

For prep stations in the restaurant where an employee can both take and fulfill guest orders, the employee does not need to reference a printed ticket of the order they entered to fulfill it. Instead, you can configure the Toast POS device to not print tickets for that specific prep station.

For example, an employee at the Bar prep station enters a cocktail order on the prep station's Toast POS device and then makes the cocktail without referring to a printed ticket. With the Toast POS device configured to not print tickets at that prep station, the ticket does not print. Orders sent by other Toast POS devices to the Bar prep station continue to print at that prep station, and alert the Bar employee of items sent from other Toast POS devices.



> **Note**
> 
> This configuration only prevents prep stations printers from *printing* kitchen tickets. Orders sent from the configured Toast POS device continue to show on the prep station KDS device.


**Procedure 10.20. To set up a Toast POS device to not print tickets at a specific prep station**

1. [Add the printer](adminAddKitchenPrinter.html).


2. [Add the prep station](adminAddPrepStation.html).

- Name the prep station.


- Set the Send to Expediter option as needed.



> **Note**
> 
> You may have the limited release Send to setting instead.



- Select Other Stations as needed.


- Specify the Ticket Printer that you added in Step 1.


- Select Always Print Tickets. This ensures that orders sent from other devices will print tickets.




3. [Assign the prep station to menu items](adminRoutingToPrepStations.html#adminAssignPrepStationMenu).

![The Advanced Properties page with Specialty items routed to the Bar prep station.](https://doc.toasttab.com/doc/media/prep_station_bar.png)


4. Save and publish your changes.


5. On the prep station Toast POS device that you do not want to print tickets from, [access the Toast POS Device Setup screen](adminConfigureDevice.html).


6. In the Kitchen Setup section, select Non-Printing Prep Stations. The Non-Printing Prep Stations screen opens.


7. Select the prep station's name to prevent tickets from printing to that prep station if they are ordered on this device.

![The Device Setup page showing the Bar prep station selected as a non-printing prep station.](https://doc.toasttab.com/doc/media/kitchen-device-setup-non-printing-prep-stations-setting.png)


8. Select Continue. The Toast platform saves the prep station configuration and stops printing the selected prep station tickets for orders sent by this device. Orders sent from other devices continue to print.



