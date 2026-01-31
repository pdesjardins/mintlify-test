---
title: "Chapter 9. Discounts"
id: adminDiscountsIntroOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-adminMenusForDigitalMenuBoardsOmitChunkFromSearchIndex.md
previousSectionTitle: "Delphi digital menu boards"
nextSectionFile: adminGuide-adminDiscountTypes.md
nextSectionTitle: "Discount types"
procedures: 0
codeExamples: 0
---

# Chapter 9. Discounts

## Discounts overview

You use discounts to reduce the prices that your guests pay. For example, you might offer promotional discounts for specific menu items or for an entire check. Or you might offer combinations of items for a lower price.

The Toast platform supports different [types of discounts](adminDiscountTypes.html).

The configuration for a discount involves the following areas:



****Eligibility****
: A discount can only be applied if the discount eligibility requirements are met.

Discounts are often configured with [required items](adminDiscountTriggerComponentsOmitChunkFromSearchIndex.html#adminDiscountRequiredItemsAbout). The discount can only be applied when the guest purchases a specific item or combination of items.

You can also configure a discount with an [availability range of dates, days, and times](adminDiscountsOverallAvailabilityOmitChunkFromSearchIndex.html#adminDiscountAvailability). Even if a check includes the required items, if the current date is not within the availability range, the discount cannot be applied.

The discount might also require a [minimum or a maximum check total](adminDiscountsMinMax.html). If the pre-tax check total is too small or too large, then the discount cannot be applied.

You can also specify which [dining options](adminDiningOptions.html) are eligible for the discount. For example, you might want to offer a discount only for dine-in customers, or only for takeout orders. The discount will only be available when the selected dining option is used for the order.



****Discount status****
: A discount can be either [active or inactive](adminDiscountsActiveInactive.html). Inactive discounts cannot be applied to a check. For example, you might make a discount inactive while you are configuring it, then make it active when it is complete. As another example, you might make a discount active for special occasions, then make it inactive again.

You can [archive discounts](adminDiscountsArchive.html) that you no longer want to use at all. Archived discounts are not displayed on the Discounts page in Toast Web, and cannot be applied to checks or items.



****How a discount is selected and applied****
: Some discounts can be [applied automatically](adminAutoApplyDiscounts.html) to eligible checks that are created or updated on the Toast POS app.

Otherwise, a restaurant employee selects the applicable discount from the Toast POS app. The discount configuration includes [how to display it on the Toast POS device](adminDiscountsApplyingOmitChunkFromSearchIndex.html#adminDiscountsPosDisplay).

For discounts that [require manager permissions](adminDiscountsRequireManager.html), restaurant employees that do not have manager permissions must ask a manager to enter a passcode before the discount can be applied.

A discount might also require that the restaurant employee enter a valid [promo code](adminDiscountPromoCodes.html).

Restaurant employees might also have to select a [discount reason](adminDiscountReasons.html), to provide additional context for why the discount was applied.

Discounts can also be applied to orders that are created using the orders API. For more information, see [Applying discounts to a new order](apiDiscountingOrders.html#apiApplyingDiscount).



****Effect of the applied discount****
: When a discount is applied to a check, then the discount configuration determines the [effect on the check prices](adminDiscountsEffectsOmitChunkFromSearchIndex.html#adminDiscountPricing).

Discounts are configured with a currency amount or percent amount to discount, or a discounted price to charge for a combination of items.

[Bulk discounts](adminBulkDiscounts.html) can be automatically applied multiple times within the same check.

The effect of the discount is also affected by [whether a discount can be combined with other discounts](adminDiscountExclusivity.html).





