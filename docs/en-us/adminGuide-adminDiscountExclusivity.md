---
title: "Exclusive and nonexclusive discounts"
id: adminDiscountExclusivity
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsEffectsOmitChunkFromSearchIndex.md
parentSectionTitle: "Effects of applied discounts"
previousSectionFile: adminGuide-adminDiscountPricing.md
previousSectionTitle: "Effect of discounts on prices"
nextSectionFile: adminGuide-adminBulkDiscounts.md
nextSectionTitle: "Bulk discounts"
excerpt: "Whether a discount is exclusive or nonexclusive determines whether the discount can be combined with other discounts."
keywords: ["exclusive", "nonexclusive", "discounts"]
procedures: 0
codeExamples: 0
---

Whether a discount is exclusive or nonexclusive determines whether the discount can be combined with other discounts.

Nonexclusive discounts can be combined with any other type of discount, regardless of whether the other discount is exclusive or nonexclusive.

Exclusive discounts cannot be combined with other exclusive discounts. They can, however, be combined with nonexclusive discounts.

## Determining whether a discount is exclusive or nonexclusive

For the following types of discounts, you can configure whether the discount can be combined with other discounts.

- Check-level fixed or open discounts


- BOGO discounts



To configure whether the discount is exclusive or nonexclusive, you use the Allow with other discounts setting, which is in the Advanced Settings section of the discount configuration page.

