---
title: "Using the price editor"
id: adminUsingThePriceEditor
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu pricing"
previousSectionFile: adminGuide-adminPricingStrategies.md
previousSectionTitle: "Pricing strategies"
nextSectionFile: adminGuide-adminUsingPriceLevels.md
nextSectionTitle: "Using price levels"
excerpt: "The..."
keywords: ["price", "editor"]
procedures: 0
codeExamples: 0
---

The Price editor page displays prices for all
    of your menu groups and menu items in one location, where you can quickly
    view and edit them. It also provides features for bulk editing your
    prices, for example, increasing the prices of all of your sandwiches by
    $1.



> **Note**
> 
> Currently, the Price editor page does not
      display prices for modifier groups and modifiers. To edit prices for
      those, you must use the modifier group and modifier details
      pages.


## Price editor overview

To view the Price editor page, [access
      Toast Web](adminGuide-adminAccessToastAdminBackend) and then choose Menus > Bulk management
      > Price editor. Click the arrow next to a menu or menu
      group to expand it and see its children. Click a menu entity's name to
      view its details page.

### Understanding the Price column

The Price column displays the prices for
        your menu groups and items. Editing the contents of the
        Price column is equivalent to making changes on a
        menu group or menu item's details page.

Menu items that inherit their prices from a menu group are
        marked "inherited" in the Price column. Changing
        the price of a menu group changes the price of any menu items that
        inherit the menu group's price. Menu items that are individually
        priced show their prices in the Price column. In
        the example below, the Turkey Sandwich and Roast Beef Sandwich inherit
        their prices from the Sandwiches menu group while the Grilled Cheese
        Sandwich is individually priced.

