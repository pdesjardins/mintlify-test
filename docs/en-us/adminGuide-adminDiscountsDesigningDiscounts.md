---
title: "Designing discounts for promotions"
id: adminDiscountsDesigningDiscounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminConfiguringDiscountsOmitChunkFromSearchIndex.md
parentSectionTitle: "Creating and updating discounts"
previousSectionFile: adminGuide-adminConfiguringDiscountsOmitChunkFromSearchIndex.md
previousSectionTitle: "Creating and updating discounts"
nextSectionFile: adminGuide-adminAvailableDiscounts.md
nextSectionTitle: "Using the Discounts page"
excerpt: "You can use Toast platform discounts to support the promotions that your restaurants offer. Those promotions must be compatible with the Toast platform discount configuration interface."
keywords: ["designing", "discounts", "promotions"]
procedures: 0
codeExamples: 0
---

### Designing discounts for promotions

You can use Toast platform discounts to support the promotions that your restaurants offer. Those promotions must be compatible with the Toast platform discount configuration interface.

The Toast platform discount configuration interface makes it easy to create many types of promotional discounts. Depending on how you configured your menu, in particular with menu groups, it might be difficult or impractical to create and maintain some more complicated promotional discount types. When you design promotional discounts, make sure that you understand how the Toast discount configuration interface interacts with your menu configuration.

The following sections provide information about the types of promotional discounts that you can configure in the Toast platform, and which types of discounts might be impractical to configure and maintain. For general information about Toast platform discount types, see [Discount types](adminDiscountTypes.html).

#### Fully supported discount types

The following table shows discount types that are not complicated to configure. These discount types are fully supported and easy to maintain as your menu configuration changes.

| Discount use | Example discount | 
| --- | --- |
| Check-level [fixed amount and fixed percent discounts](adminDiscountTypes.html#adminFixedAmountAndPercentDiscounts) | 5% off an entire check before 7:00 AM. | 
| Item-level [fixed amount and fixed percent discounts](adminDiscountTypes.html#adminFixedAmountAndPercentDiscounts) | $3.00 off a large cheese pizza. | 
| [Buy One Get One (BOGO) discounts](adminDiscountTypes.html#adminBogoDiscounts) with *buy items* that are specific menu items and that apply a fixed or percent discount to the *get item*. | Buy a large cheese pizza (a single menu item) and get a free (100% discount), two-liter bottled drink. | 
| [BOGO discounts](adminDiscountTypes.html#adminBogoDiscounts) with buy items that are specific menu items and that apply a combo price for a single, specific get menu item. | Buy a large cheese pizza at the normal price and get a large order of garlic bread for $3.00. | 
| [Combo discounts](adminDiscountTypes.html#adminCombinationDiscounts)that apply a combo price for any number of specific menu items. | Buy two large cheese pizzas, a large order of garlic bread, and a large garden salad for $20.00. | 
| [Combo discounts](adminDiscountTypes.html#adminCombinationDiscounts)that apply a combo price for any number of specific menu items and menu groups in which *all menu items have the same price and do not use size pricing*. | Buy a small cheese pizza, any bag of chips (a menu group with consistent price and without size pricing), and any 20oz bottled drink (a menu group with consistent price and without size pricing) for $7.00. | 

#### Discount types that are supported with additional configuration

The following table shows discount types that you can configure, but that might require complicated setup in the discount configuration interface. These discounts might be more difficult to maintain as your menu configuration changes.



> **Note**
> 
> If you require Toast support to configure and maintain discounts for your restaurant, make sure to confirm that a discount does not exceed supported complexity before publishing a promotion that requires that discount.
> For information about configuring more complicated discounts, see [Handling menu groups with varying prices](adminDiscountsMenuGroupsVaryingPrices.html).


| Discount use | Example discount | 
| --- | --- |
| [BOGO discounts](adminDiscountTypes.html#adminBogoDiscounts) with a buy item that is a menu group, where the menu group uses size pricing or includes items with different prices | Buy any large or extra-large pizza (a menu group that uses size pricing) at the normal price and get a large order of garlic bread for $3.00. | 
| [BOGO discounts](adminDiscountTypes.html#adminBogoDiscounts) with a get item that is a menu group, where the menu group uses size pricing or includes items with different prices and that applies a combo discount | Buy a large cheese pizza at the normal price and get a small appetizer (another menu group that uses size pricing) for $5.00. | 
| [Combo discounts](adminDiscountTypes.html#adminCombinationDiscounts)that apply a combo price for menu groups that use size pricing or that include items with different prices | Buy any large or extra-large pizza (a menu group that uses size pricing) and a small appetizer (another menu group that uses size pricing) for $15.00.  | 

