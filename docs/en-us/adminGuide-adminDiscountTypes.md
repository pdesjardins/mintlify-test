---
title: "Discount types"
id: adminDiscountTypes
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsIntroOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 9. Discounts"
previousSectionFile: adminGuide-platformDiscountsOverview.md
previousSectionTitle: "Discounts overview"
nextSectionFile: adminGuide-adminConfiguringDiscountsOmitChunkFromSearchIndex.md
nextSectionTitle: "Creating and updating discounts"
excerpt: "When you add a discount, you select the discount type:"
keywords: ["discount", "types", "BOGO discounts", "Combo discounts"]
procedures: 0
codeExamples: 0
---

When you add a discount, you select the discount type:

![Discount type field with the drop-down list of available types.](https://doc.toasttab.com/doc/media/discount-types.png)

The Toast platform supports the following types of discounts.



****Fixed and open currency amount and percent discounts****
: You can configure discounts that reduce the price of a check or an item by either a specific currency amount or by a specific percent. The currency amount or percent value is either configured in the discount, or set by the restaurant employee when they apply the discount.

- A fixed amount discount (**Fixed $ Off**) reduces the price of a check or item by a preconfigured currency amount.


- A fixed percent discount (**Fixed % Off**) reduces the price of a check or item by a preconfigured percent.


- An open amount discount (**Open $ Off**) reduces the price of a check or item by a currency amount that a restaurant employee chooses.


- An open percent discount (**Open % Off**) reduces the price of a check or item by a percent that a restaurant employee chooses.



For information about configuring fixed and open discounts, see [Configuring fixed or open amount or percent discounts](adminGuide-adminDiscountsConfigFixedOpenDiscounts).



****BOGO discounts****
: A BOGO (Buy One Get One) discount applies to certain menu items in a check when other menu items are also selected in the same check.

For example, you might configure a discount that reduces the price of a bottled drink if a guest also purchases two large pizzas. If a guest buys two large pizzas, the guest gets a bottled drink for 50% less than the normal price.

A BOGO discount includes one or a combination of required items (also referred to as *buy* items) and discounted items (also referred to as *get*items).

![Diagram that shows buy items and get items for a BOGO discount.](https://doc.toasttab.com/doc/media/bogo-discount-concept-diagram.png)

For more information on configuring BOGO discounts, see [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).



****Combo discounts****
: You can configure combo discounts that apply to one or a combination of required items in a check. A combo discount reduces the price of all the required items to a set currency amount.

For example, you might configure a discount that applies to the combination of a lunch salad and a fountain drink. That combo discount might reduce the price of both items to a total of $7.00.

For more information on configuring combo discounts, see [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).





