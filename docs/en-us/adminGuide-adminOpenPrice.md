---
title: "Open price"
id: adminOpenPrice
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminPricingStrategyDetailsOmitChunkFromSearchIndex.md
parentSectionTitle: "Pricing strategies"
previousSectionFile: adminGuide-adminLocationSpecificPrice.md
previousSectionTitle: "Location-specific price"
nextSectionFile: adminGuide-adminFixedPrice.md
nextSectionTitle: "Fixed price"
externalReferences: [https://central.toasttab.com/s/article/Creating-an-Open-Item-or-Open-Priced-Menu-Item-1492811097670]
excerpt: "Applies to: Menu groups, menu items (not including modifier item references)"
keywords: ["open", "price", "Applies to:"]
procedures: 2
codeExamples: 0
---

**Applies to:** Menu groups, menu items (*not* including [modifier item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference))

The Toast platform provides two methods for working with menu items that require open prices, the Open Items feature and the Open Price pricing strategy.



> **Note**
> 
> Open prices are not supported by Toast Online Ordering. If you use Toast Online Ordering, do not use the Open Pricepricing strategy for any menu items that will be visible on your Toast online ordering website.


The Open Items feature allows you to create a special request for a menu item that does not exist on your regular menu. When you create an open item, you give the item a name and a price and add it to a guest's check. Open items are configured on the Menus \> Settings \> Open items page. For information on creating and using open items, see this [Toast Central article](https://central.toasttab.com/s/article/Creating-an-Open-Item-or-Open-Priced-Menu-Item-1492811097670).

The Open Price pricing strategy allows you to manually specify a price for a menu item when that menu item is ordered on the Toast POS app. For example, you may want to set the price of a menu item differently depending on the market price of that menu item on the day that it is ordered. The Open Price pricing strategy can be enabled on individual menu items or at the menu group level. This section provides information on configuring and using this strategy.

**Procedure 8.125. To enable open prices for a menu group or menu item**

1. In the Pricing Strategy section of the menu group or item's details page, select Open Price.


2. Save your changes.


3. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



**Procedure 8.126. To use open prices on the Toast POS app**

1. On the order screen, tap the menu item with an open price. You see a dialog with the menu item's name.

![Example of the dialog you use to set an open price in the Toast POS app.](https://doc.toasttab.com/doc/media/pricing-open-price.png)


2. Enter a price for the item and tap Done.



