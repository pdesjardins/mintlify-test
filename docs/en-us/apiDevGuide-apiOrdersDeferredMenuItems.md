---
title: "Deferring menu items"
id: apiOrdersDeferredMenuItems
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiMarketplaceFacilitatorOrders.md
previousSectionTitle: "Marketplace facilitator orders"
nextSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 3. Payments"
excerpt: "Deferred menu items are items whose revenue you want to exclude from an order total and overall reporting. For example, you may want to exclude gift card sales from a restaurant's revenue since the..."
procedures: 1
codeExamples: 1
---

### Deferring menu items

Deferred menu items are items whose revenue you want to exclude from an order total and overall reporting. For example, you may want to exclude gift card sales from a restaurant's revenue since the funds received from gift cards are paid upfront. Typically, gift card sales do not qualify for revenue recognition as no goods or services have been exchanged.

When using the orders API you must indicate each menu item or modifier that you want to defer. The procedure below describes how to defer an item using the orders API.

**Procedure 2.9. To defer an item**

- Set the `deferred` value to `true` in each menu item `selection` object you want to defer.

To defer a modifier, set the `deferred` value to `true` in each `modifier` object you want to defer.



The example below shows a deferred item with a deferred modifier. 

```

              "selections": [
                    {
                        "guid": "a2235d4c-96dc-43ae-b0b4-693649778n44",
                        "entityType": "MenuItemSelection",
                        "externalId": null,
                       "deferred": true,
                        "preDiscountPrice": 22.0,
                        "voidReason": null,
                        "optionGroup": null,
                        "displayName": "Shrimp risotto",
                        "appliedDiscounts": [],
                        "modifiers": [
                            {
                                "guid": "1236c34c-793f-4f67-9b02-b1b2b3b4b5b6",
                                "entityType": "MenuItemSelection",
                                "externalId": null,
                                "deferred": true,
                                "preDiscountPrice": 2.0,
                                "voidReason": null,
                                "optionGroup": {
                                    "guid": "32acba90-2f06-4186-9d14-fecef3cb6599",
                                    "entityType": "MenuOptionGroup",
                                    "externalId": null,
                                    "multiLocationId": "574000462271555"
                                },
  
```

