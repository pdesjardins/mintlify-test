---
title: "Assigning prep stations"
id: adminAssigningPrepStationsMenuBuilder
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminAssigningAlcoholLabelingToMenuItemsMenuBuilder.md
previousSectionTitle: "Assigning alcohol labeling to menu items"
nextSectionFile: adminGuide-adminAssigningCourses.md
nextSectionTitle: "Assigning courses"
excerpt: "You use prep stations to route menu items to the appropriate stations in the kitchen..."
keywords: [assigning,prep,stations]
procedures: 0
codeExamples: 0
---

### Assigning prep stations

You use prep stations to route menu items to the appropriate stations in the kitchen for fulfillment. A prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.



> **Important**
> 
> If a menu item does not have any prep stations assigned to it, the Toast platform automatically routes that menu item to all prep stations.


You can set prep stations at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit prep stations from their parent menus. Menu items and subgroups inherit prep stations from their parent menu groups. For more information on inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

To set prep stations for a menu, go to the Kitchen prep section of the menu's details page and select the prep stations to which items ordered from the menu should be routed.

To override the inherited prep stations for a menu group or subgroup, go to the Kitchen prep section of the group's details page, select the link icon next to Prep stations to unlink the configuration, and then select the prep stations from the list.

![Example of a menu group that does not inherit its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-prep-stations.png)

To configure a menu group or subgroup so it inherits its prep stations, select the link icon next to Prep stationsso that the prep station settings are grayed out.

![Example of a menu group that inherits its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-prep-stations.png)

To override the inherited prep stations for a menu item, go to the Kitchen section on its details page, set its Inherit prep stations? setting to No, and then select its prep stations from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered from any menu path*.

![Example of a menu item that does not inherit its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-prep-stations.png)

To configure a menu item to inherit its prep stations, set the Inherit prep stations? setting to Yes.

If you do not have any prep stations configured yet, use the Manage prep stations link to go to the Prep Stations page where you can create them. For more information on creating and using prep stations, see [Adding a prep station](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAddPrepStation) and [Routing with prep stations](adminRoutingToPrepStations.html).

