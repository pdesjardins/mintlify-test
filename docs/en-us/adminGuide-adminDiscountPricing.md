---
title: "Effect of discounts on prices"
id: adminDiscountPricing
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsEffectsOmitChunkFromSearchIndex.md
parentSectionTitle: "Effects of applied discounts"
previousSectionFile: adminGuide-adminDiscountsEffectsOmitChunkFromSearchIndex.md
previousSectionTitle: "Effects of applied discounts"
nextSectionFile: adminGuide-adminDiscountExclusivity.md
nextSectionTitle: "Exclusive and nonexclusive discounts"
excerpt: "Toast discounts affect prices in the following ways."
keywords: [effect,discounts,prices]
procedures: 0
codeExamples: 0
---

### Effect of discounts on prices

Toast discounts affect prices in the following ways.

#### Check and item discounts

You can configure and apply discounts that affect the price of an entire restaurant check or that affect the price of an individual menu item in a check.

- Check discounts apply to all of the items in a restaurant check. For example, a 10% discount for senior citizens might apply to all items that a senior citizen orders in a check.


- Item discounts apply to specific items in a check. For example, a 10% discount on tomato soup only applies to a bowl of tomato soup that a customer orders in a check. It does not apply to any of the other items in that check. As another example, a 100% discount might apply to any menu item if a restaurant wanted to give, or *comp*, a specific item for a dissatisfied customer.



Some Toast discount types can apply to either checks or items. You can configure a currency amount or a percent discount to apply to either a check or an item.

Toast discount types for combinations of items, such as Buy One Get One (BOGO) discounts, do not apply directly to either items or checks.

For more information about discount types, see [Discount types](adminDiscountTypes.html).

#### Combo price discounts

A combo (combination) discount sets the price of multiple menu items in a check to a fixed currency amount. The fixed currency amount is not based on or affected by the normal prices of the selected items.

For example, you might configure a discount that sets the price of two large cheese pizzas and a small order of garlic bread to $15.00. In this example, the normal prices of the menu items do not affect the combo discount price. The combo price is exactly $15.00.

##### Upcharging discounted items in a combo discount

You can configure combo discounts to reduce the price of menu items that use size pricing and still increase the price for larger sizes or additional modifiers.

For example, you configure a discount that applies to a large cheese pizza and a bottled drink. You might configure that discount to apply to all larger cheese pizza sizes and add the increased price of the larger pizza size to the combo price. If a customer adds a modifier such as jalapenos to the cheese pizza, the Toast platform adds the price of the modifier on top of the combo price.

In the following example, the combo discount applies the combo price if a check includes a large cheese pizza. It also applies the combo discount if a customer orders an extra large or the largest, rustic, cheese pizza. If a customer orders either of those larger sizes, the Toast platform adds the difference in their prices to the large size to the combo discount price.

![Diagram showing how a combo discount adjusts the price based on item size.](https://doc.toasttab.com/doc/media/combo-discount-size-menu.png)

##### Combo discounts with both taxed and tax-exempt items

You can have a combo discount in which one item is taxed and another is tax-exempt. In this case, the items are weighed within the combo, and the tax is the ratio of the taxed item within the combo discount.

For example, assume this combo discount:

| Discount component | Amount | 
| --- | --- |
| NonTaxed item | $5.00 | 
| Taxed item | $10.00 and taxed at 10% | 
| Combo price for both items | $12.00 | 

Based on the weighing, the new price of the Taxed item is calculated as $8.00 and the NonTaxed item as $4.00, which adds up to the $12.00 price of the discount.

The tax is assigned based on the price after the weighing. This means that the tax on the Taxed item is $0.80 ($8.00 * 10%) The tax on the NonTaxed item is $0.00. The total tax is $0.80.

The total of the discounted check is $12.80, which is the sum of the combo discount price and the tax.

#### Combining multiple discounts

You can apply discounts to items in a check. You can apply more than one discount to a check. When you apply more than one discount to the items in a check and to the check itself, the Toast platform applies the discounts in the following order:

1. Item-level discounts


2. Check-level discounts that reduce the check price by a currency amount


3. Check-level discounts that reduce the check price by a percent value



You can only apply one discount to an item in a check.

You can only apply more than one discount to a check if the discount rules for each discount allow those discounts to be combined. For more information, see [Exclusive and nonexclusive discounts](adminDiscountExclusivity.html).

#### Consolidated items and item-level fixed currency discounts

For item-level fixed currency discounts, when you consolidate identical items into a single item, you can also determine how to apply the discounts to the consolidated item.

You can either apply the discount separately to each quantity in the consolidated item, or apply the discount once to the total quantity of the consolidated item.

##### Configuring item consolidation

You can use the Consolidate menu itemssetting to configure your restaurant to show selected identical items on the order screen as consolidated items or as separate items.

The Consolidate menu items setting is available in the Front of house \> Order screen setup \> UI options page in Toast Web.

The available options are:

- On: Groups identical items as one item with the indicated quantity. The *Qty*(quantity) column lists the number of items. For example, three Onion Rings menu items are consolidated on one line with a *Qty* of *3*. This is the default option.

![Toast POS screen showing consolidated items.](https://doc.toasttab.com/doc/media/discount-consolidated-items.png)


- Off: Each menu item is listed on a separate line. The *Qty* column for each item is set to *1*. For example, three Onion Rings menu items are listed separately, each with a *Qty* of *1*.

![Toast POS screen showing items that are not consolidated.](https://doc.toasttab.com/doc/media/discount-non-consolidated-items.png)



##### Configuring discount consolidation for consolidated items

If you [consolidate menu items](adminUiOptionsReference.html#configCombineItems), you can use the Consolidate discounts setting to set how to apply an item-level fixed currency discount to a consolidated item.

The Consolidate discounts setting is available in the Front of house \> Order screen setup \> UI options page.

![The Consolidate discounts setting in Toast Web.](https://doc.toasttab.com/doc/media/discount-consolidate-discounts.png)

The available values are:

- Yes: Indicates to apply item-level fixed currency discounts to each item.

For example, a consolidated item has a quantity of three items. A $1 item-level fixed currency discount is applied to each item. $3 is discounted from the check.


- No: This is the default. Item-level fixed currency discounts are applied to the total of all the items.

For example, a consolidated item has a quantity of three items. A $1 item-level fixed currency discount is applied to the quantity total. $1 is discounted from the check.



The Consolidate discounts setting has no effect on discounts other than item-level fixed currency discounts.

The following example shows how a discount would behave with the Consolidate discounts setting (On or Off).

In this example:

- The discount is a $2 fixed currency discount.


- The check includes two sodas, that cost $5 each.


- The pre-discount check total is $10.



The discount in the example is applied as follows, depending on the configuration setting:

| Configuration setting | Effect | 
| --- | --- |
| Consolidate discounts: Off | The fixed currency discount is applied to the total of all items:2 Sodas, $10 - $2 Discount = $8 | 
| Consolidate discounts: On | The fixed currency discount is applied to each quantity of one item:2 Sodas, $10 - $2 discount (x quantity of 2 items) = $6 | 