![Allow with other discount setting for a discount.](https://doc.toasttab.com/doc/media/discount-allow-option.png)

- If the Allow with other discountssetting is selected, then the discount is nonexclusive.


- If the Allow with other discountssetting is not checked, then the discount is exclusive.



Item-level discounts and combo discounts are always exclusive. The Allow with other discounts setting is always not enabled and empty.

## How exclusivity affects discount applicability

When you apply a discount to a check, it can affect the applicability status of the menu items on the check:

- When you apply an exclusive discount to a check, the items that the discount uses are marked as used up. Those items cannot be discounted further. The marking is internal and is not visible on the Toast POS app.

For example, if you apply an exclusive check-level discount to a check, all items in that check are marked as used up. Similarly, if you apply an exclusive BOGO discount to a check, the buy and get items are marked as used up.


- When you apply a nonexclusive discount to a check, none of the items are marked as used up. The items can be eligible for other discounts.



### Effect of discount sequence on discount eligibility

If two check-level discounts are on a check, one of those discounts must be a nonexclusive discount. Whether the discounts can be combined depends on which discount is applied first.

If the first check-level discount is nonexclusive, then none of the items are marked as used up. The second, exclusive check-level discount can then use those items and mark them as used up.

If the first check-level discount is exclusive, then all of the items in the check are marked as used up. When you apply the second, nonexclusive check-level discount to the check, the effect is as follows:

- If the second, nonexclusive check-level discount does not have a required item, the discount applies, because it can be combined with other discounts and does not need an item in order to be applied. In this case, the order in which you apply the discounts does not matter.


- If the second, nonexclusive check-level discount does have a required item, the discount does not apply. The first, exclusive discount item marked every item as used up, and did not leave any items for the second discount.

In other words, although a nonexclusive discount can normally be combined with an exclusive discount, in this case it cannot because of the requirement for an item that is not used up. In this case, the order in which you apply the discounts does matter.



### Effect on applicable BOGO discounts

BOGO discounts are also affected if their buy and get items are used up:

- If you first apply an exclusive check-level discount to a check, you cannot subsequently apply a nonexclusive BOGO discount. The buy and get items are marked as used up by the exclusive discount.


- If two nonexclusive BOGO discounts use the same buy item (for example, a large pizza) but different get items, you can apply both nonexclusive BOGO discounts only if the order has two or more large pizzas on it.

The first BOGO discount uses one of the large pizza items as its buy item. The second BOGO discount uses the second large pizza item as its buy item.

However, if the order has only one large pizza, you cannot apply both nonexclusive BOGO discounts. The first BOGO discount uses up the buy item that is needed by the second nonexclusive BOGO discount.



## Combinations of exclusive and non-exclusive discounts

The following table summarizes how different combinations of exclusive and nonexclusive discounts interact.

For information on configuring required items for discounts, see [Choosing the required items for a discount](docs/en-us/adminGuide-adminDiscountRequiredItemsAbout).

| Discount type | Required items | Exclusive or Nonexclusive | Combines with other discounts? | 
| --- | --- | --- | --- |
| Check-level discount | None | Nonexclusive | - Combines with nonexclusive discounts (check-level or BOGO). Order of application does not matter.
- Combines with exclusive discounts (check-level, item-level, BOGO, or combo). Order of application does not matter.

 | 
| Check-level discount | One required item | Nonexclusive | - Combines with nonexclusive discounts (check-level or BOGO) if applied first.
- If another nonexclusive discount (check-level or BOGO) is applied first, the second nonexclusive discount combines with the first one only if the first discount does not use up the required item required by the second nonexclusive discount.
- Combines with an exclusive discount (of any type) if the nonexclusive discount is applied first and does not use up items required by the exclusive discount.
- If an exclusive discount is applied first, the nonexclusive discount combines with the exclusive discount only if the exclusive discount does not use up the required item needed by the nonexclusive discount.

 | 
| Check-level discount | Either none or one required item | Exclusive | - Combines with a nonexclusive check-level discount that does not use a required item. Order of application does not matter.
- Combines with nonexclusive discounts (check-level or BOGO) that have required items if the nonexclusive discount is applied first.
- If applied first, combines with a nonexclusive check-level discount that has a required item as long as the nonexclusive discount does not have a required item that was used by the exclusive BOGO discount.
- Cannot combine with other exclusive discounts (of any type). For example, an exclusive check-level discount cannot combine with an item-level discount.

 | 
| BOGO discount | Buy and get items | Nonexclusive | - Combines with nonexclusive check-level discounts if the BOGO discount is applied first and if the check-level discount does not use up an item required by the BOGO discount.
- Combines with other nonexclusive BOGO discounts only if the second BOGO discount's buy item is not used up.
- Cannot combine with exclusive check-level discounts.
- Combines with an item-level discount as long as the item-level discount does not use up the BOGO discount's buy and get items.

 | 
| BOGO discount | Buy and get items | Exclusive | - Combines with nonexclusive check-level discounts that have no required items. Order of application does not matter.
- Combines with nonexclusive check-level discounts that have required items if the nonexclusive discount is applied first.
- If applied first, combines with a nonexclusive check-level discount that has a required item as long as the nonexclusive discount does not have a required item that was used by the exclusive BOGO discount. For example, an exclusive BOGO discount can combine with a nonexclusive check-level discount as long as the buy and get items are not required by the nonexclusive check-level discount.
- Combines with an item-level discount as long as the item-level discount does not use up the BOGO discount's buy and get items.
- Cannot combine with an exclusive check-level discount.

 | 
| Item-level discount | One required item | Exclusive - All item-level discounts are exclusive | - Can apply a maximum of one item-level discount per item. If an item-level discount is already applied to an item, the item-level discount is removed when another item-level discount is subsequently applied to the same item.
- Combines with nonexclusive discounts (check-level or BOGO) as long as the nonexclusive discount does not have required items that have been used by the item-level discount.
- Cannot combine with exclusive check-level discounts. If an item-level discount is already applied to an item, the item-level discount is removed when an exclusive check-level discount is subsequently applied to the check.
- Combines with BOGO discounts as long as the item-level discount does not use up the BOGO discount's buy and get items.

 | 
| Combo discount | Combo items | Exclusive - All combo discounts are exclusive | - Combines with a nonexclusive check-level discount that has no required item. Order of application does not matter.
- Combines with nonexclusive discounts (check-level or BOGO) that have required items if the nonexclusive discount is applied first.
- If applied first, combines with nonexclusive check-level discounts that have required items as long as the nonexclusive discount does not have required items that have been used by the combo discount.
- If applied first, combines with a nonexclusive BOGO discount as long as the BOGO discount does not have buy and get items items that have been used by the combo discount.
- Combines with an item-level discount if that item is not required by the combo discount.
- Cannot combine with exclusive check-level or BOGO discounts.

 | 

