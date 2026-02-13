---
title: "Menu-specific price"
id: adminMenuSpecificPrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminTimeSpecificPrice.md
previousSectionTitle: "Time-specific price"
nextSectionFile: adminGuide-adminLocationSpecificPrice.md
nextSectionTitle: "Location-specific price"
excerpt: "Applies to: Menu items (including modifier item references)"
keywords: ["menuspecific", "price", "Applies to:"]
procedures: 1
codeExamples: 0
---

**Applies to:** Menu items (including
    [modifier item
    references](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference))

With menu-specific pricing, the price of a menu item changes based
    on the menu it was ordered from, for example, a menu item that costs $5
    when it is ordered from the Lunch menu and $7 when it is ordered from the
    Dinner menu.



> **Important**
> 
> If your restaurant has multiple locations, there are additional
      best practices you should follow when configuring menu-specific prices.
      For more information, see [Menu-specific prices for multi-location restaurants](adminGuide-platformMenuSpecificPricesForMultiLocationRestaurants) in
      the [Multiple
      restaurant locations](adminGuide-sharingMenusAndOtherInformationAmongRestaurants) section.


You create menu-specific prices for a menu item on the item's
    details page. After you have created the menu-specific prices, you can
    view them in the Items grid that appears on the
    details page for any of the item's parent menu groups. However, the
    menu-specific prices are not editable from the Items
    grid.

The Items grid only displays one price,
    determined by the menu you are currently viewing. For example, consider
    the following scenario:

- You create a Fries menu item that costs $5 on the Lunch menu and
        $7 on the Dinner menu.


- The Fries menu item belongs to a Lunch Sides menu group in the
        Lunch menu and a Dinner Sides menu group in the Dinner menu.


- When you view the details page for the Lunch Sides menu group,
        the price of the Fries menu item in the Items
        grid is $5. When you view the details page for the Dinner Sides menu
        group, the price of the Fries menu in the Items
        grid is $7. A menu icon appears next to the price to indicate that it
        is a menu-specific price.



**Procedure 8.124. To create menu-specific prices for a menu item**

1. In the Pricing Strategy section of the menu
        item's details page, select Menu Specific
        Price.


2. In the
        Base Price field, enter a base price for the menu
        item. This price is used if a menu-specific price for the item cannot
        be calculated. For example, if you added the menu item to a newly
        created menu but neglected to update the menu item with a
        menu-specific price for the new menu.


3. In the Menu Prices grid, enter the price to
        be used for the menu item when it is ordered from each menu.



> **Note**
> 
> Technically, you only need to enter a price for each menu that
          contains the menu item but it is a best practice to enter a price
          for all menus in case you add the menu item to another menu in the
          future.



4. Save your changes.


5. [If you are done editing
        prices for your menus, publish your changes.](adminGuide-adminNoteAboutPublishingPrices)



Once you have created a menu-specific price, you can either return
    to the menu item's details page and edit it there, or edit it on the
    Price editor page. When editing a menu-specific price
    on the Price editor page, be sure to expand the menu
    that contains the menu-specific price you want to edit, locate the menu
    item within that menu, and enter a new price for the menu item.

On the Price editor page, you can also bulk
    convert prices to menu-specific prices. For more information, see [Using the price editor](adminGuide-adminUsingThePriceEditor).

