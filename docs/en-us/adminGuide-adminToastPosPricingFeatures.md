---
title: "Toast pricing features"
id: adminToastPosPricingFeatures
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu pricing"
previousSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
previousSectionTitle: "Menu pricing"
nextSectionFile: adminGuide-adminNoteAboutPublishingPrices.md
nextSectionTitle: "Note about publishing prices"
externalReferences: [https://central.toasttab.com/s/article/Creating-an-Open-Item-or-Open-Priced-Menu-Item-1492811097670]
excerpt: "The Toast platform offers a variety of pricing-related features that give you the flexibility to choose the pricing approaches that work best for your menu entities. The table below gives a brief..."
keywords: ["toast", "pricing", "features", "Open items", "Open Price pricing strategy"]
procedures: 0
codeExamples: 0
---

The Toast platform offers a variety of pricing-related features that give you the flexibility to choose the pricing approaches that work best for your menu entities. The table below gives a brief overview of each pricing feature and the types of menu entities you can use them for.


<table>
  <thead>
    <tr>
      <th>Pricing Feature</th>
      <th>Description</th>
      <th>Can be applied to</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="adminGuide-adminBasePrice">Base Price</a> pricing strategy</td>
      <td>The price of a menu entity, for example, $5. A base price can be used in conjunction with a more complex pricing strategy such as time-specific pricing or menu-specific pricing. When combined with a more complex pricing strategy, the base price provides a default price for cases where the more complex price does not apply. For example, if you specify a time-specific price for a menu item during the hours of 12 p.m. to 2 p.m., the base price is used for the menu item for any orders placed outside of that two-hour time period.</td>
      <td>Menu groups <br/> Menu items <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminTimeSpecificPrice">Time Specific Price</a> pricing strategy</td>
      <td>For example, a menu item that costs $10 between noon and 2p.m. and $12 during the rest of the day. <br/> For multi-location restaurants, the time-specific price is in each location's local time.</td>
      <td>Menu groups <br/> Menu items <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminMenuSpecificPrice">Menu Specific Price</a> pricing strategy</td>
      <td>For example, a menu item that costs $5 when it is ordered from the Lunch menu and $7 when it is ordered from the Dinner menu.</td>
      <td>Menu items <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminLocationSpecificPrice">Location Specific Price</a> pricing strategy</td>
      <td>Only applies to customers that use the enterprise module. <br/> For example, a steak that costs $18 at the Boston location and $20 at the New York City location.</td>
      <td>Menu items <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminSizePrice">Size Price</a> pricing strategy</td>
      <td>For example, a drink that costs $3 for the 12 ounce size and $4 for the 16 ounce size, or a pizza topping that costs $1 when it is added to a small pizza and $2 when its added to a large pizza. <blockquote><strong>Note</strong> Size pricing for menu items is supported on all product channels. Size pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see <a href="adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures">Toast product channel support for advanced pricing features</a>.</blockquote> </td>
      <td>Menu groups <br/> Menu items <br/> Modifier groups <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminOpenPrice">Open Price</a> pricing strategy</td>
      <td>Allows you to manually specify a price for a menu item at the time that menu item is ordered on the Toast POS app. The Open Price strategy can be set on individual menu items or at the menu group level. <br/> See also <strong>Open items</strong>  below for another pricing feature that handles menu items with open prices.</td>
      <td>Menu groups <br/> Menu items</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminFixedPrice">Fixed Price</a> pricing strategy</td>
      <td>Sets the same price for all modifiers in a modifier group. For example, all modifiers in the modifier group cost $1.</td>
      <td>Modifier groups</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminSequencePrice">Sequence Price</a> pricing strategy</td>
      <td>For example, the first modifier costs $3, the second costs $2, and the third costs $1. <blockquote><strong>Note</strong> Sequence pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see <a href="adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures">Toast product channel support for advanced pricing features</a>.</blockquote> </td>
      <td>Modifier groups</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminSizeSequencePrice">Size/Sequence Price</a> pricing strategy</td>
      <td>With size/sequence pricing, the cost of a modifier depends on the size of the menu item it is applied to and the order in which it is applied to the menu item. For example, the first topping on a small pizza is $0.50 and additional toppings are $1, while the first topping on a large pizza is $1.50 and additional toppings are $2.50 <blockquote><strong>Note</strong> Size/sequence pricing for modifiers is supported on the Toast POS app, Toast Online Ordering, and in the menu data returned to online ordering partners. It is not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk. For more information, see <a href="adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures">Toast product channel support for advanced pricing features</a>.</blockquote> </td>
      <td>Modifier groups</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminPricingModifierOptions#adminUsingSubstitutionPricingForDefaultModifierOptions">Substitution pricing</a></td>
      <td>Substitution pricing allows you to substitute one modifier for another and only charge the guest for the difference in price. For example, consider an entree salad that has a Protein modifier group with Chicken ($5), Salmon ($6) and Steak ($7) modifiers. By default, the entree salad comes with chicken and the price of the Chicken modifier is included in the price of the entree salad. Substitution pricing allows you to swap out the chicken for salmon or steak and then add the difference in protein price to the overall cost of the salad. For salmon, the additional charge is $1 and for steak the additional charge is $2.</td>
      <td>Modifier groups</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminUsingPriceLevels">Price levels</a></td>
      <td>Price levels allow you to price a collection of menu groups or menu items using the same price. For example, all draft beers are $6 while all bottled beers are $5. You define a price level and then assign it to the menu group or menu items that should use that price level. To make changes to all the menu groups or items that use a price level, you only need to change the price level itself, rather than every menu group and item it applies to.</td>
      <td>Menu groups <br/> Menu items <br/> <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">Modifier item references</a></td>
    </tr>
    <tr>
      <td>Open items</td>
      <td>Open items allow you to create a special request for a menu item that does not exist on your regular menu. When you create an open item on the Toast POS app, you give the item a name and a price and add it to a guest's check. Open items are configured on the Menus > Settings > Open items page. For information about configuring and using open items, see this <a href="https://central.toasttab.com/s/article/Creating-an-Open-Item-or-Open-Priced-Menu-Item-1492811097670">Toast Central article</a>. <br/> Also, see <strong>Open Price pricing strategy</strong>  above for another pricing feature that handles menu items with open prices.</td>
      <td>Menu groups <br/> Menu items</td>
    </tr>
  </tbody>
</table>

