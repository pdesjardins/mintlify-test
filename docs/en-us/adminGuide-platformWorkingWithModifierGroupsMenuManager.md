---
title: "Working with modifier groups"
id: platformWorkingWithModifierGroupsMenuManager
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerWorkingWithMenuItems.md
previousSectionTitle: "Working with menu items"
nextSectionFile: adminGuide-platformWorkingWithModifiersMenuManager.md
nextSectionTitle: "Working with modifiers"
externalReferences: [https://central.toasttab.com/s/article/How-to-Send-an-Invoice, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events, https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering]
excerpt: "This section provides information about working with modifier groups in the menu manager."
keywords: [working,modifier,groups]
procedures: 0
codeExamples: 0
---

### Working with modifier groups

This section provides information about working with modifier groups in the menu manager.

#### Creating a modifier group

To create a new modifier group, you start by viewing the side panel for a menu group or item that will use the modifier group, then you create the modifier group for that menu group or item, and add individual modifiers to it. Once you have created a modifier group for one menu group or item, you can quickly add it to others.

After they are created, modifier groups appear in the menu hierarchy table in the Full menu view and you can select them to see and edit their details in the side panel.

Here are some important points to keep in mind when creating new modifier groups:

- You can add modifier groups to menu groups or menu items.

- When you add a modifier group to a menu item, it only applies to that menu item.


- When you add a modifier group to a menu group, by default, it is inherited by all menu items in the menu group.

You can disable inherited modifier groups for an individual item within a menu group or subgroup, by setting the item's Inherit modifier groups? setting to No. If you set a menu item's Inherit modifier groups? option to No, it will not inherit *any* of the modifier groups assigned to *any* of its parent menu groups. For more information, see [Inheriting modifier groups from a parent menu group](platformWorkingWithModifierGroupsMenuManager.html#platformInheritingModifierGroupsFromAParentMenuGroupMenuManager).




- To reduce the number of modifier groups you have to manage, [add existing modifier groups](platformWorkingWithModifierGroupsMenuManager.html#platformAddingExistingModifierGroupsToAMenuGroupOrItemMenuManager) to menu groups or items whenever possible instead of creating new ones. For example, add the same Salad Dressing modifier group to both the Dinner Salad and Side Salad menu items.


- You must add at least one modifier to a modifier group before you can save the group.



For multi-location restaurants:

- Currently, the menu group side panel does not have the Modifier groups card, so you cannot add modifier groups in the side panel. You must go to a menu group's [classic details page](adminMenuManagerAndTheClassicMenuDetailsPages.html) to add modifier groups to it.


- Newly created modifier groups inherit the target and owner of their parent menu group or menu item by default. For more information, see [Defaults for targets and owners](platformMenuManagerMenuAndMultiLocationRestaurants.html#platformMenuManagerDefaultsForTargetsAndOwners).


- You must have the Edit Full Menupermission to the owner of a menu group or item in order to add a new modifier group to it.


- If the menu group or item you are adding a modifier group to is [versioned](versions.html), you must pick the version you want to add the modifier group to. The modifier group is only added to that version.



**Procedure 8.81. To create a new modifier group**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate and expand the menu group or item you want to add a modifier group to.


6. Select the menu group or item to view its side panel, then scroll to the Modifier groups section.



> **Note**
> 
> For multi-location restaurants, the menu group side panel does not currently have the option to add modifier groups. You must go to a menu group's classic details page to add modifier groups to it.



7. Do one of the following:

- If you are viewing the side panel for a menu item, select Add modifier group.


- If you are viewing the side panel for a menu group, select either the Add new button (if this menu group does not have any modifier groups yet) or select the arrow next to the + Add button and choose Add new (if the menu group already has some modifier groups).



The Create modifier group page opens.



> **Note**
> 
> If you have made any changes to the menu group, subgroup, or item that have not been saved yet, they will be lost when you move to the Create modifier group page. To avoid this issue, save the changes before creating the new modifier group.



8. On the Create modifier group page, in the Modifier group details section, enter a name for the modifier group in the Modifier group name field.


9. In the Modifier group details section, if you use Toast POS devices, you can customize the name and color of the POS button. To customize the name, enter a name in the POS name field. To specify a button color, select Button color and then select a color from the color palette.


10. In the Pricing section, [specify how the modifiers in this group are priced](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager).


11. In the Modifiers section, [create new modifiers](platformWorkingWithModifiersMenuManager.html#platformCreatingANewModifierInAModifierGroupMenuManager) or [add existing modifiers](platformWorkingWithModifiersMenuManager.html#platformAddingAnExistingModifierToAModifierGroupMenuManager) to the group.


12. In the Modifier group settings section, [choose whether selecting a modifier from this group is required or optional, and, if it's optional, whether to prompt the server](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingIfAModifierGroupIsRequiredOrOptionalMenuManager).


13. In the Modifier group settings section, [specify whether you want guests to be able to order more than one modifier from this group, the minimum and maximum number of modifiers to choose from, and whether a modifier can be chosen more than once](platformWorkingWithModifierGroupsMenuManager.html#platformAllowingGuestsToChooseOneorMoreModifiersFromTheSameModifierGroupMenuManager).


14. In the Channel visibility section, [select the ordering channels where this modifier group is visible](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingOrderingChannelVisibilityForAModifierGroupMenuManager). A modifier group is available for ordering on the channels where it is visible.


15. Select Save.


16. Select the X icon in the upper-left corner to return to Full menu view.


17. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Adding existing modifier groups to a menu group or item

To reduce the number of modifier groups you have to manage, add existing modifier groups whenever possible instead of creating new ones.

Here are some important points to keep in mind when adding existing modifier groups:

- You can add existing modifier groups to menu groups or menu items.

- When you add a modifier group to a menu item, it only applies to that menu item.


- When you add a modifier group to a menu group, by default, it is inherited by all menu items in the menu group.

You can disable inherited modifier groups for an individual item by setting the item's Inherit modifier groups? setting to No. If you set a menu item's Inherit modifier groups?option to No, it will not inherit *any* modifier groups assigned to *any* of its parent menu groups. For more information, see [Inheriting modifier groups from a parent menu group](platformWorkingWithModifierGroupsMenuManager.html#platformInheritingModifierGroupsFromAParentMenuGroupMenuManager).




- If a modifier group is used by more than one menu group or item:

- When you edit the modifier group, it is edited for all the menu groups and items that use it.


- When you remove the modifier group from one of the menu groups or items, the other menu groups or items continue to use it.





For multi-location restaurants:

- Currently, the menu group side panel does not have the Modifier groups card, so you cannot add existing modifier groups in the side panel. You must go to a menu group's [classic details page](adminMenuManagerAndTheClassicMenuDetailsPages.html) to add modifier groups to it.


- You must have the Edit Full Menupermission to the owner of a menu group or item in order to add an existing modifier group to it.


- The existing modifier groups you are allowed to add are filtered so that you can only add modifier groups that have a target that is the same as the parent menu item's target, or an ancestor or child of the parent menu item's target. This ensures that the target of the modifier group is compatible with the target of its parent menu item.


- If the menu group or item you are adding a modifier group to is [versioned](versions.html), you must pick the version you want to add the existing modifier group to. The modifier group is only added to that version.



**Procedure 8.82. To add existing modifier groups to a menu group or item**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate and expand the menu group or item you want to add an existing modifier group to.


6. Select the menu group or item to view its side panel, then scroll to the Modifier groups section.


7. Do one of the following:

- If you are viewing the side panel for a menu group, select either the Add existing button (if this menu group does not have any modifier groups yet) or select the arrow next to the + Add button and choose Add existing (if the menu group already has some modifier groups).


- If you are viewing the side panel for a menu item, select the arrow next to the + Add modifier group button and choose Add existing modifier group.

![The location of a down arrow on the Add modifier group button.](https://doc.toasttab.com/doc/media/menu-manager-add-existing-mod-group-from-menu-item-side-panel.png)



The What would you like to add? page opens.


8. Enter the name of the first modifier group you want to add in the search box. Matching modifier group results appear as you type.

Modifier groups that are eligible for adding appear in black text. Modifier groups in gray text have already been added to the menu group or item and cannot be added again. If a modifier group's check box is selected, it means you've already chosen to add it during this Add existingsession.

If there are more than 25 search results, scroll to the end of the list and select Load more to view the next 25 results.


9. Optionally, select a modifier group's name to preview it and see additional details, such as the modifiers that the group contains, the way the modifier group is priced, and the other menu groups or items that use it.


10. Select the check box for a modifier group you want to add.


11. Repeat steps 6 to 8 to include additional modifier groups.


12. Optionally, select the Selected modifier groups tab to review a list of the modifier groups you've chosen to add during this Add existingsession. On the Selected modifier groups tab, you can:

- Select a modifier group's name to preview it and see additional details.


- Select the remove icon next to an individual modifier group to remove it from the list.

![The location of a remove icon on the Selected modifier groups tab.](https://doc.toasttab.com/doc/media/menu-builder-remove-icon.png)


- Select Remove all to remove all modifier groups from the list.




13. When you are done specifying the modifier groups you want to add, select the Add modifier group button. You are returned to the menu group or menu item side panel with the modifier group(s) added.


14. Select Save in the side panel. Refresh the page and return to the Full menu view to see your changes in the menu hierarchy table.


15. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Renaming a modifier group

Follow the procedure below to rename a modifier group.

**Procedure 8.83. To rename a modifier group**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group's name to open its side panel.


7. In the Modifier group details section, enter the new name in the Modifier group namefield.


8. Select Save.


9. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Reordering modifier groups

Currently, you cannot reorder modifier groups in Full menu view. You must use the [classic pages](adminMenuManagerAndTheClassicMenuDetailsPages.html) for the menu group or item that contains the modifier groups instead.

#### Removing a modifier group from a menu group or item

When you remove a modifier group from a menu group or item, the modifier group is no longer available for that menu group or item, but the modifier group remains in your Toast Web database and can still be added to or used by other menu groups or items.

Here are some important points to keep in mind when removing modifier groups:

- If a modifier group is applied to a menu group and you remove it, that modifier group is removed from all menu items that inherit it from the menu group.


- If the modifier group is attached to multiple menu groups or items, removing it from one group or item has no effect on the other entities. They continue to use the modifier group.



For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a menu group or item in order to remove a modifier group from it. For example, consider a Sandwiches menu group that has a Cheese modifier group. You must have Edit Full Menu permission to the owner of the Sandwiches menu group to remove the Cheese modifier group from it.


- If a menu group or item is [versioned](versions.html) and you want to remove a modifier group from it, you must pick the version you want to remove the modifier group from. The modifier group is removed from that version only. The other versions continue to use the modifier group.


- If a modifier group is versioned and you remove it from a menu group or item, all versions of the modifier group are removed from the menu group or item.





> **Note**
> 
> To remove a modifier group from *all* menu groups or items that use it, you must archive it from the modifier group's [classic details page](adminMenuManagerAndTheClassicMenuDetailsPages.html).


**Procedure 8.84. To remove a modifier group**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to remove.


6. Select the menu item's overflow menu (...) and choose Remove modifier group. Your changes are automatically saved.


7. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Inheriting modifier groups from a parent menu group

The Modifier groups section of the menu item side panel has an Inherit modifier groups? setting. By default, this setting is set to Yes, so that the menu item inherits modifier groups from its parent menu groups.

If you do not want a menu item to inherit modifier groups, set its Inherit modifier groups? setting to No and then add modifier groups to it directly using the Item-level modifier groupssettings.

![An example of a menu item with the Inherit modifier groups? setting set to No.](https://doc.toasttab.com/doc/media/menu-manager-item-level-mod-groups-only.png)

##### Understanding where a menu item inherits its modifier groups from

Menu items can belong to more than one menu path. When a menu item belongs to more than one menu path, it can inherit different modifier groups from each path. For example, the Grilled Cheese menu item in the illustration below belongs to two menu paths: Dinner > Dinner Sandwiches and Lunch > Lunch Sandwiches. When a Grilled Cheese is ordered from the Dinner > Dinner Sandwiches path, it uses the Dinner Sides modifier group. When a Grilled Cheese is ordered from the Lunch > Lunch Sandwiches path, the menu item uses the Lunch Sides modifier group.

![An example of a menu item that inherits different modifier groups, depending on the menu path the item is ordered from.](https://doc.toasttab.com/doc/media/menu-builder-inherited-mod-groups-from-different-paths.png)

When you set a menu item's Inherit modifier groups? option to Yes, you see a set of tables that show the different menu paths the menu item belongs to. The table for each path shows the modifier groups that the menu item inherits for each path, and the specific parent menu groups within those paths that provide the inherited modifier groups.

For more information on inheritance, see [Understanding inheritance](platformUnderstandingInheritanceMenuManager.html).

##### Menu items can have item-level and menu group-level modifier groups

A menu item can have both inherited modifier groups and item-level modifier groups that are added directly to the menu item itself, using the Item-level modifier groupssettings. In the example below, the Filet Mignon menu item inherits the Dinner Sides modifier group from its parent menu group while the Sauces modifier group is added directly to the Filet Mignon menu item.

![An example of a menu item that has both an inherited modifier group and an item-level modifier group.](https://doc.toasttab.com/doc/media/menu-manager-both-item-level-and-inherited-mod-groups.png)

##### Overriding modifier group inheritance for individual menu items

By default, the Inherit modifier groups?setting is set to Yes for all menu items within a menu group. However, you can choose to override that setting on individual menu items within the group. For example, consider a Sandwiches menu group that has an assortment of sandwiches, one of which is vegan. You could add a Cheese Selection modifier group to the Sandwiches menu group and allow the non-vegan sandwiches to inherit it but toggle the Inherit modifier groups? setting to No for the vegan sandwich.



> **Important**
> 
> You cannot set a menu item to inherit some of the modifier groups from its parent menu groups. It either inherits all of them or none of them.


#### Specifying how modifiers in a group are priced

You use the Pricing section in a modifier group's side panel to specify how the modifiers in a group are priced:

- No charge: There is no charge for the modifiers in the group.


- Individual: Each modifier in the group has its own price. When you choose this option, the table in the Modifiers section displays a Price column that you use to specify the prices of the modifiers. Currently, you can set base prices using the Price column. For information on setting individual prices for a modifier, see [Specifying modifier prices](platformWorkingWithModifiersMenuManager.html#platformSpecifyingModifiersPricesMenuManager).


- Group: All modifiers in the group share the same price. When you choose this option, a Price field appears in the Pricing section where you can enter the price for the modifiers.

If the modifier group is configured with an advanced pricing strategy (for example, size or sequence pricing), you see a notification with a link that takes you to the modifier group's classic details page where you can edit the advanced pricing. For more information on advanced pricing strategies, see [Pricing strategies overview](adminPricingStrategiesOverview.html).



#### Specifying if a modifier group is required or optional

In the Modifier group settings section of a modifier group's side panel, you can choose whether selecting a modifier from a group is required or optional:

- A Required modifier group is always shown to a guest or server and they must make a selection before they can proceed with an order (for example, meat temperature on a Steak menu item).


- An Optional modifier group is available to a guest or server but they don't have to view it or make a selection from it before proceeding with the order (for example, adding a chicken modifier to a Salad menu item).

If you choose Optional and you use POS devices, you can also toggle the Include a POS prompt setting to On to require servers to view the modifier group before they can continue with the order. Servers must either pick a modifier or choose Done to close the modifier group before proceeding. This feature is useful to remind servers about optional upsells they may want to suggest to the guest. This setting has no effect on your online ordering site.



##### Sequence of modifier groups

The sequence of modifier groups in Toast ordering channels is affected by the required and optional settings. In general, required modifier groups are shown first, followed by optional groups that use a POS prompt, followed by optional groups that don't use a POS prompt; however there are other factors that affect modifier group display order. For more information, see [Modifier group display order overview](platformModifierGroupDisplayOrderOverview.html).

##### Required modifier groups and visibility settings

When you configure a modifier group as Required, you must also pay careful attention to the group's [ordering channel visibility](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingOrderingChannelVisibilityForAModifierGroupMenuManager) settings. If the group is not visible on a particular channel, guests and servers won't see it on that channel and it will be missing from orders placed on that channel, even if it is marked as Required. Examples of channels include the Toast POS app, a Toast Kiosk, a restaurant's Toast online ordering site, or a third-party ordering website like Grubhub, Doordash, or UberEats.

Consider the following example. A Dinner Salad menu item has a Dressing modifier group that is marked as Required. The Dinner Salad's visibility settings specify that it is visible and available for ordering on all channels. The Dressing modifier group, however, was accidentally configured so that it is not visible on the Toast Online Ordering site. When a guest places an order for the Dinner Salad on the Toast online ordering site, they are not shown the Dressing modifier group because that modifier group is not visible on the Toast online ordering site. Consequently, when the order is sent to the restaurant, it is missing a selection from the Dressing modifier group.

To sum up, if you mark a modifier group as Required, pay careful attention to its visibility settings to ensure it is displayed on the correct channels and your servers and guests can see it and select it.

#### Allowing guests to choose one or more modifiers from the same modifier group

In the Modifier group settings section of a modifier group's side panel, you can specify whether guests can order more than one modifier from a modifier group.

Set the Allow guests to select more than one modifier setting to On if you want guests to be able to select more than one modifier from this group. The additional options you see depend on whether the modifier group is required or optional:

- The What is the maximum number a guest can select option appears for both required and optional modifier groups and allows you to specify the maximum number of modifiers a guest can select from this group. This option defaults to No maximum, meaning a guest can select as many modifiers from the group as they want.


- The What is the minimum number a guest must select option appears for required modifier groups and lets you specify the number of modifiers a guest *must select* from this group. This option defaults to 1, meaning a guest must select one modifier from the group, but you can increase that number if necessary.



The table below provides some examples to help you better understand how to use the minimum and maximum settings:

| Requirements | Example | Settings | 
| --- | --- | --- |
| Guests can make zero or one selection from this modifier group. | A Protein modifier group that lets a guest optionally add chicken or salmon to a Salad entree. | OptionalMinimum: 0Maximum: 1 | 
| Guests must make one, and only one, selection from this modifier group. | A Temperature modifier group that defines the cooking temperature for a Steak entree and has Rare, Medium, or Well Done modifiers. | RequiredMinimum: 1Maximum: 1 | 
| Guests must select a specific number of modifiers from this modifier group. | A pick-two lunch entree where the guest can pick two offerings from a group of lunch dishes, for example, soup and a sandwich, or soup and a salad, or salad and a sandwich. | RequiredMinimum: 2Maximum: 2 | 
| Guests can select as few or as many modifiers from this modifier group as they want. | A Pizza Toppings modifier group for a make-your-own pizza where the guest can choose as few or as many toppings as they like. | OptionalNo minimumNo maximum | 
| Guests must select at least one modifier from this modifier group but they can also pick as many modifiers from this group as they want. | A Cheese Choice modifier group where the guest must specify at least one type of cheese to add to a sandwich but they can optionally add as many types of cheese as they want. | RequiredMinimum: 1No maximum | 
| Guests do not have to select any modifiers from this group but, if they do, they are limited to a specific number. | An Extra Sides modifier group where the guest does not have to pick a side dish but they can optionally add up to two side dishes. | OptionalNo minimumMaximum: 2 | 

##### Selecting a single modifier more than once

If the Allow guests to select more than one modifier option is On, the Can a single modifier be selected more than onceoption is also displayed. Set this option to Onif you want a guest to be able to select a single modifier more than once, for example, to let a guest add double pepperoni to a pizza.

##### Minimum modifiers and visibility settings

When you configure a modifier group to use the What is the minimum number a guest must select setting, you must also pay careful attention to the [ordering channel visibility](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingOrderingChannelVisibilityForAModifierGroupMenuManager) settings for the modifiers in that group. Specifically, you must ensure that the number of modifiers that are visible in any given ordering channel meet or exceed the minimum number of modifiers a guest or server must select from the modifier group.

For example, consider a Lunch Sides modifier group that sets the What is the minimum number a guest must selectoption to 2 and has the following modifiers:

- Fries


- Salad


- Soup



The Fries modifier is visible on both the Toast POS app and the Toast Online Ordering site but the Soup and Salad modifiers were mistakenly configured so that they are only visible on the Toast POS app. When a guest on the Toast Online Ordering site places an order, they will only see the Fries modifier in the Lunch Sides modifier group, making it impossible for them to pick two sides. The guest will still be allowed to place this order and the order will not fail when it is sent to the Toast platform, but it will not have all the information the kitchen needs to fulfill it.

#### Specifying ordering channel visibility for a modifier group

Ordering channel visibility settings determine the ordering channels where a modifier group is visible. If a modifier group is visible on a channel, it is available for ordering on that channel. Options include:

- POS: The modifier group is visible in the Toast POS app.


- Kiosk, Toast Order and Pay: The modifier group is visible on Toast Kiosks and on the Toast Order and Pay web page. In order to enable this setting, you must first enable the POS setting.


- Toast Online Ordering, Toast Takeout (Local by Toast) app: The modifier group is visible on your restaurant's Toast Online Ordering website and in the Toast Takeout (Local by Toast) app. In order to enable this setting, you must first enable the POS setting.


- Customer invoices, Catering & Events, Catering Online Ordering: The modifier group is visible when:

- Creating customer invoices for orders using the Payments > Payment methods > Customer invoices page. For information, see this [Toast Central article](https://central.toasttab.com/s/article/How-to-Send-an-Invoice).


- Creating catering orders using Toast Catering & Events. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events).


- Configuring the menu entities that guests can see when placing online catering orders. For information, see this [Toast Central article](https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering).



Note that this setting is always enabled for all menu entities and cannot be changed.


- Online ordering partners: The modifier group is visible on the online ordering sites of all ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub).



**Procedure 8.85. To set ordering channel visibility for a modifier group**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Channel visibility section.


7. Select the channels where you want the modifier group to appear.


8. Select Save.


9. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



