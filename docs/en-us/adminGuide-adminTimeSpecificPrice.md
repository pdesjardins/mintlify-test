---
title: "Time-specific price"
id: adminTimeSpecificPrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminBasePrice.md
previousSectionTitle: "Base price"
nextSectionFile: adminGuide-adminMenuSpecificPrice.md
nextSectionTitle: "Menu-specific price"
excerpt: "Applies to: Menu groups, menu items (including modifier item references)"
keywords: ["timespecific", "price", "Applies to:"]
procedures: 1
codeExamples: 0
---

**Applies to:** Menu groups, menu items (including [modifier item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference))

With time-specific pricing, you define the price of a menu group or item during specific times of the day. For example, a menu item that costs $10 between noon and 2pm and $12 during the rest of the day. With time-specific pricing, you also specify a base price that functions as a default price for times of day when a time-specific price has not been defined.

You create time-specific prices for a menu group or menu item on the group or item's details page. After you have created time-specific prices for menu items, you can view them in the Items grid that appears on the details page for any of the item's parent menu groups. However, the time-specific prices are not editable from the Items grid. To edit a time-specific price, you can either return to the menu group or item's details page and edit it there, or edit it on the [Price editor](adminUsingThePriceEditor.html) page.

For multi-location restaurants, the time-specific price is in each location's local time.

**Procedure 8.123. To create time-specific prices for a menu group or menu item**

1. In the Pricing Strategy section of the menu group or item's details page, select Time Specific Price.


2. In the Base Price field, enter a base price for the menu group or item. This price is used during any time periods that are not covered by the time-specific prices you create in the Time Prices grid.


3. In the Time Prices grid, specify the first time-specific price by entering the start and end times for the price, choosing the days on which the price will be active, and entering the price amount.


4. To create additional time-specific prices, click Add to add rows to the grid. Fill out the rows for the time-specific prices you want to create. Be careful to avoid overlapping time-specific prices. For example, if you specify a time-specific price from 8:00am to 12:00pm and then another time-specific price for 12:00pm to 9:00pm, a pricing conflict exists for any menu item ordered at exactly 12:00pm. To avoid this conflict, the time-specific prices should be set to 8:00am to 11:59am and 12:00pm to 9:00pm.


5. To remove a time-specific price, click the trash can icon in the price's row.


6. Save your changes.


7. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



