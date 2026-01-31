---
title: "Menu manager limitations"
id: platformMenuManagerLimitations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformColumnsInTheMenuManagerViews.md
previousSectionTitle: "Columns in the menu manager views"
nextSectionFile: adminGuide-adminMenuVisibilityOmitChunkFromSearchIndex.md
nextSectionTitle: "Menu visibility"
excerpt: "This section lists the current limitations of the menu manager."
keywords: [menu,manager,limitations]
procedures: 0
codeExamples: 0
---

### Menu manager limitations

This section lists the current limitations of the menu manager.

- Full menu view limitations include the following:

- Updates made in the Full menu view must be [published manually](platformPublishingMenuManagerChanges.html#platformSavingChangesAndManuallyPublishingThemMenuManager). You cannot use the scheduled publishing feature with Full menu view updates.


- For single-location restaurants, you can reorder menu groups within their parent menu or menu group. You cannot move menu groups from one menu to another menu, or from one menu group to another menu group.


- You cannot reorder or remove modifier groups in Full menu view. You must use the classic pages for the menu group or item that contains the modifier groups instead.


- If you make any changes to a menu group, subgroup, or item that have not been saved yet, they are lost when you select Add modifier group from a menu item or menu group side panel to open the Create modifier group page. To avoid this issue, save the changes before creating the new modifier group.


- Some edits, for example, adding a modifier to a modifier group, require you to refresh the page before you see the changes in Full menu view.


- Multi-location restaurants also have the following limitations:

- The side panel for menu groups shows a very shortened version of a menu group details page with properties such as name, POS name, color, target, and owner. Selecting the full screen icon in the menu group side panel takes you to the [classic menu group details page](adminMenuManagerAndTheClassicMenuDetailsPages.html). The menu manager does not yet have a full screen version of the menu group details page.


- The reordering feature in Full menuview that allows you to reorganize the order of your menus, menu groups, and menu items is not yet supported for multi-location restaurants.


- The location filter setting is not retained when you move to the Full menu view from any of the other views.


- The menu group side panel does not have the Modifier groups card yet, so you cannot add new or existing modifier groups in the side panel. You must go to a menu group's [classic details page](adminMenuManagerAndTheClassicMenuDetailsPages.html) to add modifier groups to it.


- If a modifier uses a location-specific price, only the pricing strategy is displayed in the Modifiers table and the Edit modifier dialog. The price range is not displayed. To view the price range, you must go to the modifier's classic details page.






- You can edit prices for:

- Menu items and modifiers that use the base price, size price, menu-specific, or location-specific pricing strategies. Other pricing strategies are not yet supported. The menu manager displays prices for menu items or modifiers that use the other pricing strategies but they are not editable.

If a menu item or modifier uses the location-specific pricing strategy, the location-specific prices must be base prices or menu-specific prices (in other words, the location-specific prices cannot use one of the other [advanced pricing strategies](adminMenuPricingOmitChunkFromSearchIndex.html#adminToastPosPricingFeatures)).

Also, the menu manager only allows you to edit location-specific prices that are already defined on a menu item or modifier's details page. If you need to add a price for another location, you must add the location's price on the details page first, before it is visible and available for editing on the Menu manager page. The same is true for size and menu-specific prices. If you need to add a price for another size or menu, you must add the price on the details page first. For more information on adding size prices, see [Configuring size pricing on menu groups and menu items](adminSizePrice.html#adminConfiguringSizePricingOnMenuGroupsAndMenuItems)and [Configuring size pricing on modifier groups and modifiers](adminSizePrice.html#adminConfiguringSizePricingOnModifierGroupsAndModifierOptions). For more information on adding menu-specific prices, see [Menu-specific price](adminMenuSpecificPrice.html). For more information on adding location-specific prices, see [Enabling and setting location-specific prices](adminEnablingAndSettingLocationSpecificPrices.html).


- Price levels that use the base pricing strategy. Other pricing strategies are not yet supported. The menu manager displays prices for price levels that use the other pricing strategies but they are not editable.




- You cannot edit prices for:

- Menu groups.


- A menu item that inherits its price from a parent menu group.




- Modifiers can belong to multiple modifier groups. The modifier price you see in Modifiers view is only used by modifier groups that are priced at the individual modifier level. Modifier groups that are priced at the group level ignore the individual price in Modifiers view. If you edit the individual price in Modifiers view, but the modifier is priced at the group level, then the price you specify in Modifiers view will have no effect.


- Modifiers and price levels must have been published at least once before you can use the menu manager's Schedule button to schedule updates for them. For example, you create Price Level A. You must publish Price Level A before you can edit Price Level A in the menu manager and schedule those edits to be published at a future date and time.

The Toast platform handles menu items that have not been published at least once differently. For more information, see [Scheduling changes for menu entities that have not been previously published](platformPublishingMenuManagerChanges.html#platformSchedulingChangesForMenuEntitiesThatHaveNotBeenPreviouslyPublished).


- The Columns selector is currently only available for items and modifiers.


- The menu manager has some functional overlap with the older price editor, however, some features are still only available in the price editor. Specifically, you cannot do the following in the menu manager:

- Increase a set of prices by a dollar or percentage amount.


- Convert prices from one pricing strategy to another.


- Filter by pricing strategy.





