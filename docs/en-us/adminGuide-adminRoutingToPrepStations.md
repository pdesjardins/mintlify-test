---
title: "Routing with prep stations"
id: adminRoutingToPrepStations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
parentSectionTitle: "Item and order routing"
previousSectionFile: adminGuide-platformKitchenRoutingOverview.md
previousSectionTitle: "Routing overview"
nextSectionFile: adminGuide-platformKDSRoutingUsingAssemblyLines.md
nextSectionTitle: "Routing using assembly lines"
excerpt: "For..."
keywords: ["routing", "prep", "stations"]
procedures: 0
codeExamples: 0
---

For an efficient order fulfillment workflow, assign every menu item and modifier in your menus to a prep station. In the Toast platform, a prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.

After you [add your prep stations](adminGuide-adminAddPrepStation), assign them to your menus, menu groups, items, and modifiers, so that every item in an order can be sent immediately to the correct prep station for fulfillment. For items that require preparation at several prep stations, you can assign multiple prep stations.

If you assign a prep station to a menu or menu group, the Toast platform assigns that prep station to all of the items and modifiers in that menu or group. For example, you assign your "online" menu to a prep station dedicated to fulfilling those orders, and your "in store" menu(s) to different prep stations. You can then override this default assignment as needed for individual menu items and modifiers.

Once the item is sent from the front of house, the item can either appear on a KDS device, print from a kitchen printer, or both. Whether the item is also sent to expediters depends on the prep station Send to expediter setting. Whether or not the item appears on a KDS device or prints from the kitchen printer also depends on your prep station settings.



> **Note**
> 
> The limited release Send to setting allows you to choose whether a prep station sends its items to the prep station, expediter, or both. For more information, see [Sending items to prep stations, expediters, or both](adminGuide-adminRoutingToPrepStations#platformKitchenSendingToPrepStationExpediterBoth).


If you choose to have a prep station send to prep stations, the item displays on the prep station KDS device, prints at the prep station kitchen printer, or both. For example, your kitchen has *Cold* and *Hot* prep stations, so you add a prep station for each one, along with another prep station for *Dessert*. Once an order is sent from the front of house, the item displays on a KDS or prints from a kitchen printer at the prep station or stations assigned to it.

![A workflow diagram of an order going from Front of House to three prep stations: Cold, Hot, and Dessert.](https://doc.toasttab.com/doc/media/prep_station_workflow_basic.png)

If your restaurant has a bar, you might also add a prep station for the bar so that drink orders can be routed to the bartenders for fulfillment, and not to the kitchen.

## Sending items to prep stations, expediters, or both



> **Note**
> 
> This feature is in limited release.


Depending on how you want to route items assigned to certain prep stations, you can choose whether to have a configured prep station send items to the prep station KDS device or printer, the expediter KDS device or printer, or to both the prep station and expediter KDS device or printer. For example, a prep station that is outside of the kitchen does not need to send items to the expediter, such as a Bar. The items at the Bar prep station do not need to go to the expediter before being delivered to guests. On the other hand, some items only need to be added at the expediter, such as utensils or sauces. These items do not need a prep station because they are added at the expediter. For situations like these, you can use the Send to setting to send items assigned to these prep stations to specific station types.

**Procedure 10.12. To assign prep stations to send to specific station types**

1. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend)


2. Choose Kitchen \> Kitchen stations \> Prep stations.


3. Under the Send to column, select where to send prep station items to. The options include:

- Prep station and expediter: Items assigned to this prep station are sent to the prep station and the expediter.


- Expediter only: Items assigned to this prep station are only sent to the expediter. Prep stations with this setting cannot be assigned to prep station KDS devices.


- Prep station only: Items assigned to this prep station are only sent to the prep station.




4. Save and publish your changes.





> **Note**
> 
> If you require fulfillment at both prep stations and expediters using the Sequenced KDS fulfillment setting, items only need to be fulfilled where they were sent to. For example, if you choose to send an item to only prep stations, you cannot fulfill the item at the expediter because it was never sent to expediter.


## Multiple prep stations for an item

For individual items that require work at multiple prep stations, you can choose to assign more than one prep station to it. For example, a Caesar Chicken Salad item is sent to both the *Cold* prep station and the *Grill* prep station. For more information on how the item is fulfilled at multiple prep stations on the KDS, see [Understanding item fulfillment](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS).

You can also configure your kitchen tickets to show which other prep stations are working on the item or order. For more information, see [Monitoring items at other prep stations](adminGuide-adminMonitoringTicketsOtherPrepStations).

## Assigning prep stations to menu entities

The following procedure is for assigning prep stations to multiple [menu entities](adminGuide-adminMenuHierarchy) at once. You can also choose to assign prep stations to each menu entity while creating it. For more information about assigning prep stations while creating a single menu entity, see [Assigning prep stations](adminGuide-adminAssigningPrepStationsMenuBuilder).



> **Note**
> 
> You must have the 4. Restaurant Admin \> 4.5 Edit Full Menu permission to assign prep stations to menu entities.


**Procedure 10.13. To assign prep stations to menu entities**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus \> Bulk management \> Advanced properties. The Advanced Propertiespage with an interactive table with rows for each restaurant menu opens.


3. Expand the menu to show the menu groups in a menu. Continue to expand to see menu items, modifier groups, and modifiers.


4. Use the Show/Hide dropdown list above the table to select Prep Stations. A Prep Stations column appears on the table.


5. In the Prep Stations column, you can assign a prep station to an entire menu, a menu group, a menu item, or a modifier option. To assign a prep station, click in the Prep Stations cell for that menu and then select the prep station from the drop down list.

![A screenshot of a the Advanced Properties page with a column for prep station assignments.](https://doc.toasttab.com/doc/media/item_routing_assign_prep_station.png)


6. Save and publish your changes.



