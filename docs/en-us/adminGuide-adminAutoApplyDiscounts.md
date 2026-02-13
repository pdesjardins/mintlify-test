---
title: "Automatically applying discounts"
id: adminAutoApplyDiscounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsApplyingOmitChunkFromSearchIndex.md
parentSectionTitle: "Managing how discounts are applied"
previousSectionFile: adminGuide-adminDiscountReasons.md
previousSectionTitle: "Requiring a discount reason for a discount"
nextSectionFile: adminGuide-adminDiscountsEffectsOmitChunkFromSearchIndex.md
nextSectionTitle: "Effects of applied discounts"
excerpt: "You can create discounts that automatically apply to a check when a restaurant employee saves items (with the Send, Stay, Hold, or Pay buttons) or prints a receipt."
keywords: ["automatically", "applying", "discounts"]
procedures: 0
codeExamples: 0
---

You can create discounts that automatically apply to a check when
      a restaurant employee saves items (with the Send,
      Stay, Hold, or
      Pay buttons) or prints a receipt.

An auto-apply discount is applied if the items on the check match
      the selection criteria of the discount, without any action from a
      restaurant employee.

Discounts can only be applied automatically to checks that are
      created or updated on the Toast POS app.

## Eligibility rules for auto-apply discounts

You can configure these discount types to be auto-apply
        discounts:

- BOGO discounts


- Combo discounts


- Bulk discounts. These are fixed currency check-level
              discounts and fixed percent check-level discounts that are
              configured with at least one required item, and are configured
              as [bulk discounts](adminGuide-adminBulkDiscounts).


- Fixed currency and fixed percent Item-level discounts.
              Open item-level open discounts cannot be auto-apply
              discounts.



You cannot add the auto-apply feature to any discount that has
        any of the following configurations, which require server or manager
        intervention to apply the discount:

- Manager permissions level. Auto-apply
            discounts must have an Any User permissions
            level.


- Assigned discount reasons


- Promo codes



## Configuring a discount to be auto-applied

For eligible discounts, the Advanced
        settings section of the discount configuration page
        includes an Auto apply discount setting that
        allows you to specify whether to automatically apply the
        discount.

![The Auto apply discount setting in the Advanced Settings section of the discount configuration page.](https://doc.toasttab.com/doc/media/discount-auto-apply.png)

## How discounts are auto-applied to checks

The Toast platform applies auto-apply discounts as
        follows:



****Multiple auto-apply discounts on a
            check****
: Multiple discounts can be auto-applied to the same
              check.

For example, both a check-level bulk discount and an
              item-level discount can be auto-applied to a check.



****Applying the same auto-apply discount
            multiple times****
: The same auto-apply discount can apply multiple times to
              the same check, as long as the check has eligible items that
              have not been discounted.

For example, an auto-apply BOGO discount with a buy item
              of one cheese pizza and a get item of one small drink is
              auto-applied twice if the check has two cheese pizzas and two
              small drinks.

You cannot limit the number of times the discount is
              auto-applied to a check.



****Effect of splitting a
            check****
: Splitting a check re-validates an order, which removes all
              discounts on all checks, and then auto-applies all discounts to
              all checks in the order.



****Effect of sending a
            check****
: When a restaurant employee sends a check (by pressing
              Pay, Send, or
              Stay), all auto-applied discounts are
              removed from the check and then re-applied.

This refresh ensures that the discounts are applied to the
              correct items on the check, including items added after the
              discount was first auto-applied.

Manually-applied discounts are never removed.





## Determining the sequencing of auto-applied discounts

You can control the sequence in which to auto-apply
        discounts.

The discounts are auto-applied to a check based on the display
        sequence on the Discounts page.

On the Discounts page, the
        Order button allows you to define the display
        sequence of your discounts on the page:

![Order button on the Discounts page.](https://doc.toasttab.com/doc/media/discount-auto-apply-order.png)

**Procedure 9.13. To configure the application sequence for auto-applied
          discounts**

1. Click the Order button.

An Order column is added to the front
            of the list. If you previously configured the sequence, then the
            current sequence values are displayed. Discounts that do not have
            a configured sequence number are at the bottom of the list, and
            have an empty value for Order.

![Order column on the Discounts page.](https://doc.toasttab.com/doc/media/discount-list-order-column.png)


2. In the Order column, update the
            sequence numbers to reflect the sequence in which to apply
            auto-applied discounts.

As you edit the sequence numbers, the discount rows are
            moved to reflect the new sequence.


3. When you are finished, to hide the
            Order column, click the
            Order button.



## Example of an auto-applied discount on the Toast POS
        app

As an example of how a discount is automatically applied to a
        check, assume you have a BOGO auto-apply discount named
        *BOGO*. The discount has a buy item of one avocado
        toast and a get item of one soda at a 25% discount.

When those two items are on the check, and you tap the
        Stay button, the BOGO discount is automatically
        applied to the Soda item, as shown in this example:

![Toast POS screen showing a BOGO discount that is auto-applied to an order of avocado toast and a soda.](https://doc.toasttab.com/doc/media/discount-auto-apply-example.png)

