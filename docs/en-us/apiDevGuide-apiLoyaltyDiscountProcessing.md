---
title: "Reward offers processing"
id: apiLoyaltyDiscountProcessing
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyKioskWorkflow.md
previousSectionTitle: "Kiosk workflow"
nextSectionFile: apiDevGuide-apiLoyaltyErrorHandling.md
nextSectionTitle: "Error handling"
excerpt: "Loyalty reward offer redemptions are handled entirely by your organization. Your loyalty program is responsible for accepting or rejecting the redemptions as requested by the Toast platform and the..."
keywords: ["reward", "offers", "processing", "Inquire"]
procedures: 0
codeExamples: 0
---

Loyalty reward offer redemptions are handled entirely by your organization. Your loyalty program is responsible for accepting or rejecting the redemptions as requested by the Toast platform and the POS will honor them as reported from your loyalty program integration. The Toast POS applies reward redemptions as discounts.

- When the Toast POS sends an inquire request to your loyalty program integration, it includes all of the discounts that are currently applied to a check. Your loyalty program integration can use these to determine whether those discounts affect the applicability of your loyalty reward discount.


- The Toast platform will honor the response from your loyalty program that indicates whether or not to apply a loyalty redemption. Any validation done by the Toast platform is minimal (such as ensuring a check or item price is not brought below zero).


- `Inquire` calls are made whenever the list of offers is loaded (if the contents of the check have changed since the last inquire call) to get the list of offers currently applicable to the check. The restaurant employee can subsequently select which offer to redeem by selecting from the list.


- `Inquire` is also called at the end of the POS workflow during payment. At this point, all redemptions attached to the check have a final opportunity to be verified. Your loyalty program integration can either *accept* or *reject* each redemption. Prior to the final inquire call, the POS will verify Toast domain configured discounts and Promotion service integration discounts (in that order).



#### Check-level reward offers

There is no additional validation done by the POS for check-level rewards. Check-level rewards are entirely validated by your loyalty program. If applied, the POS will recalculate the check total.

#### Item-level reward offers

Minimal validation occurs in the POS when an item-level reward offer is selected. The offer must include a selection GUID to which the reward can apply. If the reward is applied by the restaurant employee, the POS will attach the reward to the item selection with the matching GUID.

The array of rewards returned to the POS is in a `ResponseCheck` object. Each item-level offer contains a `selectionIdentifier` value. This is a Toast POS-defined GUID and is the way your loyalty program integration can specify which item an offer may apply to.

1. Your loyalty program integration must retrieve menu information from Toast. The recommended approach is to use the menus API to retrieve a list of all menu items. See [Menus API overview](apiGettingMenuInformationFromTheMenusAPI.html).


2. Specific top level items which offers apply to is optionally returned in the loyalty API response to an inquire request:

A `ResponseCheck` object contains an `offers` value which contains an array of `Offer` objects. If an offer is of `selectionType``ITEM` and a `selectionIdentifier` is specified, then that is the menu item for which the offer can be applied. All offers are expected to have the `applicable` boolean value set to `true` if the offer can be applied to the check submitted with the request, false otherwise

The `Check` contains a list of `Selection` objects representing items on the check. Each `Selection` has a reference to the corresponding menu item. Menu items have GUIDs assigned to it. These are the IDs used to match against item level offers specified in the `selectionIdentifier` returned from an inquiry request.



#### Discount limitations

You can only apply a single item-level discount to a menu item selection in a check. If a restaurant employee applies a discount configured in the Toast platform to a menu item selection, you cannot apply an additional item-level discount based on loyalty program rewards.

There is no limit to the number of check-levels that you can apply to an entire check. You can apply an item-level discount to an item and check-level discounts at the same time.

The Toast platform does not apply discounts directly to modifiers. You can apply item-level discounts to menu item selections that include modifiers. The discount applies to the total price of the item, which includes the modifier price.

The `MULTI_ITEM` discount type applies to multiple different items or to two instances of the same item in separate `Selection` objects within a `Check`. For the discount to work, each item must be in an individual `Selection` object with a `quantity` of 1. A single `Selection` object with a `quantity` of 2 or more of the same item will not qualify for a `MULTI_ITEM`discount.

For more information about Toast platform discount functionality, see [Discounts overview](platformDiscountsOverview.html).

