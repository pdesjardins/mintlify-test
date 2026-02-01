---
title: "Working with menus"
id: platformMenuManagerWorkingWithMenus
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformUnderstandingInheritanceMenuManager.md
previousSectionTitle: "Understanding inheritance"
nextSectionFile: adminGuide-platformMenuManagerWorkingWithMenuGroups.md
nextSectionTitle: "Working with menu groups and subgroups"
externalReferences: [https://central.toasttab.com/s/article/Course-Firing-Options, https://central.toasttab.com/s/article/Sales-Reports-Overview, https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577, https://central.toasttab.com/s/article/How-to-Send-an-Invoice, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events, https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering]
excerpt: "This section provides information about working with menus in the menu manager."
keywords: [working,menus]
procedures: 0
codeExamples: 0
---

### Working with menus

This section provides information about working with menus in the menu manager.

#### Creating a menu

This section provides information about creating menus.

For multi-location restaurants, newly created menus are automatically targeted at the highest location group or location you have the Edit Full Menu permission to. The owner defaults to this same location group or location. For more information, see [Defaults for targets and owners](platformMenuManagerMenuAndMultiLocationRestaurants.html#platformMenuManagerDefaultsForTargetsAndOwners).

**Procedure 8.45. To create a menu**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. At the end of the menus list, select + Add menu, enter a name for the menu, and select the check icon. Alternatively, you can press Enter on your keyboard or select anywhere outside the text box to complete the entry. Your changes are automatically saved.

![The location of the Add menu button.](https://doc.toasttab.com/doc/media/menu-manager-add-menu-button.png)


6. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Renaming a menu

Follow the procedure below to rename a menu.

**Procedure 8.46. To rename a menu**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Select the menu's name to open its side panel.


6. Enter the new name in the Menu namefield.


7. Select Save.


8. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Reordering menus

Your Toast ordering channels display your menus in the order you see them in the Full menu view. You can reorder your menus so they appear in the order you want them to.



> **Note**
> 
> If you have a multi-location restaurant, you cannot reorder menus in Full menu view. You must use the Menus \> Edit menus page instead.


**Procedure 8.47. To reorder a menu**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. Select the re-order icon for the menu you want to move and drag it to its new location in the list of menus. Your changes are automatically saved.

![The location of the reorder icon for a menu you want to move.](https://doc.toasttab.com/doc/media/menu-manager-menu-reorder-button.png)


5. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Archiving a menu

You can archive a menu to hide it from your Toast ordering channels.

For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a menu version to archive that version.


- If you archive a menu version, only that version is archived. The other versions continue to be available.





> **Note**
> 
> To undo a menu archive, go to the Menus \> Bulk management \> Items database page in Toast Web. Select the Menus tab and then choose Show Archived. Select the checkbox for the menu you want to restore and choose Restore.


**Procedure 8.48. To archive a menu**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Select the overflow menu (...) for the menu you want to archive and choose Archive menu.

![The location of the overflow menu for a menu you want to archive.](https://doc.toasttab.com/doc/media/menu-manager-menu-overflow-button.png)


6. To confirm, select Archive in the Archive the menu dialog.


7. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Assigning a POS button name and color

You can customize the names and colors of the buttons employees see in the Toast POS app for the various menu entities:

- For menus, menu groups, subgroups, menu items, and modifier groups, go to the details section of the menu entity's details page. For example, for a menu, go to Menu details.

Enter a name in the POS name field. To specify a button color, select the Button coloroption and then select a color from the color palette.


- For modifiers, go to [the Edit modifier dialog](adminAddingModifierGroupsAndModifiers.html#platformEditingAModifiersDetails) for the modifier, select the POS button color option and then select a color from the color palette. Modifiers do not have a POS name. The Toast POS app displays the Modifier name.



By default, the POS name field is empty and the button color is set to white.

#### Assigning tax rates and tax behavior

During the on-boarding process, you specify the tax rates that apply to your restaurant location. By default, these tax rates are inherited by any menus you create for the restaurant. According to the rules of menu inheritance, the tax rates also flow down to your menu groups, subgroups, and menu items in the following ways:

- Menu groups inherit their tax rates from their parent menus.


- Menu items and subgroups inherit their tax rates from their parent menu groups.



You can override tax rates on individual menus, menu groups, subgroups, or menu items as needed.

In addition to tax rates, Toast Web includes two tax behavior settings that allow you to specify that taxes are included in a menu item's price and takeout orders are exempt from taxes. You can set the tax behavior settings at the menu, menu group, subgroup, or menu item level and they follow the same rules of inheritance as tax rates. You can override these settings as needed on individual menu entities.

For more information on menu inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

The following sections provide instructions for setting tax rates and behavior. They also provide more information about the tax behavior settings.

- [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior)


- [Understanding tax inclusion](adminAssigningTaxRatesInMenuBuilder.html#platformUnderstandingTaxInclusion)


- [Understanding takeout tax exception](adminAssigningTaxRatesInMenuBuilder.html#platformUnderstandingTakeoutTaxException)



##### Setting tax rates and tax behavior

To override the inherited tax rates for a menu, menu group, or subgroup, go to the Taxes section of the entity's details page, select the link icon next to Tax rates to unlink the configuration, and then select the tax rates from the list. To override the Calculate prices with tax included or Takeout exception setting, select its link icon to unlink the configuration and then configure the setting as needed.

![Example of a menu group that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-tax-settings.png)

To configure a menu, menu group, or subgroup so it inherits its tax rates, select the link icon next to Tax ratesso the tax rates setting is grayed out. To inherit the Calculate prices with tax included or Takeout exception setting, select its link icon so that the setting is grayed out.

![Example of a menu group that inherits its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-tax-settings.png)

To override the inherited tax rates for a menu item, go to the Tax settings section on its details page, set its Inherit tax rates? setting to No, and then select the tax rates from the list. To override the Tax inclusion or Takeout tax exception setting, set Inherit tax inclusion? or Inherit takeout tax? to No and then configure the setting as needed. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its tax rates and tax behavior settings.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-tax-settings.png)

To configure a menu item so that it inherits its tax rates, set the Inherit tax rates? setting to Yes. To inherit the Tax inclusion or Takeout tax exceptionsetting, set the Inherit tax inclusion? or Inherit takeout tax? setting to Yes.

If you do not have any tax rates configured yet, you see a Manage tax rates link that you can select to go to the Tax rates page where you can create them. For more information on creating tax rates, see [Taxes overview](adminTaxesOverview.html).

##### Understanding tax inclusion

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

For information on enabling tax inclusion, see [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior).

##### Understanding takeout tax exception

For states that do not tax takeout orders, you can specify that menu items are tax-exempt when ordered for takeout. To determine if an order is a takeout order, the Toast platform looks at the dining option associated with the order and then it looks at that dining option's behavior. Dining options that use the Take Outbehavior are considered takeout orders and are not be taxed.

For more information on setting takeout tax exemption behavior, see [Setting tax rates and tax behavior](adminAssigningTaxRatesInMenuBuilder.html#platformSettingTaxRatesAndTaxBehavior).

For more information on dining options, see [Dining options](adminDiningOptions.html).

#### Assigning prep stations

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

If you do not have any prep stations configured yet, use the Manage prep stations link to go to the Prep Stations page where you can create them. For more information on creating and using prep stations, see [Adding a prep station](adminAddPrepStation.html) and [Routing with prep stations](adminRoutingToPrepStations.html).

#### Assigning courses

You use courses to manage the firing of tickets to the kitchen for fulfillment.

You can set courses at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their course from their parent menus. Menu items and subgroups inherit their course from their parent menu groups. For more information on inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

To set the course for a menu, go to the Kitchen prep section of the menu's details page and select the course.

To override the inherited course for a menu group or subgroup, go to the Kitchen prep section of the group's details page, select the link icon next to Course to unlink the configuration, and then select the course from the list.

![Example of a menu group that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-course.png)

To configure a menu group or subgroup so that it inherits its course, select the link icon next to Course so that the course setting is grayed out.

![Example of a menu group that inherits its course.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-course.png)

To override the inherited course for a menu item, go to the Kitchen section on its details page, set its Inherit course? setting to No, and then select its course from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its course.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-course.png)

To configure a menu item so that it inherits its course, set the Inherit course? setting to Yes.

If you do not have any courses configured yet, use the Manage courses link to go to the Courses page where you can create them. For more information on creating courses, see [Creating courses](adminAssigningCourses.html#platformGuideCreatingCoursesMenuBuilder). For more information on using courses, see this [Toast Central article](https://central.toasttab.com/s/article/Course-Firing-Options).

##### Creating courses

While you can assign courses in the menu builder, you must use the classic Courses page to create the courses themselves.

**Procedure 8.49. To create courses**

1. Go to the Courses page:

If you are viewing a menu item in the menu builder, select Kitchen. If you are viewing a menu, menu group, or subgroup in the menu builder, select Kitchen prep. In the Related settingssection, select Manage courses.

Alternatively, you can do the following:

- [Log in to Toast Web](adminAccessToastAdminBackend.html).


- Switch to the restaurant you want to create courses for.


- Select Kitchen \> Pacing \> Courses.




2. Select + Add to add a row to the Courses table.


3. Enter a name for the course.


4. Repeat steps 2 and 3 for any additional courses you want to create.


5. Select Save.



#### Assigning sales categories

The Sales Summary and other Toast reports use sales categories to create a breakdown of your sales, organized by sales category, for example, Food, Drinks, Retail, and so on.

Some points to keep in mind when using sales categories:

- If you change the sales category for a menu entity, those changes are reflected in future sales reports but existing reports remain unchanged.


- While highly recommended for a better reporting experience, sales categories are optional. If you select None selected from the Sales categorymenu, no sales category is applied to the menu entity.



For information about the reports that use sales categories, see these Toast Central articles:

- [Sales Reports Overview](https://central.toasttab.com/s/article/Sales-Reports-Overview)


- [Menu Reports Overview](https://central.toasttab.com/s/article/Menu-Report-Overview-1492794696577)



You can set sales categories at the menu, menu group, subgroup, or menu item level. By default, menu groups inherit their sales category from their parent menus. Menu items and subgroups inherit their sales category from their parent menu groups. For more information on inheritance, see [Understanding inheritance](platformUnderstandingInheritance.html).

To set the sales category for a menu, go to the Reporting section of the menu's details page and select the category from the Sales category dropdown list.

To override the inherited sales category for a menu group or subgroup, go to the Reporting section of the group's details page, select the link icon next to Sales category to unlink the configuration, and then select the sales category from the list.

![Example of a menu group that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-does-not-inherit-sales-category.png)

To configure a menu group or subgroup so that it inherits its sales category, select the link icon next to Sales categoryso that the course setting is grayed out.

![Example of a menu group that inherits its sales category.](https://doc.toasttab.com/doc/media/menu-builder-menu-group-inherits-sales-category.png)

To override the inherited sales category for a menu item, go to the Reporting section on its details page, set its Inherit sales category? setting to No, and then select its sales category from the dropdown list. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![Example of a menu item that does not inherit its sales category.](https://doc.toasttab.com/doc/media/menu-builder-item-does-not-inherit-sales-category.png)

To configure a menu item so that it inherits its sales category, set the Inherit sales category? setting to Yes.

If you do not have any sales categories configured yet, use the Manage sales categories link to go to the Sales categories page where you can create them. For more information on creating sales categories, see [Creating sales categories](adminAssigningSalesCategories.html#platformCreatingSalesCategoriesMenuBuilder).

##### Creating sales categories

While you can assign sales categories in the menu builder, you must use the classic Sales Categories page to create the sales categories themselves.

**Procedure 8.50. To create sales categories**

1. Do one of the following to navigate to the Sales categories page:

On the details page for a menu, menu group, or menu item, select Reporting. In the Related settings section, select Manage sales categories.

Alternatively, you can:

- [Log in to Toast Web](adminAccessToastAdminBackend.html).


- Switch to the restaurant you want to create courses for.


- Select Menus \> Settings \> Sales categories.




2. Select + Add to add a row to the Sales Categories table.


3. Enter a name and a description for the sales category.


4. Repeat steps 2 and 3 for any additional sales categories you want to create.


5. Select Save.



#### Specifying a custom schedule for a menu

You can use a menu's Availability settings to define a specific time period that a menu is available or a specific set of days that the menu is available. By default, a menu's availability is set to Always, meaning the menu is available during all hours that the restaurant is open.

Custom schedules can only be set at the menu level. You cannot specify a custom schedule for menu groups or menu items. Also, you can only set one time period per menu.

For multi-location restaurants, the time period you specify is in each location's local time.

**Procedure 8.51. To specify a custom schedule for a menu**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Select the menu to see its details in the side panel.


6. In the Availability section of the side panel, select Specific days and time. A table appears that shows the days and time that the menu will be available.


7. To edit the availability table, select the edit icon (pencil) on the table row. You see the Edit days and time dialog.


8. In the Day(s) available section, select the days you want the menu to be available.


9. In the Time available section, the Available at all times option is selected by default, indicating that the menu is available during all hours that the restaurant is open on the days you selected in the previous step. To set specific hours that the menu is available, uncheck Available at all times to see the Start and End time settings, then specify start and end times.


10. Select Save to save your custom schedule.


11. Select Save again in the side panel.


12. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Specifying ordering channel visibility for a menu

The side panel for each menu has a Channel visibility section that shows the channels where the menu is visible. If a menu is visible on a channel, it is available for ordering on that channel. Options include:

- POS: The menu is visible in the Toast POS app.


- Kiosk, Toast Order and Pay: The menu is visible on Toast Kiosks and on the Toast order and pay web page. In order to enable this setting, you must first enable the POS setting.


- Toast Online Ordering, Toast Takeout (Local by Toast) app: The menu is visible on your restaurant's Toast Online Ordering website and in the Toast Takeout (Local by Toast) app.


- Customer invoices, Catering & Events, Catering Online Ordering: The menu entity is visible when:

- Creating customer invoices for orders using the Payments \> Payment methods \> Customer invoices page. For information, see this [Toast Central article](https://central.toasttab.com/s/article/How-to-Send-an-Invoice).


- Creating catering orders using Toast Catering & Events. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events).


- Configuring the menu entities that guests can see when placing online catering orders. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering).



Note that this setting is always enabled for all menu entities and cannot be changed.


- Online ordering partners: The menu is visible on the online ordering sites of all ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, UberEats, or Grubhub).

When you select the Online ordering partners option for a menu, an additional list of the online ordering partners you integrate with appears. By default, all of them are selected. You can uncheck an online ordering partner to hide the menu on that online ordering partner's site. This visibility setting is only available for menus. See [Restricting menu visibility to specific online ordering partners](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html)for more information.


- Digital menu board: The menu is visible on a Delphi digital menu board. Defaults to Off. This visibility setting is only available for menus.

The Digital menu board setting only appears for restaurants that have a Delphi digital menu board. For more information, see [Creating a menu for a Delphi digital menu board](platformCreatingAMenuForADigitalMenuBoard.html).


- Websites View-only: A read-only version of the menu is visible on your Toast website. Defaults to Off. This visibility setting is only available for menus.

The Websites View-only setting only appears for restaurants that have Digital Storefront Pro.





> **Note**
> 
> Modifier groups have the limitation that their Kiosk, Toast Order and Pay and Toast Online Ordering, Toast Takeout (Local by Toast) app settings, must match (this limitation does not exist for menus, menu groups, or menu item visibility). So, if you enable or disable one of those settings, the other setting will be enabled or disabled to match.


Unlike other settings such as tax rates and prep stations, the Channel visibility settings cannot be inherited from a parent. That said, if a parent menu entity is hidden from view for any of the Toast channels, then its child menu entities are also hidden from those channels. For example, consider a Dinner menu that contains an Appetizers group with a Chicken Satay menu item. If you hide the Dinner menu from Toast Online Ordering and the Toast Takeout (Local by Toast) app, then the Appetizers group and the Chicken Satay menu item will also be hidden from Toast Online Ordering and the Toast Takeout (Local by Toast) app, even if the Toast Online Ordering, Toast Takeout (Local by Toast) app setting is enabled for Appetizers and Chicken Satay.

##### Restricting menu visibility to specific online ordering partners

When you enable the Online ordering partners option for a menu, an additional list of the online ordering partners you integrate with appears. You can use these settings to make the menu visible to specific online ordering partners and hide it from others. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash. For more information on using these settings, see [Restricting menu visibility to specific online ordering partners](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html).

