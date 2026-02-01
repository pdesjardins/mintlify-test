---
title: "Columns in the menu manager views"
id: platformColumnsInTheMenuManagerViews
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformWorkingWithMenuManagerChangeSets.md
previousSectionTitle: "Working with menu manager change sets"
nextSectionFile: adminGuide-platformMenuManagerLimitations.md
nextSectionTitle: "Menu manager limitations"
excerpt: "The specific columns in the menu manager change according to the entity type you are viewing. The following sections describe the columns for each entity type."
keywords: ["columns", "menu", "manager", "views"]
procedures: 0
codeExamples: 0
---

### Columns in the menu manager views

The specific columns in the menu manager change according to the entity type you are viewing. The following sections describe the columns for each entity type.

#### Full menu view

This section describes the columns you see in the Full menu view.

![An example of Full menu view.](https://doc.toasttab.com/doc/media/menu-manager-full-menu-view-multi-location.png)

##### Name

The Name column contains the name for the menu.

##### Available at (target) (multi-location only)

The Available at (target) column only appears for multi-location restaurants.

The Available at (target) column contains the name of the location group or individual location that uses the menu. If the target's name is too long to fit in the column, hover your mouse over it to see the full name.

##### Number (multi-location only)

The Number column only appears for multi-location restaurants.

The Number column lists the multi-location number for the menu. A multi-location number lets you identify related versions of the same menu. Menus with the same number are versions of the same menu. For more information about versions, see [Versions](versions.html).

#### Items and modifiers view

This section describes the columns you see in the Items and Modifiersviews.

![An example of the Items view.](https://doc.toasttab.com/doc/media/menu-manager.png)

##### Name

The Name column contains the name for the menu item or modifier.

For multi-location restaurants, this column also lists the multi-location number for the menu item or modifier. A multi-location number lets you identify related [versions](versions.html) of the same menu entity. Menu entities with the same number are versions of the same menu entity. For example, in the illustration below, the Fried Egg menu item has two versions, one used by the CORPORATE restaurant group (and its subgroups and locations) and another used only by the Boston location:

![An example of two related versions of the same menu item and their identical multi-location number.](https://doc.toasttab.com/doc/media/menu-manager-number-field.png)

For more information on the multi-location number, see [Viewing different versions of the same configuration entity](viewingDifferentVersionsOfTheSameConfigurationEntity.html).

Keep in mind that a menu item or modifier may have more versions than those you see in the menu manager, depending on the locations you have chosen to view. For example, Menu Item A has three versions, one each for the Boston, Miami, and New York City locations. If you are viewing the Boston and Miami locations on the Menu manager page, you see two rows for the Boston and Miami versions. The New York City version is not visible.

##### Change set indicator

If the menu item or modifier is included in any change sets, you see a calendar icon on its row with a number that indicates the number of change sets it is included in.

![The location of the calendar icon for a menu item that has a price update.](https://doc.toasttab.com/doc/media/menu-manager-changeset-indicator.png)

If you have updated one or more size prices within a set of size prices, the calendar icon appears next to each size price you edited and also at the top of the expandable row. The same is true if you edit one or more menu-specific or location-specific prices.



> **Note**
> 
> Location-specific prices are only available for multi-location restaurants.


Change sets are part of the scheduled publishing feature. They are used to store menu updates that are scheduled to be saved and published at a later date and time. Select the calendar icon to see the list of the change sets a menu entity is included in. Select a change set from the list to view the change set.

For more information on scheduled publishing and change sets, see [Understanding scheduled publishing and change sets](platformUnderstandingScheduledPublishingAndChangeSets.html).

##### Target (multi-location only)

The Target column only appears for multi-location restaurants.

The Target column contains the menu item or modifier's [target](targets.html). A target is a location group or individual location that uses the menu item or modifier. If the menu item or modifier is targeted at a location group, the line below the location group's name indicates the number of subgroups and individual locations the location group contains. These subgroups and locations also use the menu item or modifier.

##### Found in

The Found in column displays information about where a menu item or modifier appears in the menu hierarchy.

The Found in column is limited to two levels of menu hierarchy. For a menu item, this means that the Found in column lists the menu that contains the item and the item's immediate parent menu group. For example, consider the following menu hierarchy:

```
Breakfast Menu [menu]
    Food [menu group]
        Egg Dishes [menu subgroup]
            3-egg Omelet [menu  item]
```

For the 3-egg Omelet menu item, the Found in column displays `Breakfast Menu \> Egg
        Dishes`.

For modifiers, the Found in column lists the item or menu group that the modifier applies to along with the modifier's immediate parent modifier group. For example, consider the following menu hierarchy:

```
Breakfast Menu [menu]
    Food [menu group]
        Egg Dishes [menu subgroup]
            3-egg Omelet [menu  item]
                Cheese [modifier group]
                    Cheddar [modifier]
```

For the Cheddar modifier, the Found incolumn displays `3-egg Omelet \> Cheese`.

If an item or a modifier is found in more than one location in the menu hierarchy, you see the first location in the Found in column and + [x] other(s) to indicate there are other locations. Hover your cursor over the item or modifier's Found in column to see a pop-up with the other locations.

![An example of the pop-up with additional found in locations.](https://doc.toasttab.com/doc/media/menu-manager-found-in-hover.png)

##### Visibility

In the Visibility column, you can see where a menu item or modifier is visible and available for ordering. Options include:

- POS: The menu item is visible on Toast POS devices.


- Kiosk, Toast Order & Pay: The menu item is visible on Toast Kiosk devices, on the Toast Mobile Order and Pay app, and on Toast digital menus (previously called Menu & Pay). This setting requires visibility on Toast POS devices, so if you select this option, the option for POS visibility is also automatically selected.


- Toast Online Ordering, Toast Takeout (Local by Toast) app: The menu item is visible on a restaurant's Toast Online Ordering site and on the Toast Takeout (Local by Toast) app.


- Online ordering partners: The menu item is visible to all of the online ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub).



> **Note**
> 
> The menu manager does not yet support setting visibility for specific online ordering partners.




Currently, the Visibility column is only editable for menu items. For modifiers, you can see the Visibility column but it is not editable. Hover your cursor over the Visibility column for a menu item or modifier to see its full list of visibility settings.

##### Price on

The Price on column provides information about where a menu item or modifier's price is set:

- For menu items, the Price on column contains Item when the menu item is priced individually. The column contains Menu groupwhen the item inherits its price from a parent menu group.


- For modifiers, the Price on column always contains Modifier to indicate that you are viewing the price configured on the individual modifier.



Modifiers can belong to multiple modifier groups. The modifier price you see in the menu manager is only used by modifier groups that are priced at the individual modifier level. Modifier groups that are priced at the group level or do not charge for their modifiers ignore the individual price. If you edit the individual price, but the modifier is priced at the group level or doesn't charge for its modifiers, then the price you specify in the menu manager has no effect. For more information on pricing modifier groups, see [Setting the pricing method for a modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).

##### Price strategy

The Price strategy column contains the menu item or modifier's pricing strategy.

For menu items or modifiers that use size-specific prices, the Price strategy column lists the `Size-specific` strategy in the top row of the expanded menu item or modifier. Subsequent rows list the specific sizes that the prices apply to.

![An example of expanding the row for a menu item that uses size prices.](https://doc.toasttab.com/doc/media/menu-manager-size-prices.png)

For menu items or modifiers that use menu-specific prices, the Price strategy column lists the `Menu-specific` strategy in the top row of the expanded menu item or modifier. Subsequent rows list the specific menus that the prices apply to and the default price. The default price is used if a menu-specific price for the item or modifier cannot be calculated. For example, if you added the item to a newly created menu but forgot to update the menu item with a menu-specific price for the new menu.

![An example of expanding the row for a menu item that uses menu-specific prices.](https://doc.toasttab.com/doc/media/menu-manager-menu-specific-prices.png)

For menu items or modifiers that use location-specific prices, the Price strategy column lists the `Location-specific` strategy in the top row of the expanded menu item or modifier. Subsequent rows list the specific locations that the prices apply to.



> **Note**
> 
> Location-specific prices are only available for multi-location restaurants.


![An example of expanding the row for a menu item that uses location-specific prices.](https://doc.toasttab.com/doc/media/menu-manager-location-specific-prices.png)

Location-specific prices can be further customized with additional pricing strategies. For example, consider the following Crab Cakes menu item that has menu-specific prices that vary depending on the location where the Crab Cakes are ordered:

- At the Boston location:

- On the Lunch menu, Crab Cakes cost $11


- On the Dinner menu, Crab Cakes cost $15




- At the Portland location:

- On the Lunch menu, Crab Cakes cost $12


- On the Dinner menu, Crab Cakes cost $16




- All other locations use the Corporate price:

- On the Lunch menu, Crab Cakes cost $10


- On the Dinner menu, Crab Cakes cost $14





For this pricing scenario, the Pricing strategy column lists the Location-specific strategy and + Menu-specific in the top row of the expanded menu item or modifier. Subsequent rows list the specific location and menu combinations that the prices apply to and the default price. The default price is used if a menu-specific price for the item or modifier cannot be calculated. For example, if you added the item to a newly created menu but neglected to update the menu item with a menu-specific price for the new menu.

![An example of an expanded row for a menu item that uses location-specific prices with nested menu-specific prices.](https://doc.toasttab.com/doc/media/menu-manager-lsp-with-nested-msps.png)

If a menu item or modifier uses location-specific prices, and those location-specific prices use a variety of nested pricing strategies, then the top row displays Location-specific and + Nested strategy. The illustration below shows an example where the Boston and Portland locations use nested menu-specific prices but the Corporate location uses a nested base price.

![An example of an expanded row for a menu item that uses location-specific prices with a variety of nested pricing strategies.](https://doc.toasttab.com/doc/media/menu-manager-lsp-with-nested-variety.png)



> **Note**
> 
> Currently, the menu manager only supports editing nested base prices and menus-specific prices under location-specific prices.


##### Price

The Price column contains the menu item or modifier's price or price range.

You can edit the prices in this column for menu items or modifiers that are priced individually and use the base, size, menu-specific, or location-specific pricing strategy. Menu items or modifiers that use size, menu-specific, or location-specific prices have an [expandable row](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows). The top of the expandable row contains the price range. The expanded rows contain the editable size, menu-specific, or location-specific prices.

For pricing configurations that the menu manager does not yet support, you can see pricing information but it is not editable. You must continue to edit the prices for these menu items or modifiers outside of the menu manager. This includes:

- Menu items that are priced at the menu group level.


- Menu items or modifiers that are individually priced with a strategy other than base, size, menu-specific, or location-specific price.



It is important to remember that the modifier prices you see in the menu manager are *individual prices*. A modifier's individual price is overridden when it is included by a modifier group that is priced at the group level. For more information, see [Price on](platformColumnsInTheMenuManagerViews.html#platformMenuManagerItemAndModifierColumns_PriceOn).

For location-specific prices, there are some additional points to keep in mind:

- If a menu item or modifier uses the location-specific pricing strategy, the location-specific prices must be base prices or menu-specific prices for them to be editable in the menu manager. Location-specific prices that use one of the other [advanced pricing strategies](adminToastPosPricingFeatures.html) are not editable. For more information, see [Using pricing strategies with location-specific prices](adminUsingPricingStrategiesWithLocationSpecificPrices.html)and [Menu-specific prices for multi-location restaurants](platformMenuSpecificPricesForMultiLocationRestaurants.html).


- If you are filtering by location, the location-specific prices you see in the Price column are also filtered. For example, Menu Item A has location-specific prices for the Boston and Miami locations but you are currently filtering the menu manager to view only menu items for the Boston location. In this scenario, the Boston location-specific price appears in the Price column for Menu Item A but the Miami location-specific price does not.


- If a menu item or modifier is versioned, all versions of the menu item or modifier that use location-specific pricing use *the same location-specific prices*. Editing the location-specific prices for one version edits them for all versions. For more information, see [Location-specific prices and versions](adminLocationSpecificPricesAndVersions.html).



#### Price levels view

This section describes the columns you see in the Price levels view.

![An example of the Price levels view.](https://doc.toasttab.com/doc/media/menu-manager-price-level-columns.png)



> **Note**
> 
> For more information on price levels, see [Using price levels](adminUsingPriceLevels.html).


##### Name

The Name column contains the name for the price level.

For multi-location restaurants, this column also lists the multi-location number for the price level. A multi-location number lets you identify related [versions](versions.html) of the same menu entity. Menu entities with the same number are versions of the same menu entity. For more information on the multi-location number, see [Viewing different versions of the same configuration entity](viewingDifferentVersionsOfTheSameConfigurationEntity.html).

Keep in mind that a price level may have more versions than those you see in the menu manager, depending on the locations you have chosen to view. For example, Price Level A has three versions, one each for the Boston, Miami, and New York City locations. If you are viewing the Boston and Miami locations on the Menu manager page, you see two rows for the Boston and Miami versions. The New York City version is not visible.

##### Change set indicator

If a price level is included in any change sets, you see a calendar icon on its row with a number that indicates the number of change sets it is included in.

![The location of the calendar icon for a price level that has a price update.](https://doc.toasttab.com/doc/media/menu-manager-changeset-indicator-price-levels.png)

Change sets are part of the scheduled publishing feature. They are used to store menu updates that are scheduled to be saved and published at a later date and time. Select the calendar icon to see the list of the change sets a price level is included in. Select a change set from the list to view the change set.

For more information on scheduled publishing and change sets, see [Understanding scheduled publishing and change sets](platformUnderstandingScheduledPublishingAndChangeSets.html).

##### Target (multi-location only)

The Target column only appears for multi-location restaurants.

The Target column contains the price level's [target](targets.html). A target is a location group or individual location that uses the price level. If the price level is targeted at a location group, the line below the location group's name indicates the number of subgroups and individual locations the location group contains. These subgroups and locations also use the price level.

##### Price strategy

The Price strategy column contains the price strategy used by the price level.

On its details page, a price level can be configured to use one of the advanced pricing strategies, like menu-specific or time-specific price. However, currently you can only edit a price level in the menu manager if it uses the Basestrategy. If a price level uses an advanced pricing strategy, the strategy name is listed in the Price strategycolumn and a price range is shown in the Pricecolumn but you cannot edit it.

##### Price

The Price column contains the price that is set for the price level.

Currently, you can only edit a price level in the menu manager if it uses the Base strategy. If a price level uses an advanced pricing strategy, the strategy name is listed in the Price strategy column and a price range is shown in the Price column but you cannot edit it.

