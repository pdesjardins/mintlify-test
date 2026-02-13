---
title: "Daily order for tracking excess food"
id: apiDailyOrderForTrackingExcessFood
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiOrdersFindingAnOrderGuid.md
previousSectionTitle: "Finding an order or check GUID"
nextSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating order information"
externalReferences: [https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/]
excerpt: "The..."
keywords: ["excessFood", "Waste", "preDiscountPrice"]
procedures: 0
codeExamples: 0
---

The orders API returns a daily *excess food order*for restaurants that use the Toast platform's waste tracking feature. An excess food order, also referred to as a waste order, is a special type of order created in the Toast platform to track excess food in a restaurant. Like guest orders, excess food orders may contain menu items, modifiers, or both.

Currently, the Toast platform creates one excess food order per day at each restaurant using the waste tracking feature. The Toast platform creates the daily excess food order the first time a restaurant employee uses the waste tracking feature to identify excess food. If restaurant employees identify additional excess food over the course of the business day, that excess food is added to the daily excess food order. If no excess food is identified on a given day, no excess food order is created for that day.

The orders API indicates that an order is an excess food order using the `excessFood` value on the [Order](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/)object. Excess food orders are structurally the same as standard guest orders. However, certain behavior is applied to these orders automatically by the waste tracking feature:

- The `excessFood` field is set to `true`.


- Exactly one check is created on each excess food order.


- Each selection on the check is discounted to $0 using an item-level 100% discount. This discount is created automatically by the Toast platform and has the name `Waste`.


- If the restaurant has configured waste reasons and the employee identifying the waste selects one of those reasons when tracking the item in the POS, that reason is applied to the discounted selection. Note that waste reasons are not returned in orders API responses.



Because all selections on the check are discounted, the `price` value on each selection and the `amount` value of the check is always $0. The `preDiscountPrice` value on each selection, however, reflects the retail value of each selection. If you use the `preDiscountPrice` field in order to report on gross sales, you might want to exclude excess food orders from this calculation.

