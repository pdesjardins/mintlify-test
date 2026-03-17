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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Pricing Feature</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Can be applied to</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminBasePrice" className="">Base Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of a menu entity, for example, $5. A base price can be used in conjunction with a more complex pricing strategy such as time-specific pricing or menu-specific pricing. When combined with a more complex pricing strategy, the base price provides a default price for cases where the more complex price does not apply. For example, if you specify a time-specific price for a menu item during the hours of 12 p.m. to 2 p.m., the base price is used for the menu item for any orders placed outside of that two-hour time period.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminTimeSpecificPrice" className="">Time Specific Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For example, a menu item that costs $10 between noon and 2p.m. and $12 during the rest of the day.</p> <p className="text-base leading-relaxed">For multi-location restaurants, the time-specific price is in each location's local time.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminMenuSpecificPrice" className="">Menu Specific Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For example, a menu item that costs $5 when it is ordered from the Lunch menu and $7 when it is ordered from the Dinner menu.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminLocationSpecificPrice" className="">Location Specific Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only applies to customers that use the enterprise module.</p> <p className="text-base leading-relaxed">For example, a steak that costs $18 at the Boston location and $20 at the New York City location.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminSizePrice" className="">Size Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed">Modifier groups</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminOpenPrice" className="">Open Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows you to manually specify a price for a menu item at the time that menu item is ordered on the Toast POS app. The **Open Price** strategy can be set on individual menu items or at the menu group level.</p> <p className="text-base leading-relaxed">See also <strong className="font-semibold">Open items</strong>  below for another pricing feature that handles menu items with open prices.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminFixedPrice" className="">Fixed Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets the same price for all modifiers in a modifier group. For example, all modifiers in the modifier group cost $1.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier groups</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminSequencePrice" className="">Sequence Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier groups</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminSizeSequencePrice" className="">Size/Sequence Price</a> pricing strategy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier groups</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUsingSubstitutionPricingForDefaultModifierOptions" className="">Substitution pricing</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Substitution pricing allows you to substitute one modifier for another and only charge the guest for the difference in price. For example, consider an entree salad that has a Protein modifier group with Chicken ($5), Salmon ($6) and Steak ($7) modifiers. By default, the entree salad comes with chicken and the price of the Chicken modifier is included in the price of the entree salad. Substitution pricing allows you to swap out the chicken for salmon or steak and then add the difference in protein price to the overall cost of the salad. For salmon, the additional charge is $1 and for steak the additional charge is $2.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier groups</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-adminUsingPriceLevels" className="">Price levels</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Price levels allow you to price a collection of menu groups or menu items using the same price. For example, all draft beers are $6 while all bottled beers are $5. You define a price level and then assign it to the menu group or menu items that should use that price level. To make changes to all the menu groups or items that use a price level, you only need to change the price level itself, rather than every menu group and item it applies to.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p> <p className="text-base leading-relaxed"><a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">Modifier item references</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Open items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Open items allow you to create a special request for a menu item that does not exist on your regular menu. When you create an open item on the Toast POS app, you give the item a name and a price and add it to a guest's check. Open items are configured on the **Menus &gt; Settings &gt; Open items** page. For information about configuring and using open items, see this <a href="https://central.toasttab.com/s/article/Creating-an-Open-Item-or-Open-Priced-Menu-Item-1492811097670" className="">Toast Central article</a>.</p> <p className="text-base leading-relaxed">Also, see <strong className="font-semibold">Open Price pricing strategy</strong>  above for another pricing feature that handles menu items with open prices.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menu groups</p> <p className="text-base leading-relaxed">Menu items</p></div></td>
    </tr>
  </tbody>
</table>
</div>

