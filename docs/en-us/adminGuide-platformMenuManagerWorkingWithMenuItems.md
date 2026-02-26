---
title: "Working with menu items"
id: platformMenuManagerWorkingWithMenuItems
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerWorkingWithMenuGroups.md
previousSectionTitle: "Working with menu groups and subgroups"
nextSectionFile: adminGuide-platformWorkingWithModifierGroupsMenuManager.md
nextSectionTitle: "Working with modifier groups"
externalReferences: [https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057#:~:text=Since%20Toast%20is%20a%20cloud,Quick%20Edit%20Mode%2C%20select%20OK., https://central.toasttab.com/s/article/Course-Firing-Options, https://central.toasttab.com/s/article/Sales-Reports-Overview, https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577, https://central.toasttab.com/s/article/Getting-Started-with-Toast-Online-Ordering-Pro, https://central.toasttab.com/s/article/Get-Started-With-the-Branded-Mobile-App, https://central.toasttab.com/s/article/How-to-Send-an-Invoice, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events, https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering, https://central.toasttab.com/s/article/Shallow-and-Deep-Copying-Menu-Items-and-Modifiers]
excerpt: "This section provides information about working with menu items in the menu manager."
keywords: ["working", "menu", "items"]
procedures: 0
codeExamples: 0
---

This section provides information about working with menu items in the menu manager.

## Adding a new menu item

Use the procedure below to add a new menu item.



> **Note**
> 
> To reduce the number of menu items you have to manage, [add existing menu items](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerAddingAnExistingMenuItem) whenever possible instead of creating new ones.


For multi-location restaurants:

- Newly created menu items inherit the target and owner of their parent menu group by default. For more information, see [Defaults for targets and owners](adminGuide-platformMenuManagerMenuAndMultiLocationRestaurants#platformMenuManagerDefaultsForTargetsAndOwners).


- You must have the Edit Full Menupermission to the owner of a menu group in order to add a new menu item to it.



**Procedure 8.59. To add a new menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate and expand the menu group you want to add an item to.


6. Select + Add item and enter a name for the menu item. A dropdown list appears that has a Create new option followed by a list of any existing menu items that match the text you entered.

![Example of the dropdown for adding a new menu item.](https://doc.toasttab.com/doc/media/menu-manager-add-new-item.png)


7. After you are done entering the item name, select the Create new option (alternatively, you can press the Enter key). A side panel opens for the menu item and you are automatically scrolled to the Pricing section for the new menu item where you can quickly enter a price for the new item.

If you need to specify any other menu item configurations, scroll to the appropriate section of the side panel and make your changes. See the other sections in [Working with menu items](adminGuide-platformMenuManagerWorkingWithMenuItems) for more details on additional configurations.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Adding an existing menu item

To reduce the number of menu items you have to manage, add existing menu items whenever possible instead of creating new ones.



> **Note**
> 
> If you have a multi-location restaurant, you cannot add existing menu items in Full menu view. You must use the classic page for the parent menu group instead.


When reusing a menu item in multiple menu groups, keep in mind that:

- When you edit the menu item, it is edited for all the menu groups that use it.


- When you [remove the menu item](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerRemovingAMenuItemFromAMenuGroup) from one of the menu groups, the other menu groups continue to use it.


- When you [archive a menu item](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerArchivingAMenuItem), it is removed from all menu groups that use it.



**Procedure 8.60. To add an existing menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate and expand the menu group you want to add an existing item to.


5. Select + Add item and enter a name for the menu item. A dropdown list appears that has a Create new option followed by a list of any existing menu items that match the text you entered.

![Example of the dropdown list for adding an existing menu item.](https://doc.toasttab.com/doc/media/menu-manager-add-existing-menu-item.png)


6. Select the existing item you want to add. Alternatively, use the down arrow to highlight the existing item and then press the Enter key. Your changes are automatically saved.


7. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Renaming a menu item

Follow the procedure below to rename a menu item.

**Procedure 8.61. To rename a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the menu item's name to open its side panel.


7. In the Item details section, enter the new name in the Menu item name field.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Reordering menu items

Your Toast ordering channels display your menu items in the order you see them in the Full menu view. You can reorder your menu items so they appear in the order you want them to.

You can reorder menu items within a single menu group. You cannot move a menu item from one menu group to another.



> **Note**
> 
> If you have a multi-location restaurant, you cannot reorder menu items in Full menu view. You must use the classic page for their parent menu group instead.


**Procedure 8.62. To reorder a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to reorder.


5. Select the menu item's reorder icon and drag it to its new location. Your changes are automatically saved.

![The location of the reorder icon for a menu item you want to move.](https://doc.toasttab.com/doc/media/menu-manager-menu-item-reorder-button.png)


6. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Removing a menu item from a menu group

You can remove a menu item from a menu group using the Remove menu item option from the overflow menu. When you remove a menu item from a menu group, the item no longer appears in that menu group, but the item remains in your Toast Web database and can still be added to or used by other menu groups.

If the menu item belongs to multiple menu groups, removing the item from one group has no effect on the others. They continue to use the menu item.

For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a menu item's parent in order to remove the menu item. For example, consider a Sandwiches menu group that contains a Turkey Club menu item. You must have Edit Full Menu permission to the owner of the Sandwiches menu group to remove the Turkey Club menu item from it.


- If the parent menu group of the menu item you want to remove is versioned, you must pick the version you want to remove the menu item from. The menu item is removed from that version only. The other versions continue to use the menu group.


- If the menu item you want to remove is versioned, removing the menu item from its parent removes all versions of the menu item from the parent.





> **Note**
> 
> To remove a menu item from *all* menu groups that use it, you must archive it. For more information, see [Archiving a menu item](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerArchivingAMenuItem).


**Procedure 8.63. To remove a menu item from a menu group**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to remove.


6. Select the menu item's overflow menu (...) and choose Remove menu item. Your changes are automatically saved.

![The location of the overflow menu for a menu item you want to remove.](https://doc.toasttab.com/doc/media/menu-manager-menu-item-overflow-button.png)


7. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Archiving a menu item

You can archive a menu item to hide it from your Toast ordering channels. When archiving a menu item, keep in mind that:

- An archived menu item is removed from *all*the menu groups that use it.


- If the menu item is reused as a modifier, those modifiers are also archived.



For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a menu item version to archive that version.


- If you archive a version of a menu item, only that version is archived. The other versions continue to be available.





> **Note**
> 
> To undo a menu item archive, go to the Menus &gt; Bulk management &gt; Items database page in Toast Web. Select the Items tab and then choose Show Archived. Select the checkbox for the menu item you want to restore and choose Restore.


**Procedure 8.64. To archive a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to archive.


6. Select the menu item's overflow menu (...) and choose Archive menu item.

![The location of the overflow menu for a menu item you want to archive.](https://doc.toasttab.com/doc/media/menu-manager-menu-item-overflow-button.png)


7. To confirm, select Archive in the Archive the item dialog. Your changes are automatically saved.


8. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Setting stock status and count for a menu item

You can set the stock status for menu items to indicate whether a menu item is in stock, out of stock, or in limited supply. Out of stock items are displayed to your guests, however, they are marked as "out of stock" and cannot be ordered.

A menu item must be saved at least once before you can update its stock status.

**Procedure 8.65. To set stock status for a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel, then select the stock dropdown list.

![The location of the full screen icon for the side panel.](https://doc.toasttab.com/doc/media/menu-manager-stock-dropdown.png)


7. Set the stock status:

- In stock: The menu item is in stock and can be ordered.


- Out of stock: The menu item is out of stock. Your guests can see the menu item, marked as "out of stock", but they cannot order it.


- If the menu item is in limited supply, you can set a specific quantity for the item by typing a number into the Enter quantity field and pressing Enter. The Toast platform automatically marks the item as "out of stock" when the last unit is sold.

The stock amount you set appears next to the menu item's name, as shown below:

![The location of the stock amount on a menu item details page.](https://doc.toasttab.com/doc/media/menu-manager-set-stock-quantity.png)

The Toast platform updates the stock amount when you initially open the menu item's details page to reflect any units that have been sold since the stock amount was set. However, the stock amount *is not updated after the menu item details page is initially loaded*. This means that, if units of the menu item are sold while you are viewing the menu item's details page, you won't see those changes to the stock amount until you refresh the menu item's details page.

Stock changes that you make are immediately applied and there is no need to save or publish them.





## Editing a menu item's price

You can edit menu items that are *priced individually* from either Full menu view or Items view.



> **Note**
> 
> Items that inherit their prices from a parent menu group are not editable in the menu manager. You must edit these items in their [classic menu item details pages](adminGuide-adminMenuManagerAndTheClassicMenuDetailsPages) instead.


Full menu view and Itemsview have different pricing capabilities:

- In Full menu view, you can edit items that use the Base, Size, or Open pricing strategy. You must [manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) pricing changes you make in Full menu view. Full menu view does not support scheduled publishing.


- In Items view, you can edit items that use the Base, Size, Menu-specific or Location-specific pricing strategy. You can manually publish pricing changes you make in Items view or [schedule them for future publishing](adminGuide-platformPublishingMenuManagerChanges).



Follow the procedure below for the view you want to use, [Full menu](adminGuide-platformMenuManagerWorkingWithMenuItems#platformToEditAMenuItemsPriceInFullMenuView) view or [Items](adminGuide-platformMenuManagerWorkingWithMenuItems#platformToEditAMenuItemsPriceInItemsView)view.

**Procedure 8.66. To edit a menu item's price in Full menu view**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel, then scroll to the Pricing section.


7. In the Pricing section, enter a price for the menu item:

- To enter a base price, choose the Base pricing strategy and enter a price in the Price field.


- To enter size prices, choose the Sizepricing strategy and enter a price for each size.

Optionally, you can modify the names of the sizes and the number of sizes the item has.

You cannot save a menu item if it has empty size price rows, so delete any empty rows after you are done entering your prices.


- To use an open price, choose the Openpricing strategy. For items that have a daily market price, Toast support recommends configuring the item with an open price and then using [Quick Edit](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057#:~:text=Since%20Toast%20is%20a%20cloud,Quick%20Edit%20Mode%2C%20select%20OK.) mode on a Toast POS device to set a price for the item each day. This ensures that the price is accurate and employees don't have to enter a price every time the item is ordered.

Note that open prices are not supported for Toast Online Ordering, so you should not use an open price for a menu item that will appear on your Toast Online Ordering website.





> **Note**
> 
> You can use the classic menu item details page to set other advanced pricing strategies for a menu item, for example, time-specific prices. To create a menu item with one of these other advanced prices, you must first create the menu item with a base price, save it, and then edit it to add the advanced price. For more information, see [Using advanced pricing strategies for menu items](adminGuide-platformMenuManagerWorkingWithMenuItems#adminUsingAdvancedPricingStrategiesForMenuItemsMenuManager).



8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



**Procedure 8.67. To edit a menu item's price in Items view**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Items.


4. Use the [search field](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerSearchingForMenuEntities) or the [filtering controls](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringMenuEntities) to refine the list of menu items.


5. Make your price edits:

- To edit a menu item with a base price, enter the new price in the Price column.


- To edit a menu item with a size, menu-specific, or location-specific price, expand its row and enter the new price in the Price column.



> **Note**
> 
> Items view only allows you to edit size prices that are already defined on a menu item's details page. If you need to add a price for another size, you must add the size's price on the details page first, before it is visible and available for editing in Items view. The same is true for menu-specific and location-specific prices. If you need to add a price for another menu or location, you must add the price on the details page first. For more information on adding size prices, see [Configuring size pricing on menu groups and menu items](adminGuide-adminSizePrice#adminConfiguringSizePricingOnMenuGroupsAndMenuItems). For more information on adding menu-specific prices, see [Menu-specific price](adminGuide-adminMenuSpecificPrice). For more information on adding location-specific prices, see [Enabling and setting location-specific prices](adminGuide-adminEnablingAndSettingLocationSpecificPrices).




> **Note**
> 
> If a menu item is versioned, all of its versions that use location-specific pricing use the *same location-specific prices*. In this situation, the versioned menu item appears on multiple rows on the Items view, one row per version, and the location-specific prices associated with the versions are identical. If you edit the location-specific prices for one version, they are edited for all versions. For more information, see [Location-specific prices and versions](adminGuide-adminLocationSpecificPricesAndVersions).





6. Continue reading the [Publishing menu manager changes](adminGuide-platformPublishingMenuManagerChanges) section to understand how to make your menu changes available to employees and guests.



> **Important**
> 
> Items view offers additional workflows for saving and publishing your pricing edits that are different from other configuration pages in Toast Web, including the ability to create a change set that publishes your changes at a later date and time. In Items view, you *either* select Scheduleto create a change set *or*Save to save your changes immediately. If you select Save, your changes are saved immediately and you will not be able to create a change set. Do not select Save in Itemsview until you fully understand the publishing workflows described in [Publishing menu manager changes](adminGuide-platformPublishingMenuManagerChanges).




## Adding images to menu items

Toast support recommends adding images to your menu items to make them more appealing on your Toast Online Ordering website. Images must be in .jpg and .png format and no larger than 5MB.

**Procedure 8.68. To specify an image for a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel.


7. In the Item details section, select Add image, locate the image you want to use, and select Open. Alternatively, you can drag an image file to the gray box.


8. To remove the image you specified and replace it with a different one, select the Remove image button and then repeat the preceding step.


9. Select Save.


10. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Adding a menu item description

Use the procedure below to add a description to a menu item.

**Procedure 8.69. To add a menu item description**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel.


7. In the Item details section, enter a description in the Description field.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Assigning a POS button name and color

You can customize the names and colors of the buttons employees see in the Toast POS app for the various menu entities:

- For menus, menu groups, subgroups, menu items, and modifier groups, go to the details section of the menu entity's details page. For example, for a menu, go to Menu details.

Enter a name in the POS name field. To specify a button color, select the Button coloroption and then select a color from the color palette.


- For modifiers, go to [the Edit modifier dialog](adminGuide-adminAddingModifierGroupsAndModifiers#platformEditingAModifiersDetails) for the modifier, select the POS button color option and then select a color from the color palette. Modifiers do not have a POS name. The Toast POS app displays the Modifier name.



By default, the POS name field is empty and the button color is set to white.

## Specifying calories for a menu item

Use the procedure below to specify the calorie count for a menu item.

**Procedure 8.70. To specify calories for a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel.


7. In the Item details section, enter the calories in the Calories field.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Specifying a PLU or SKU for a menu item

Use the procedure below to specify a PLU or SKU for a menu item.

**Procedure 8.71. To add a PLU or SKU for a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel.


7. In the Item details section, enter a PLU or SKU in the PLU or SKUfield.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Assigning alcohol labeling to menu items

Each menu item has a Does this item contain alcohol? setting, under the Item detailssection in the side panel. This setting identifies whether the menu item contains alcohol in cases where orders containing alcohol require additional handling. For example, local laws might require an ID check or prevent accrual of loyalty points.



> **Important**
> 
> Once an option is initially selected, you can only choose from the Yes or Nooptions.


Identifying alcoholic items makes it easier for online ordering partners to comply with alcohol delivery laws and enables restaurants to include alcohol with takeout and delivery orders.

**Procedure 8.72. To assign alcohol labeling to a menu item**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel.


7. In the Item details section, set the Does this item contain alcohol? setting. Select Yes to indicate that the item contains alcohol and requires additional handling. Select No to indicate that the item does not require additional handling. For example, choose Yes for items such as Red Wine and Beer, but No for items such as Bananas Foster or Rum Cake.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Determining where a menu item is used

You can use the Found in section of a menu item's details page to see which menus a menu item is included in and the path within each menu that an employee or guest must follow to get to the menu item. To quickly go to a menu or menu group in a menu path, select its name.

For example, the menu item in the illustration below belongs to two menu paths: Lunch &gt; Sandwiches and Dinner &gt; Sandwiches.

![An example of the Found in section of a menu item details page, showing the two menu paths for the item.](https://doc.toasttab.com/doc/media/menu-builder-found-in.png)

## Specifying a different name and color for KDS devices and kitchen tickets

You can specify a kitchen name for a menu item. The kitchen name is used instead of the POS name on KDS devices and printed kitchen tickets. You can also specify a KDS color for a menu item. The KDS color is used instead of the POS color on KDS devices.

**Procedure 8.73. To specify a different name and color for KDS devices and kitchen tickets**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. Select the item to see its details in the side panel, then scroll to the Kitchen section.


7. Enter a name in the Kitchen name field. To specify a button color, select the KDS coloroption and then select a color from the color palette.


8. Select Save.


9. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Adding a recipe view



> **Note**
> 
> This feature is in limited release.


You can add a recipe to a menu item that can then be viewed on KDS devices. Recipe files must:

- Use either .jpg or .png format.


- Be between 100 kilobytes and 1.5 megabytes.



Toast support also recommends using a resolution that allows text to be readable on a standard screen and the image orientation be in portrait mode. For information about how to access the recipe on KDS devices, see [Viewing recipes](adminGuide-platformKDSOverview#platformKitchenKDSViewRecipes).

**Procedure 8.74. To add a recipe to a menu item for viewing on KDS devices**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


5. Select the item to see its details in the side panel, then scroll to the Kitchen section.


6. Go to the Recipe View section and select Upload Recipe. The Upload Recipe dialog opens.

![The Upload Recipe dialog when adding a recipe to a menu item.](https://doc.toasttab.com/doc/media/menu-manager-upload-recipe-dialog.png)


7. Optionally, edit the Recipe Name. The Toast platform automatically names the recipe with the menu item name, followed by "Recipe."


8. Select Add image, locate the image you want to use, and select Open. Alternatively, you can drag an image file to the gray box.



> **Note**
> 
> You can have only one recipe for each menu item.



9. To remove the image you specified and replace it with a different one, select the Remove image button and then repeat the preceding step.


10. Select Upload recipe. The Upload Recipe dialog closes.


11. Select Save.


12. Optionally, if you do not want the recipe available on KDS devices, return to the Recipe View section, turn off the Active on KDS toggle next to the recipe name, and select Save.

![The Recipe View section of a menu item, with the recipe toggled to be active on KDS devices.](https://doc.toasttab.com/doc/media/menu-manager-recipe-view-active-toggle.png)


13. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



## Assigning prep stations

You use prep stations to route menu items to the appropriate stations in the kitchen for fulfillment. A prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.



> **Important**
> 
> If a menu item does not have any prep stations assigned to it, the Toast platform automatically routes that menu item to all prep stations.


You can set prep stations at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit prep stations from their parent menus. Menu items and subgroups inherit prep stations from their parent menu groups. For more information on inheritance, see [Understanding inheritance](adminGuide-platformUnderstandingInheritance).

To set prep stations for a menu, go to the Kitchen prep section of the menu's details page and select the prep stations to which items ordered from the menu should be routed.

To override the inherited prep stations for a menu group or subgroup, go to the Kitchen prep section of the group's details page, select the link icon next to Prep stations to unlink the configuration, and then select the prep stations from the list.

![Example of a menu group that does not inherit its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-prep-stations.png)

To configure a menu group or subgroup so it inherits its prep stations, select the link icon next to Prep stationsso that the prep station settings are grayed out.

![Example of a menu group that inherits its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-prep-stations.png)

To override the inherited prep stations for a menu item, go to the Kitchen section on its details page, set its Inherit prep stations? setting to No, and then select its prep stations from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered from any menu path*.

![Example of a menu item that does not inherit its prep stations.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-prep-stations.png)

To configure a menu item to inherit its prep stations, set the Inherit prep stations? setting to Yes.

If you do not have any prep stations configured yet, use the Manage prep stations link to go to the Prep Stations page where you can create them. For more information on creating and using prep stations, see [Adding a prep station](adminGuide-adminAddPrepStation) and [Routing with prep stations](adminGuide-adminRoutingToPrepStations).

## Assigning courses

You use courses to manage the firing of tickets to the kitchen for fulfillment.

You can set courses at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their course from their parent menus. Menu items and subgroups inherit their course from their parent menu groups. For more information on inheritance, see [Understanding inheritance](adminGuide-platformUnderstandingInheritance).

To set the course for a menu, go to the Kitchen prep section of the menu's details page and select the course.

To override the inherited course for a menu group or subgroup, go to the Kitchen prep section of the group's details page, select the link icon next to Course to unlink the configuration, and then select the course from the list.

![Example of a menu group that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-course.png)

To configure a menu group or subgroup so that it inherits its course, select the link icon next to Course so that the course setting is grayed out.

![Example of a menu group that inherits its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-course.png)

To override the inherited course for a menu item, go to the Kitchen section on its details page, set its Inherit course? setting to No, and then select its course from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-course.png)

To configure a menu item so that it inherits its course, set the Inherit course? setting to Yes.

If you do not have any courses configured yet, use the Manage courses link to go to the Courses page where you can create them. For more information on creating courses, see [Creating courses](adminGuide-adminAssigningCourses#platformGuideCreatingCoursesMenuBuilder). For more information on using courses, see this [Toast Central article](https://central.toasttab.com/s/article/Course-Firing-Options).

### Creating courses

While you can assign courses in the menu builder, you must use the classic Courses page to create the courses themselves.

**Procedure 8.75. To create courses**

1. Go to the Courses page:

If you are viewing a menu item in the menu builder, select Kitchen. If you are viewing a menu, menu group, or subgroup in the menu builder, select Kitchen prep. In the Related settingssection, select Manage courses.

Alternatively, you can do the following:

- [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend).


- Switch to the restaurant you want to create courses for.


- Select Kitchen &gt; Pacing &gt; Courses.




2. Select + Add to add a row to the Courses table.


3. Enter a name for the course.


4. Repeat steps 2 and 3 for any additional courses you want to create.


5. Select Save.



## Assigning sales categories

The Sales Summary and other Toast reports use sales categories to create a breakdown of your sales, organized by sales category, for example, Food, Drinks, Retail, and so on.

Some points to keep in mind when using sales categories:

- If you change the sales category for a menu entity, those changes are reflected in future sales reports but existing reports remain unchanged.


- While highly recommended for a better reporting experience, sales categories are optional. If you select None selected from the Sales categorymenu, no sales category is applied to the menu entity.



For information about the reports that use sales categories, see these Toast Central articles:

- [Sales Reports Overview](https://central.toasttab.com/s/article/Sales-Reports-Overview)


- [Menu Reports Overview](https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577)



You can set sales categories at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their sales category from their parent menus. Menu items and subgroups inherit their sales category from their parent menu groups. For more information on inheritance, see [Understanding inheritance](adminGuide-platformUnderstandingInheritance).

To set the sales category for a menu, go to the Reporting section of the menu's details page and select the category from the Sales category dropdown list.

To override the inherited sales category for a menu group or subgroup, go to the Reporting section of the group's details page, select the link icon next to Sales category to unlink the configuration, and then select the sales category from the list.

![Example of a menu group that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-sales-category.png)

To configure a menu group or subgroup so that it inherits its sales category, select the link icon next to Sales categoryso that the course setting is grayed out.

![Example of a menu group that inherits its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-sales-category.png)

To override the inherited sales category for a menu item, go to the Reporting section on its details page, set its Inherit sales category? setting to No, and then select its sales category from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-sales-category.png)

To configure a menu item so that it inherits its sales category, set the Inherit sales category? setting to Yes.

If you do not have any sales categories configured yet, use the Manage sales categories link to go to the Sales categories page where you can create them. For more information on creating sales categories, see [Creating sales categories](adminGuide-adminAssigningSalesCategories#platformCreatingSalesCategoriesMenuBuilder).

### Creating sales categories

While you can assign sales categories in the menu builder, you must use the classic Sales Categories page to create the sales categories themselves.

**Procedure 8.76. To create sales categories**

1. Do one of the following to navigate to the Sales categories page:

On the details page for a menu, menu group, or menu item, select Reporting. In the Related settings section, select Manage sales categories.

Alternatively, you can:

- [Log in to Toast Web](adminGuide-adminAccessToastAdminBackend).


- Switch to the restaurant you want to create courses for.


- Select Menus &gt; Settings &gt; Sales categories.




2. Select + Add to add a row to the Sales Categories table.


3. Enter a name and a description for the sales category.


4. Repeat steps 2 and 3 for any additional sales categories you want to create.


5. Select Save.



## Assigning tax rates and tax behavior

During the on-boarding process, you specify the tax rates that apply to your restaurant location. By default, these tax rates are inherited by any menus you create for the restaurant. According to the rules of menu inheritance, the tax rates also flow down to your menu groups, subgroups, and menu items in the following ways:

- Menu groups inherit their tax rates from their parent menus.


- Menu items and subgroups inherit their tax rates from their parent menu groups.



You can override tax rates on individual menus, menu groups, subgroups, or menu items as needed.

In addition to tax rates, Toast Web includes two tax behavior settings that allow you to specify that taxes are included in a menu item's price and takeout orders are exempt from taxes. You can set the tax behavior settings at the menu, menu group, subgroup, or menu item level and they follow the same rules of inheritance as tax rates. You can override these settings as needed on individual menu entities.

For more information on menu inheritance, see [Understanding inheritance](adminGuide-platformUnderstandingInheritance).

The following sections provide instructions for setting tax rates and behavior. They also provide more information about the tax behavior settings.

- [Setting tax rates and tax behavior](adminGuide-adminAssigningTaxRatesInMenuBuilder#platformSettingTaxRatesAndTaxBehavior)


- [Understanding tax inclusion](adminGuide-adminAssigningTaxRatesInMenuBuilder#platformUnderstandingTaxInclusion)


- [Understanding takeout tax exception](adminGuide-adminAssigningTaxRatesInMenuBuilder#platformUnderstandingTakeoutTaxException)



### Setting tax rates and tax behavior

To override the inherited tax rates for a menu, menu group, or subgroup, go to the Taxes section of the entity's details page, select the link icon next to Tax rates to unlink the configuration, and then select the tax rates from the list. To override the Calculate prices with tax included or Takeout exception setting, select its link icon to unlink the configuration and then configure the setting as needed.

![Example of a menu group that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-tax-settings.png)

To configure a menu, menu group, or subgroup so it inherits its tax rates, select the link icon next to Tax ratesso the tax rates setting is grayed out. To inherit the Calculate prices with tax included or Takeout exception setting, select its link icon so that the setting is grayed out.

![Example of a menu group that inherits its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-tax-settings.png)

To override the inherited tax rates for a menu item, go to the Tax settings section on its details page, set its Inherit tax rates? setting to No, and then select the tax rates from the list. To override the Tax inclusion or Takeout tax exception setting, set Inherit tax inclusion? or Inherit takeout tax? to No and then configure the setting as needed. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-tax-settings.png)

To configure a menu item so that it inherits its tax rates, set the Inherit tax rates? setting to Yes. To inherit the Tax inclusion or Takeout tax exceptionsetting, set the Inherit tax inclusion? or Inherit takeout tax? setting to Yes.

If you do not have any tax rates configured yet, you see a Manage tax rates link that you can select to go to the Tax rates page where you can create them. For more information on creating tax rates, see [Taxes overview](adminGuide-adminTaxesOverview).

### Understanding tax inclusion

When tax is included in a menu item's price, the guest pays the price you have set and any applicable taxes are taken out of that price, instead of being added to it. Use this option when you want a guest's check total to be a round number. This eliminates the need for employees to deal with coins and makes tipping simpler to calculate. It can, however, decrease net revenue if the price you set does not account for applicable taxes.

To better understand the effect of tax inclusion on your revenue, consider an item that has a price of $10 and a tax rate of 7%. When tax is included, the Toast platform calculates a price and tax combination that equals the price you have set but also covers any applicable taxes. In this case, the guest pays $10 ($9.35 for the item and $0.65 for the tax) and your revenue is $9.35:

- $9.35 item price x .07 tax rate = $0.65 tax


- $9.35 item price + $0.65 tax = $10 price with tax included


- Your revenue is $9.35



When tax is not included, the guest pays $10.70 ($10 for the item and $0.70 for the tax) and your revenue is $10:

- $10.00 item price x .07 tax rate = $0.70 in tax


- $10.00 item price + $0.70 tax = $10 price without tax included


- Your revenue is $10



Your sales reports display the item price and tax amount that the Toast platform has calculated for any tax included items, so you can see the breakdown of revenue versus tax when tax is included.

For information on enabling tax inclusion, see [Setting tax rates and tax behavior](adminGuide-adminAssigningTaxRatesInMenuBuilder#platformSettingTaxRatesAndTaxBehavior).

### Understanding takeout tax exception

For states that do not tax takeout orders, you can specify that menu items are tax-exempt when ordered for takeout. To determine if an order is a takeout order, the Toast platform looks at the dining option associated with the order and then it looks at that dining option's behavior. Dining options that use the Take Outbehavior are considered takeout orders and are not be taxed.

For more information on setting takeout tax exemption behavior, see [Setting tax rates and tax behavior](adminGuide-adminAssigningTaxRatesInMenuBuilder#platformSettingTaxRatesAndTaxBehavior).

For more information on dining options, see [Dining options](adminGuide-adminDiningOptions).

## Setting time-based ordering rules for online orders

In the Time-based ordering rules section of a menu item's details page, you can specify rules for your online orders:

- Minimum lead time: Allows you to specify the number of hours in advance a guest must order the menu item online.


- Pre order: Allows you to specify dates during which the menu item is visible for online ordering, and also dates during which the menu item may be picked up by a guest or a delivery driver, if your restaurant offers delivery services. This feature is useful for menu items that your restaurant doesn't carry on a daily basis. For example, a holiday dessert menu item may be available only in the days leading up to the holiday and should be picked up before the holiday.





> **Important**
> 
> These rules are only available to restaurants that use [Toast Online Ordering Pro](https://central.toasttab.com/s/article/Getting-Started-with-Toast-Online-Ordering-Pro) or the [Branded Mobile App](https://central.toasttab.com/s/article/Get-Started-With-the-Branded-Mobile-App) and they only apply to orders placed through these channels.


**Procedure 8.77. To specify a minimum lead time for online orders**

1. On the details page for the menu item that you want to edit, go to the Time-based ordering rules section.


2. Select + Add rule. The Add Rule dialog opens.


3. Select Minimum lead time.


4. Enter the lead time, in hours, in the How many hours in advance? box.


5. Select Save. Your changes are applied immediately after you select Save and you do not have to publish this change. It can take up to an hour for the rule to display on your online ordering page.



**Procedure 8.78. To specify dates for pre-ordering and pick up**

1. On the details page for the menu item that you want to edit, MENU-3285-itemsgo to the Time-based ordering rules section.


2. Select + Add rule. The Add Rule dialog opens.


3. Select Pre order.


4. In the Order range section, specify the date range during which the menu item can be ordered from your online ordering site. Select Select dates to view a calendar. Select the first day in the date range and then select the last day in the date range. Click or tap outside the calendar to close it.


5. In the Pickup range section, specify the date range during which the guest or delivery driver can pick up the menu item. Select Select dates to view a calendar. Select the first day in the date range and then select the last day in the date range. Click or tap outside the calendar to close it.


6. Select Save. Your changes are applied immediately after you select Save and you do not have to publish this change. It can take up to an hour for the rule to display on your online ordering page.



## Specifying ordering channel visibility for a menu item

The side panel for each menu item has a Channel visibility section that shows the ordering channels where the menu item is visible. If a menu item is visible on a channel, it is available for ordering on that channel. Options include:

- POS: The menu item is visible in the Toast POS app.


- Kiosk, Toast Order and Pay: The menu item is visible on Toast Kiosks and on the Toast Order and Pay web page. In order to enable this setting, you must first enable the POS setting.


- Toast Online Ordering, Toast Takeout (Local by Toast) app: The menu item is visible on your restaurant's Toast Online Ordering website and in the Toast Takeout (Local by Toast) app.


- Customer invoices, Catering & Events, Catering Online Ordering: The menu item is visible when:

- Creating customer invoices for orders using the Payments &gt; Payment methods &gt; Customer invoices page. For information, see this [Toast Central article](https://central.toasttab.com/s/article/How-to-Send-an-Invoice).


- Creating catering orders using Toast Catering & Events. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events).


- Configuring the menu entities that guests can see when placing online catering orders. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering).



Note that this setting is always enabled for all menu entities and cannot be changed.


- Online ordering partners: The menu item is visible on the online ordering sites of all ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub).



Unlike other settings such as tax rates and prep stations, the Channel visibility settings cannot be inherited from a parent. That said, if a parent menu entity is hidden from view for any of the Toast channels, then its child menu entities are also hidden from those channels. For example, consider a Dinner menu that contains an Appetizers group with a Chicken Satay menu item. If you hide the Dinner menu from Toast Online Ordering and the Toast Takeout (Local by Toast) app, then the Appetizers group and the Chicken Satay menu item will also be hidden from Toast Online Ordering and the Toast Takeout (Local by Toast) app, even if the Toast Online Ordering, Toast Takeout (Local by Toast) app setting is enabled for Appetizers and Chicken Satay.

You can edit a menu item's visibility from Full menu view or from Items view. You can set the same visibility options in the two views but the way you publish those changes is different:

- You must [manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) visibility changes you make in Full menu view. Full menu view does not support scheduled publishing.


- You can manually publish visibility changes you make in Items view or [schedule them for future publishing](adminGuide-platformPublishingMenuManagerChanges).



Follow the procedure below for the view you want to use, [Full menu](adminGuide-platformMenuManagerWorkingWithMenuItems#platformToEditAMenuItemsVisibilityInFullMenuView) view or [Items](adminGuide-platformMenuManagerWorkingWithMenuItems#platformToEditAMenuItemsVisibilityInItemsView)view.



> **Note**
> 
> Multi-location restaurants must use Itemsview to edit item visibility. They cannot edit visibility in Full menu view yet.
> Also, the following procedures let you make visibility updates to individual menu items. Use the bulk editing feature to make the *same* visibility edits to multiple menu items at one time. For more information, see [Making bulk edits](adminGuide-platformMenuManagerMakingBulkEdits).


**Procedure 8.79. To edit a menu item's visibility in Full menu view**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. Use the expand icons to locate the item you want to edit.


5. Select the item to see its details in the side panel, then scroll to the Channel visibilitysection.


6. Enable or disable the visibility settings as needed.


7. Select Save.


8. [Manually publish](adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



**Procedure 8.80. To edit a menu item's visibility in Items view**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Items.


4. Use the [search field](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerSearchingForMenuEntities) or the [filtering controls](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringMenuEntities) to refine the list of menu items.


5. Select a menu item's Visibility column and enable or disable the visibility settings as needed. Repeat this step with any other menu items that require visibility updates.


6. Continue reading the [Publishing menu manager changes](adminGuide-platformPublishingMenuManagerChanges) section to understand how to make your menu changes available to employees and guests.



> **Important**
> 
> Items view offers additional workflows for saving and publishing your pricing edits that are different from other configuration pages in Toast Web, including the ability to create a change set that publishes your changes at a later date and time. In Items view, you *either* select Scheduleto create a change set *or*Save to save your changes immediately. If you select Save, your changes will be saved immediately and you will not be able to create a change set. Do not select Save in Itemsview until you fully understand the publishing workflows described in [Publishing menu manager changes](adminGuide-platformPublishingMenuManagerChanges).




## Using advanced pricing strategies for menu items

Menu manager supports setting base prices, size prices, and open prices in Full menu view and editing existing base, size, location-specific, and menu-specific prices in Items view.

You can use the classic menu item detail pages to configure other advanced pricing strategies for your menu items, beyond those supported in the menu manager, for example, time prices and price levels. You can also use the classic pages to specify that a menu item inherits its price from a menu group.

If you set an advanced pricing strategy for a menu item, Items view displays the pricing strategy's name and the price range for the price (for example, $8.00 - $10.00). If the pricing strategy is one that is editable in Itemsview (base, size, location-specific, or menu-specific), you can edit the prices. If not, the prices are read-only.

If you configure a menu item to inherit its price from a menu group, the Price on column in Items view contains Menu groupto indicate the menu item inherits its price from a parent menu group. Currently, the menu item side panel in Full menuview doesn't show whether a menu item is priced at the group level or not. It only shows individual prices for the menu item, which are ignored if the menu item belongs to a menu group that is priced at the group level.

It is important to note that not all pricing strategies are supported on all Toast ordering channels. For example, Toast Online Ordering does not support time or open prices so you should not use those pricing strategies for menu items that will be displayed on your Toast Online Ordering website. Before using an advanced pricing strategy, check the table below to ensure that the strategy you want to use is supported by the Toast ordering channels where those menu items will be visible. This table also includes a description of each pricing strategy and the location where you configure it (in the menu manager or in the classic menu item details page). The sections that follow the table describe how to configure each of these pricing strategies.

| Pricing strategy | Description | Can be used with... | Configure in... | 
| --- | --- | --- | --- |
| Size price | With size pricing, the price of a menu item changes based on the size chosen for the menu item. For example, a small pizza costs $12 and a large pizza costs $14. | - Toast POS app
- Toast Online Ordering
- Toast Takeout (Local by Toast) app
- Toast Kiosk
- Toast Order and Pay
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Menu manager | 
| Open price | With open pricing, you manually specify a price for a menu item when that menu item is ordered on the Toast POS app. For example, you may want to set the price of a menu item differently depending on the market price of that menu item on the day that it is ordered.

> **Note**
> 
> For items that have a daily market price, Toast support recommends configuring the item with an open price and then using [Quick Edit](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057#:~:text=Since%20Toast%20is%20a%20cloud,Quick%20Edit%20Mode%2C%20select%20OK.) mode on a Toast POS device to set a price for the item each day. This ensures that the price is accurate and employees don't have to enter a price every time the item is ordered.


 | - Toast POS app
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Menu manager | 
| Menu-specific price | With menu-specific pricing, the price of a menu item changes based on the menu it was ordered from, for example, a menu item that costs $5 when it is ordered from the Lunch menu and $7 when it is ordered from the Dinner menu.Menu-specific prices require that the same menu item has been added to multiple menus. Currently, that type of configuration can only be created in the classic menu details pages in Toast Web. For instructions on how to add the same menu item to multiple menus, see this [Toast Central article](https://central.toasttab.com/s/article/Shallow-and-Deep-Copying-Menu-Items-and-Modifiers). | - Toast POS app
- Toast Online Ordering
- Toast Takeout (Local by Toast) app
- Toast Kiosk
- Toast Order and Pay
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Classic menu item details pageYou can update existing menu-specific prices in the menu manager Items view *after* you have defined them on the classic menu item details page. | 
| Location-specific price | With location-specific pricing, the price of a menu item changes based on the location it was ordered from, for example, a menu item that costs $15 when it is ordered from the Boston location and $17 when it is ordered from the New York location. | - Toast POS app
- Toast Kiosk
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Classic menu item details pageYou can update existing location-specific prices in the menu manager Items view *after* you have defined them on the classic menu item details page. | 
| Time price | With time pricing, you define the price of a menu group or item during specific times of the day. For example, a menu item that costs $10 between noon and 2pm and $12 during the rest of the day. With time pricing, you also specify a base price that functions as a default price for times of day when a time price has not been defined. | - Toast POS app
- Toast Online Ordering
- Toast Takeout (Local by Toast) app
- Toast Kiosk
- Toast Order and Pay
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Classic menu item details page | 
| Price levels | Price levels allow you to quickly price menu items that all share the same price. You create a price level, and then assign it to the menu items that will use it. For example, all bottled beers are $5 and all draft beers are $6. To change the price of the menu items that use a price level, you only need to change the price level itself. This eliminates the need to edit the price for each individual menu group or item. | - Toast POS app
- Toast Kiosk
- Online ordering partners (Support can vary by online ordering partner. Contact the partner to confirm.)

 | Classic menu item details page | 

For detailed information about setting base, size, and open prices in the Full menu view of the menu manager, see [Editing a menu item's price](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerEditingAMenuItemsPrice). This same topic provides information about editing existing size, location-specific, and menu-specific prices in Items view.

Follow the instructions below to access the classic details page for a menu item, where you can configure all advanced pricing strategies.

**Procedure 8.81. To set an advanced price using the classic menu item details page**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Menu management &gt; Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](adminGuide-platformMenuManagerUsingAndCustomizingTheMenuManagerViews#platformMenuManagerExpandingAndCollapsingRows) to locate the item you want to edit.


6. If you are a single-location restaurant, select the item to see its side panel, then select More settingsto open its classic details page.

If you are a multi-location restaurant, select the item's name to open its classic details page.


7. If you want to use the Menu Specific Price, Time Specific Price, or Location Specific Price pricing strategy, do the following:

- Leave the Pricing Provider section set to Specify pricing on this item.


- In the Pricing Strategy section, choose the advanced pricing strategy and fill out its configuration details. Click a link below for specific instructions for each strategy type:

- [Menu Specific Price](adminGuide-adminMenuSpecificPrice#adminToCreateMenuSpecificPricesForAMenuItem)


- [Time Specific Price](adminGuide-adminTimeSpecificPrice#adminToCreateTimeSpecificPricesForAMenuGroupOrMenuItem)


- [Location Specific Price](adminGuide-adminEnablingAndSettingLocationSpecificPrices)






8. If you want to use price levels, set the Pricing Provider section to Price level and then choose a price level from the Price Leveldropdown list.



> **Note**
> 
> Price levels must be created before you can assign them to your menu items. Currently, price level creation must be done in the classic menu details pages in Toast Web. For instructions on how to create price levels, see [Using price levels](adminGuide-adminUsingPriceLevels).



9. At the top of the page, select Save.


10. When you are ready to make your changes visible to employees and guests, you must publish them. Follow the instructions below for your scenario:

- If you have a single location, select Publish now.


- If you have multiple locations, select the Unpublished changes link at the top of the page to go to the Toast account &gt; Publishing &gt; Publish Config page. Follow the instructions in [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations) to publish changes to all or some of your locations.



> **Note**
> 
> The Publish now prompt that appears when you edit configuration pages in Toast Web publishes changes to the [session restaurant](adminGuide-sessionRestaurant) only. To publish to multiple locations, you must use the Publish Config page.






## Viewing read-only menu item information in Items view

The Items view of the menu manager provides additional read-only information about menu items. For example, the Found in column displays information about where a menu item appears in the menu hierarchy. For more information, see [Items and modifiers view](adminGuide-platformColumnsInTheMenuManagerViews#platformMenuManagerItemAndModifierColumns).

