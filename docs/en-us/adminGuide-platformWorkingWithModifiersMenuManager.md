---
title: "Working with modifiers"
id: platformWorkingWithModifiersMenuManager
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformWorkingWithModifierGroupsMenuManager.md
previousSectionTitle: "Working with modifier groups"
nextSectionFile: adminGuide-platformMenuManagerWorkingWithPriceLevels.md
nextSectionTitle: "Working with price levels"
excerpt: "Modifier..."
keywords: [working,modifiers]
procedures: 0
codeExamples: 0
---

### Working with modifiers

Modifier groups contain individual modifiers that allow guests to customize their orders. For example, a Dinner Salad menu item might have a Salad Dressing modifier group that contains modifiers such as Blue Cheese and Ranch.

To add and customize the modifiers in a modifier group, you use the Modifiers section of a modifier group's side panel:

![A modifier group details page with the Modifiers section displayed.](https://doc.toasttab.com/doc/media/menu-manager-modifiers-table.png)

Here are some important points to keep in mind when working with modifiers:

- To reduce the number of modifiers you have to manage, [add existing modifiers](platformWorkingWithModifiersMenuManager.html#platformAddingAnExistingModifierToAModifierGroupMenuManager) to modifier groups whenever possible instead of creating new ones. For example, a Breakfast Sides modifier group and a Burger Toppings modifier group could share a Bacon modifier.


- If a modifier is used by more than one modifier group:

- When you edit the modifier, it is edited for all the modifier groups that use it.


- When you remove the modifier from one of the modifier groups, the other modifier groups continue to use it.




- You must add at least one modifier to a modifier group before you can save the group.



#### Understanding a modifier item reference

In the [classic menu configuration experience](adminMenuManagerAndTheClassicMenuDetailsPages.html), you can base a modifier on an existing menu item. For example, a Fries menu item can function as a normal menu item but also as the item reference for a Fries modifier. For this reason, all modifiers are supported by an underlying menu item, called the modifier's *item reference*. Item references have all the configuration settings of a normal menu item such as name, POS button color, pricing, and so on.

When you create a new modifier that is *not based on* an existing menu item, the Toast platform automatically creates an item reference for it. This maintains the same underlying structure for both modifiers based on existing menu items and modifiers that are not based on existing menu items. This section uses the term *stand-alone modifier* for a modifier that is not based on an existing menu item.



> **Note**
> 
> The menu manager currently only supports creating stand-alone modifiers but you can see and edit any modifiers that have been created using the classic experience, including both stand-alone modifiers and modifiers based on existing menu items.


When a modifier is based on an existing menu item, you can choose to use the price of the underlying menu item as the price of the modifier, or you can override that price with a price that is specific to the modifier. For example, the price of the Fries menu item could be $8 while the override price of the Fries modifier is $5.

For stand-alone modifiers, the price you specify when creating the modifier becomes the price of the underlying item reference that the Toast platform creates.

The same is true for the modifier's name. For a modifier based on an existing menu item, you can use the name of the underlying item reference or you can specify an override name for the modifier. If you create a stand-alone modifier, the name you provide becomes the name of the underlying item reference.

Whichever price is in effect, either the item reference price or an override price, that's the price you see and edit in:

- The Modifiers section of the modifier group side panel in Full menu view.


- The Edit modifier dialog you access by selecting the name of a modifier in the Modifiers section of the modifier group side panel.


- The Price column in Modifiers view.



The same is true for the name field.

**Procedure 8.86. To access a modifier's item reference**

1. Do one of the following to open the modifier's classic details page:

- In Modifiers view, use the search and filter controls to locate the modifier, then select its name.


- In Full menu view, select a modifier group to display its side panel, scroll to the Modifiers section, and select the modifier's name to open the Edit modifierdialog. In the Edit modifier dialog, select More modifier settings.



The modifier's classic details page opens.



> **Note**
> 
> For multi-location restaurants, if a modifier is [versioned](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly), you see a single row in the Modifiers table and the version that has the highest target is displayed. It is this highest-targeted version that you see in the Edit modifier dialog. Selecting the More modifier settings opens the classic modifier details page for this highest version. For information on opening the classic modifier details pages for the other versions, see [Versioned modifiers (multi-location only)](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly).



2. Select Edit Item. The modifier's item reference page opens.

From the item reference page, you can set the item reference name and price. This includes setting advanced pricing strategies for the item reference like menu-specific or location-specific pricing. For information on advanced pricing strategies, see [Pricing strategies overview](adminPricingStrategyDetailsOmitChunkFromSearchIndex.html#adminPricingStrategiesOverview).


3. If you make any changes to the item reference, select Save at the top of the page.


4. When you are ready to make your changes visible to employees and guests, you must publish them. Follow the instructions below for your scenario:

- If you have a single location, select Publish now.


- If you have multiple locations, select the Unpublished changes link at the top of the page to go to the Toast account > Publishing > Publish Config page. Follow the instructions in [Publishing changes for multiple locations](publishingChangesForMultipleLocations.html) to publish changes to all or some of your locations.



> **Note**
> 
> The Publish now prompt that appears when you edit configuration pages in Toast Web publishes changes to the [session restaurant](understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.html#sessionRestaurant) only. To publish to multiple locations, you must use the Publish Config page.






**Procedure 8.87. To specify an override name or price for a modifier**

1. Do one of the following to open the modifier's classic details page:

- In Modifiers view, use the search and filter controls to locate the modifier, then select its name.


- In Full menu view, select a modifier group to display its side panel, scroll to the Modifiers section, and select Edit from the modifier's overflow menu (...) to open the Edit modifier dialog. In the Edit modifier dialog, select More modifier settings.



The modifier's classic details page opens.

![An example of the classic modifier details page.](https://doc.toasttab.com/doc/media/menu-manager-classic-modifier-details-page-example.png)



> **Note**
> 
> For multi-location restaurants, if a modifier is [versioned](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly), you see a single row in the Modifiers table and the version that has the highest target is displayed. It is this highest-targeted version that you see in the Edit modifier dialog. Selecting the More modifier settings opens the classic modifier details page for this highest version. For information on opening the classic modifier details pages for the other versions, see [Versioned modifiers (multi-location only)](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly).



2. To enter an override name, enter the name in the Modifier name field.


3. To enter an override price, set the Override item price option to Yes and enter a price in the Modifier-specific price field. Override prices are always base prices.


4. At the top of the page, select Save.


5. When you are ready to make your changes visible to employees and guests, you must publish them. Follow the instructions below for your scenario:

- If you have a single location, select Publish now.


- If you have multiple locations, select the Unpublished changes link at the top of the page to go to the Toast account > Publishing > Publish Config page. Follow the instructions in [Publishing changes for multiple locations](publishingChangesForMultipleLocations.html) to publish changes to all or some of your locations.



> **Note**
> 
> The Publish now prompt that appears when you edit configuration pages in Toast Web publishes changes to the [session restaurant](understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.html#sessionRestaurant) only. To publish to multiple locations, you must use the Publish Config page.






#### Versioned modifiers (multi-location only)

Modifiers can be versioned using the New Version button on their classic details pages. For example, you could have a Fries modifier targeted at a Corporate location group that uses an [override price](platformWorkingWithModifiersMenuManager.html#platformToSpecifyAnOverrideNameOrPriceForAModifier) of $7 and another version of that modifier targeted at Boston that uses an override price of $9.

![The location of the New Version button on the classic modifier details page.](https://doc.toasttab.com/doc/media/menu-manager-classic-modifier-details-page-new-version-button.png)

If a modifier is versioned, you see a row for each version in Modifiers view, assuming you are viewing all locations (if you are not viewing all locations then you see the versions associated with the locations you have chosen to view).

![An example of Modifiers view showing multiple rows for a versioned modifier.](https://doc.toasttab.com/doc/media/menu-manager-versioned-modifier-modifiers-view.png)

The same is true for the menu hierarchy table in Full menu view, you see a row for each version in the menu hierarchy table, depending on which locations you have chosen to view.

![An example of Full menu view showing multiple rows for a versioned modifier.](https://doc.toasttab.com/doc/media/menu-manager-versioned-modifier-hierarchy-table.png)

The Modifiers table you see in the modifier group side panel, however, behaves differently.

![An example of Full menu view showing multiple rows for a versioned modifier.](https://doc.toasttab.com/doc/media/menu-manager-versioned-modifier-side-panel.png)

If a modifier is versioned, you see a single row for that modifier in the Modifiers table on the modifier group side panel. The version that has the highest target is displayed in the row, along with its price if the modifier group is [priced individually](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager). For example, consider the following location group hierarchy:

- Corporate

- Northeast

- Boston


- New York City







If the modifier has versions targeted at Corporate and Northeast, then the Corporate version is shown in the Modifiers table.

If you edit a versioned modifier in the Modifiers table, you are only editing the highest-targeted version. If you select the name of a versioned modifier in the Modifiers table, the Edit modifier dialog that appears also only affects the highest-targeted version.

If you need to edit a modifier version that doesn't appear in the Modifiers table, you can use Modifiers view instead, which has columns for setting the modifier version's price and visibility. To edit other settings, select the name of a modifier version in Modifiers view to open its classic modifier details page. From the classic modifier details page, you can also select Edit Item to access the modifier's [item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager) page where you can set additional properties.

#### Creating a new modifier

Follow the instructions below to create new modifiers for a modifier group.

For multi-location restaurants:

- Newly created modifiers inherit the target and owner of their parent modifier group by default. For more information, see [Defaults for targets and owners](platformMenuManagerMenuAndMultiLocationRestaurants.html#platformMenuManagerDefaultsForTargetsAndOwners).


- You must have the Edit Full Menupermission to the owner of a modifier group in order to create a new modifier for it.



**Procedure 8.88. To create new modifiers for a modifier group**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to add a modifier to.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. Select + Add modifier and enter a name for the modifier. A dropdown list appears that has a Create new option followed by a list of any existing modifiers that match the text you entered.


8. After you are done entering the modifier name, select the Create new option (alternatively, you can press the Enter key).


9. If your modifiers are [priced individually](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager), the Modifiers table has a Price column where you can enter a price for each modifier you create.



> **Note**
> 
> If you enter a minus sign before a modifier's price, the value you enter is deducted from the menu item's price. Consider using this method if a guest wants to remove a costly ingredient such as meat from a pizza or salad.



10. Select Save.


11. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Adding an existing modifier to a modifier group

To reduce the number of modifiers you have to manage, add existing modifiers whenever possible instead of creating new ones. For example, a Breakfast Sides modifier group and a Burger Toppings modifier group could share a Bacon modifier.

If a modifier is used by more than one modifier group, keep in mind that:

- When you edit the modifier, it is edited for all the modifier groups that use it.


- When you remove the modifier from one of the modifier groups, the other modifier groups continue to use it.



For multi-location restaurants, you must have the Edit Full Menu permission to the owner of a modifier group in order to add an existing modifier to it.

**Procedure 8.89. To add an existing modifier to a modifier group**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate and expand the modifier group you want to add an existing modifier to.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. Select + Add modifier and enter a name for the modifier. A dropdown list appears that has a Create new option followed by a list of any existing modifiers that match the text you entered.


8. Select the existing modifier you want to add from the dropdown menu. Alternatively, use the down arrow to highlight the existing modifier and then press the Enterkey. The modifier is added to the Modifierstable.

If you have a multi-location restaurant:

- The dropdown list of matching modifiers is filtered so that you only see modifiers that both match the text you enter and have a target that is the same as the parent modifier group's target, or an ancestor or descendant of the parent modifier group's target. This ensures that the target of the modifier is compatible with the target of its parent modifier group.


- If the existing modifier is [versioned](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly), you see a single row in the Modifierstable and it displays the version with the highest target. For more information, see [Versioned modifiers (multi-location only)](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly).




9. Select Save.


10. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Editing a modifier's details

The Modifiers table in the modifier group side panel displays names and prices for the modifiers contained in the group (the Price column only appears if the modifiers in the group are [priced individually](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager)). To set other details for a modifier, such as button color and calories, you open its Edit modifier dialog by selecting the modifier's name in the Modifiers table.



> **Note**
> 
> To fully understand and edit a modifier, you should understand the concept of a modifier item reference. For more information, see [Understanding a modifier item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager).


For multi-location restaurants:

- If a modifier is [versioned](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly), you see a single row in the Modifiers table and it displays the version with the highest target. It is this highest-targeted version that you can see and edit in the Edit modifier dialog. To edit the other versions, you must go to their classic details pages. For more information, see [Versioned modifiers (multi-location only)](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly).



**Procedure 8.90. To set other details for a modifier**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. Select a modifier's name.

The Edit modifier dialog opens.

![The Edit modifier dialog.](https://doc.toasttab.com/doc/media/menu-manager-mod-option-details.png)


8. In the Edit modifier dialog, you can:

- Edit the modifier's name.

The name you see and edit here is either the modifier's item reference name or its override name, if one exists. For more information, see [Understanding a modifier item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager).


- Enter the number of calories for the modifier. If you enter a minus sign before a modifier's calorie value, the amount you enter is deducted from the menu item's calorie value. For example, for a No Cheese modifier, you could use the minus sign to deduct the cheese calories from the menu item.


- Specify a POS button color by selecting the POS button color option and then selecting a color from the color palette.


- View or edit the modifier's price:

If the modifier [inherits its price](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager) from its parent modifier group, you can view the price but you can't edit it. You must edit the price from the Pricing section of the modifier group's side panel instead.

If the modifier is [priced individually](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager) and uses a base price, you can edit the price in the Modifier price field. The price you see and edit here is either the modifier's item reference price or its override price, if one exists. For more information, see [Understanding a modifier item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager).

If the modifier is priced individually and uses an advanced pricing strategy, you can view the advanced price but you can't edit it. To edit the advanced price, use the More modifier settings link to go to the modifier's classic details page. From the classic modifier details page, you can access the modifier's [item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager) page where you can set an [advanced pricing strategy](adminPricingStrategyDetailsOmitChunkFromSearchIndex.html#adminPricingStrategiesOverview) for the modifier.




9. Select Update in the Edit modifier dialog.


10. Select Save in the side panel.


11. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Reordering modifiers

Your Toast ordering channels display your modifiers in the order you see them in the Full menu view. You can reorder your modifiers so they appear in the order you want them to.

For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a modifier group in order to change the display order of the modifiers it contains.


- If a modifier group is versioned, you must pick the version you want to change the display order for. The display order is updated for that version only. The other versions are not updated.


- If a modifier is versioned, all versions of that modifier are displayed in the same order within a modifier group.



**Procedure 8.91. To change the order of modifiers in a modifier group**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. Select a modifier's reorder icon and drag the row to its new location.

![The location of a modifier's reorder icon.](https://doc.toasttab.com/doc/media/menu-manager-modifiers-table-reorder.png)


8. Select Save.


9. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Removing a modifier from a group

When you remove a modifier from a modifier group, the modifier no longer appears in that modifier group, but the modifier remains in your Toast Web database and can still be added to or used by other modifier groups.

If the modifier belongs to multiple modifier groups, removing the modifier from one group has no effect on the others. They continue to use the modifier.

Modifier groups require at least one modifier, so the Toast platform prevents you from removing a modifier if it is the only one in the modifier group.



> **Note**
> 
> To remove a modifier from *all* modifier groups that use it, you must archive it using the modifier's classic details page.


For multi-location restaurants:

- You must have the Edit Full Menupermission to the owner of a modifier group in order to remove a modifier from it. For example, consider a Cheese modifier group that contains a Cheddar modifier. You must have Edit Full Menu permission to the owner of the Cheese modifier group to remove the Cheddar modifier from it.


- If a modifier group is versioned and you want to remove a modifier from it, you must pick the version you want to remove the modifier from. The modifier is removed from that version only. The other versions continue to use the modifier.


- If a modifier is versioned and you remove it from a modifier group, all versions of the modifier are removed from that group.



**Procedure 8.92. To remove modifiers from a modifier group**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. Select the modifier's delete icon.

![The location of a modifier's remove icon.](https://doc.toasttab.com/doc/media/menu-manager-modifiers-table-remove.png)


8. Select Save.


9. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



#### Specifying modifier prices

When you create a modifier group, you [specify how modifiers in that group are priced](platformWorkingWithModifierGroupsMenuManager.html#platformSpecifyingHowModifiersInAGroupArePricedMenuManager): no charge, all modifiers share the same price, or modifiers are priced individually. This section covers how to set prices for modifiers once you've chosen the pricing method for a modifier group.

##### Modifiers priced at the group level

When a modifier group is priced at the group level, all modifiers in the group use the same price. You can set a base price for the modifier group using the modifier group's side panel in the menu manager.

**Procedure 8.93. To set a base price for a modifier group**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Pricing section.


7. Select Group.


8. In the Price field, enter the base price.


9. Select Save.


10. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



To set an advanced pricing strategy for the modifier group, you use the classic modifier group details page, accessed by selecting the More settings link in the modifier group's side panel. Advanced price strategies include:

- [Size](adminSizePrice.html): The price of the modifier changes based on the size chosen for the menu item. For example, a topping on a small pizza costs $5 and topping on a large pizza costs $10.


- [Sequence](adminSequencePrice.html): The price of individual modifiers in a modifier group is determined by the sequence in which they are added to a menu item. For example, on a pizza menu item with a Toppings modifier group, the first topping is free, the second topping costs $5.00, the third topping costs $5.50, and all additional toppings cost $6.00.


- [Size/sequence](adminSizeSequencePrice.html): The price of a modifier depends on the size of the menu item it is applied to and the order in which it is applied to the menu item. For example, the first topping on a small pizza is $5.00 and additional toppings are $6 while the first topping on a large pizza is $10 and additional toppings are $11.



If a modifier group uses an advanced pricing strategy, the Pricing section in the modifier group's side panel lists the strategy and advises you to go to the classic modifier group details page to edit it.

##### Individually-priced modifiers that use base prices

Individually-priced modifiers that use base prices can be edited in the following locations:

- In Full menu view, using the Modifiers section of the modifier group side panel.


- In Full menu view, using the Price field of the Edit modifier dialog. You access the Edit modifier dialog by selecting a modifier's name in the Modifiers section of the modifier group side panel.


- In Modifiers view, using the Price column.



Changes you make in Modifiers view can either be [manually published](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) or [scheduled for future publishing](platformPublishingMenuManagerChanges.html). Full menu view does not support scheduled publishing, so you must manually publish pricing changes you make in Full menu view.

For multi-location restaurants:

- If a modifier is [versioned](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly), you see a single row for it in the Modifierssection of the modifier group side panel. This single row displays the name and price of the version with the highest target. It is also this highest-targeted version that you edit in the corresponding Edit modifier dialog.

To edit the other versions, you can use the Price column in Modifiers view or go to classic details pages for the modifier version you want to edit. For more information, see [Versioned modifiers (multi-location only)](platformWorkingWithModifiersMenuManager.html#platformVersionedModifiersMultiLocationOnly).



**Procedure 8.94. To set a base price for a modifier using the modifier group side panel**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. In the Modifiers table, enter the price for the modifier.


8. Select Save in the side panel.


9. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



**Procedure 8.95. To set a base price for a modifier using the Edit modifier dialog**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Full menu.


4. (Multi-location only) Select the locations whose menu data you want to edit from the [locations control](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation).


5. Use the [expand icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to locate the modifier group you want to edit.


6. Select the modifier group to view its side panel, then scroll to the Modifiers section.


7. In the Modifiers table, select the modifier's name to open its Edit modifierdialog.


8. Enter a base price in the Pricefield.


9. Select Update in the Edit modifier dialog.


10. Select Save in the side panel.


11. [Manually publish](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager) your changes when you are ready for guests and employees to see them.



**Procedure 8.96. To set a base price in Modifiers view**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Modifiers.


4. Use the [search field](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerSearchingForMenuEntities) or the [filtering controls](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringMenuEntities) to refine the list of modifiers.


5. To edit a modifier with a base price, enter the new price in the Price column.


6. Continue reading the [Publishing menu manager changes](platformPublishingMenuManagerChanges.html) section to understand how to make your menu changes available to restaurant employees and guests.



> **Important**
> 
> Modifiers view offers additional workflows for saving and publishing your pricing edits that are different from other configuration pages in Toast Web, including the ability to create a change set that saves and publishes your changes at a later date and time. In the menu manager, you *either* select Scheduleto create a change set *or*Save to save your changes immediately but you don't do both. If you select Save, your changes will be saved immediately and you will not be able to create a change set. Do not select Save in the menu manager until you fully understand the publishing workflows described in [Publishing menu manager changes](platformPublishingMenuManagerChanges.html).




##### Individually-priced modifiers that use advanced pricing strategies

Using a modifier's [item reference page](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager), you can specify advanced pricing strategies for the modifier, including [size](adminSizePrice.html#adminConfiguringSizePricingOnModifierGroupsAndModifierOptions), [menu-specific](adminMenuSpecificPrice.html), [location-specific](adminSettingLocationSpecificPricesOmitChunkFromSearchIndex.html#adminLocationSpecificPriceOverview), [time-specific](adminTimeSpecificPrice.html), and [open](adminOpenPrice.html)prices.

The menu manager provides partial support for editing advanced prices on modifiers, allowing you to edit size, menu-specific, and location-specific prices in the Price column of Modifiers view.

The Modifiers table in the modifier group side panel and the Edit modifier dialog do not support editing advanced prices. For modifiers that use advanced prices, you see the name of the pricing strategy and the price range but you cannot edit the price.



> **Note**
> 
> For multi-location restaurants, if the modifier uses a location-specific price, currently only the pricing strategy is displayed in the Modifiers table and the Edit modifier dialog. The price range is not displayed. To view the price range, you must go to the modifier's classic details page.


**Procedure 8.97. To edit an advanced price for a modifier in Modifiers view**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Menus > Menu management > Menu manager to open the Menu managerpage.


3. From the Show section, choose Modifiers.


4. Use the [search field](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerSearchingForMenuEntities) or the [filtering controls](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringMenuEntities) to refine the list of modifiers.


5. To edit a modifier with a size, menu-specific, or location-specific price, expand its row and enter the new prices in the Price column.



> **Note**
> 
> The menu manager only allows you to edit size prices that are already defined on a modifier's [classic details page](adminMenuManagerAndTheClassicMenuDetailsPages.html). If you need to add a price for another size, you must add the size's price on the classic details page first, before it is visible and available for editing on the Menu manager page. The same is true for menu-specific and location-specific prices. If you need to add a price for another menu or location, you must add the price on the classic details page first. For more information on adding size prices, see [Configuring size pricing on modifier groups and modifiers](adminSizePrice.html#adminConfiguringSizePricingOnModifierGroupsAndModifierOptions). For more information on adding menu-specific prices, see [Menu-specific price](adminMenuSpecificPrice.html). For more information on adding location-specific prices, see [Enabling and setting location-specific prices](adminEnablingAndSettingLocationSpecificPrices.html).




> **Note**
> 
> If a modifier is versioned, all of its versions that use location-specific pricing use the *same location-specific prices*. In this situation, the versioned modifier appears on multiple rows on the Modifiers view, one row per version, and the location-specific prices associated with the versions are identical. If you edit the location-specific prices for one version, they are edited for all versions. For more information, see [Location-specific prices and versions](adminLocationSpecificPricesAndVersions.html).



6. Continue reading the [Publishing menu manager changes](platformPublishingMenuManagerChanges.html) section to understand how to make your menu changes available to restaurant employees and guests.



> **Important**
> 
> Modifiers view offers additional workflows for saving and publishing your pricing edits that are different from other configuration pages in Toast Web, including the ability to create a change set that saves and publishes your changes at a later date and time. In the menu manager, you *either* select Scheduleto create a change set *or*Save to save your changes immediately but you don't do both. If you select Save, your changes will be saved immediately and you will not be able to create a change set. Do not select Save in the menu manager until you fully understand the publishing workflows described in [Publishing menu manager changes](platformPublishingMenuManagerChanges.html).




##### Modifiers that use override prices

When a modifier is based on an existing menu item, you can choose to use the price of the underlying menu item as the price of the modifier, or you can override that price with a price that is specific to the modifier. For example, the price of the Fries menu item could be $8 while the override price of the Fries modifier is $5.

Override prices are always base prices. Override price appears in the Modifiers table of the modifier group side panel, in the Price field of the Edit modifier dialog, and in the Pricecolumn of Modifiers view. If you edit an override price in any of those locations, it has no effect on the item reference price, only the override price is affected. For more information on setting override prices, see [Understanding a modifier item reference](platformWorkingWithModifiersMenuManager.html#platformUnderstandingAModifierItemReferenceMenuManager).

#### Viewing read-only modifier information

The Modifiers view of the menu manager provides additional read-only information about modifiers. For example, the Found in column displays information about where a modifier appears in the menu hierarchy. For more information, see [Items and modifiers view](platformColumnsInTheMenuManagerViews.html#platformMenuManagerItemAndModifierColumns).