![Example of how the price editor displays individually priced items and items that inherit their prices.](https://doc.toasttab.com/doc/media/pricing-price-editor-inherited-prices.png)

Icons in the area to the left of the Price
        column indicate the pricing strategy used for a menu group or item
        when a strategy other than [Base Price](adminGuide-adminBasePrice) is used. In the example
        above, the Grilled Cheese Sandwich uses the Base
        Price strategy so it has no pricing strategy icon. The
        examples below show the icons used for the other pricing
        strategies.

For menu groups and items that use the:

- [Size Price](adminGuide-adminSizePrice) strategy, each size
            appears on a separate row. In the example below, the small (SM)
            size of the Fries menu item is $2 and the large (LG) size is
            $4.

![Example of how the price editor displays a menu item that uses size pricing.](https://doc.toasttab.com/doc/media/pricing-price-editor-size-prices.png)


- [Time Specific Price](adminGuide-adminTimeSpecificPrice)
            strategy, the base price appears in the first row and the prices
            for other time periods appear in rows beneath the base price. In
            the example below, the Pasta Special is $9 between 12p.m. and
            2p.m. and $10 during the rest of the day.

![Example of how the price editor displays a menu item that uses time-specific pricing.](https://doc.toasttab.com/doc/media/pricing-price-editor-time-prices.png)


- [Menu Specific Price](adminGuide-adminMenuSpecificPrice)
            strategy, a menu icon appears next to the price and the price
            reflects the menu where that price is appearing. For example, in
            the illustration below, the Steak menu item costs $9 when it is
            ordered from the Breakfast menu.

If a menu group or item is configured to use a
            Menu Specific Price but a price has not been
            defined for it in a given menu, then the Price
            Editor shows the default base price that is defined as
            part of the Menu Specific Price
            configuration. The base price is shown in gray, without the menu
            icon, and you cannot edit it. In the Lunch menu below, the Steak
            menu item is using the default base price from a Menu
            Specific Price configuration.

![Example of how the price editor displays a menu item that uses menu-specific pricing.](https://doc.toasttab.com/doc/media/pricing-price-editor-menu-prices.png)


- [Location Specific
            Price](adminGuide-adminLocationSpecificPriceOverview) strategy, the location-specific prices appear on
            separate rows. The rows are ordered based on the restaurant
            hierarchy with the least specific location in the hierarchy first
            (Corporate in the example below) and the most specific location in
            the hierarchy last (NYC in the example).

![Example of how the price editor displays a menu item that uses location-specific pricing.](https://doc.toasttab.com/doc/media/pricing-price-editor-location-price.png)


- [Open Price](adminGuide-adminOpenPrice) strategy, the word
            "open" appears in the Price column. For
            example, the Breakfast Specials menu group below is configured to
            use open pricing.

![Example of how the price editor displays a menu item that uses open pricing.](https://doc.toasttab.com/doc/media/pricing-price-editor-open-price.png)


- [Price Levels](adminGuide-adminUsingPriceLevels), the
            Price editor page shows a price levels icon
            and the name of the price level but it does not display the price.
            To see the price, you must click the price level name to view the
            price level's details page.

![Example of how the price editor displays a menu item that uses price levels.](https://doc.toasttab.com/doc/media/pricing-price-editor-price-levels.png)



### Filtering by pricing strategy

To make it easier to locate and edit prices on the
        Price editor page, you can filter the prices you
        see by pricing strategy. Choose the pricing strategy you want from the
        menu in the upper-right corner of the page. The page is filtered to
        show only menu groups and items that use that pricing strategy. To
        return to viewing all prices, choose All
        Strategies from this menu.

![The location of the pricing strategy filter on the Price Editor page.](https://doc.toasttab.com/doc/media/pricing-price-editor-strategy-filter.png)

## Using the Price Editor to make bulk edits

To make a bulk edit in the Price Editor, you
      choose the menu groups and menu items that the bulk edit will apply to
      and then you choose the type of edit to make. You can choose to set the
      prices to a specific dollar value, or to increase or decrease them by a
      dollar or percentage amount. The numeric prices of the menu groups and
      items change to reflect the edits you make. However, these changes have
      no affect on your inheritance or pricing strategy configuration. Menu
      items that inherit their prices continue to inherit them. Pricing
      strategies you have specified remain in effect but the prices configured
      for those strategies are updated. For example, consider the following
      time-specific prices:

![Example of menu items that use time-specific prices.](https://doc.toasttab.com/doc/media/pricing-price-editor-time-prices.png)

If you used to the Set to option to update
      these time-specific prices to $12, the prices would look like this
      following the update operation:

![The same example after resetting the time-specific prices to $12.](https://doc.toasttab.com/doc/media/pricing-price-editor-set-to-example.png)

The prices continue to be time-specific prices but their values
      have all been changed to $12.

**Procedure 8.115. To make bulk edits using the Price Editor**

1. [Access Toast Web
          ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus > Bulk management > Price
          editor to open the Price editor
          page.


3. Expand the menus and menu groups to view the prices you want
          to make bulk changes to.


4. Select the menu groups and items you want to edit by clicking
          the box on the left side of the menu group or item's row. If you
          select a menu group, all of its menu items and sub-groups are
          automatically selected.


5. Click the Update menu and choose the type
          of update you want to make:

- Set to: The prices for the menu
              groups or items you have selected are updated to the dollar
              value you specify.


- Increase by $: The prices for the
              menu groups or items you have selected are increased by the
              dollar amount you specify. To decrease the prices, enter a
              negative number in this field, for example, -1.00.


- Increase by %: The prices for the
              menu groups or items you have selected are increased by the
              percentage you specify. For example, if an item costs $1 and you
              increase prices by 20%, the item costs $1.20. To decrease the
              prices, enter a negative number in this field, for example,
              -20.




6. Click Update.


7. Save your changes.


8. [If you are done editing
          prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



## Converting to menu-specific or location-specific prices

The Price editor page allows you to quickly
      convert the prices of menu items to menu-specific or location-specific
      prices.

### Converting menu items to menu-specific prices

The Price editor page provides a quick
        option to convert a menu item that is individually priced using the
        Base Price pricing strategy into one that uses
        the Menu Specific Price pricing strategy.



> **Note**
> 
> You cannot convert menu items that use the more complex
          pricing strategies such as Time Specific Price
          or Location Specific Price. Also, you cannot
          convert menu items that inherit their pricing from a menu
          group.


**Procedure 8.116. To convert a menu item to use a menu-specific price**

1. [Access Toast Web
            ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus > Bulk management > Price
            editor to open the Price editor
            page.


3. Expand the menus and menu groups to view the menu item you
            want to convert.


4. Select the menu item by clicking the box on the left side of
            the menu item's row.


5. Click the Update menu and choose
            Convert to Menu-Specific Price.

"Menu-specific price" appears to the left of the
            Price column to indicate that the pricing
            strategy of the menu item has changed. The Base
            Price that was defined for the menu item becomes the
            [default base
            price](adminGuide-adminMenuSpecificPrice#adminDefaultBasePriceForMenuSpecificPrice) of the Menu Specific Price
            pricing strategy.


6. Click Save to save the pricing strategy
            change, after which you can set the individual menu-specific
            prices.


7. Locate the menu item in a menu. If the default base price is
            acceptable, no changes are necessary. If the base price is not
            acceptable, edit the menu-specific price and click
            Save. Repeat this step for each instance of
            the menu item (for example, if a menu item is included in both the
            Lunch and Dinner menus, you perform this step twice).



> **Note**
> 
> An issue in the Toast platform prevents you from editing
              all of the menu-specific prices for a converted menu item in one
              action. You must edit each instance of the menu item
              individually and click Save after each
              edit.



8. [If you are done editing
            prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



### Converting menu items to location-specific prices

For customers that use the enterprise module, the
        Price Editor page provides a quick option to
        convert a menu item that is individually priced using the
        Base Price pricing strategy to one that uses the
        Location Specific Price pricing strategy.



> **Note**
> 
> You cannot convert menu items that use the more complex
          pricing strategies such as Time Specific Price
          or Location Specific Price. Also, you cannot
          convert menu items that inherit their pricing from a menu
          group.


**Procedure 8.117. To convert a menu item to use a location-specific
          price**

1. [Access Toast Web
            ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus > Bulk management > Price
            editor to open the Price editor
            page.


3. Expand the menus and menu groups to view the menu item you
            want to convert.


4. Select the menu item by clicking the box on the left side of
            the menu item's row.


5. Click the Update menu and choose
            Convert to Location-Specific Price.


6. Click Save and *refresh the
            page*. This enables the location-specific price settings
            for the menu item, where you can add more location-specific
            prices. For more information about using these settings, see
            [Procedure 5.7, “To set location-specific prices for a menu item using the Price
      Editor”](adminGuide-adminEnablingAndSettingLocationSpecificPrices#adminToSetLocationSpecificPricesOnAMenuItem).


7. [If you are done editing
            prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



