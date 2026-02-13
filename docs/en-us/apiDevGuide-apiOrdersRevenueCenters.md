---
title: "Providing revenue center information for an order"
id: apiOrdersRevenueCenters
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiDiscountingOrders.md
previousSectionTitle: "Working with order discounts"
nextSectionFile: apiDevGuide-orders_api_future_orders.md
nextSectionTitle: "Scheduling future orders"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/]
excerpt: "You can specify the revenue center associated with the order."
keywords: ["Order", "revenueCenter", "GET", "/revenueCenters", "/serviceAreas"]
procedures: 0
codeExamples: 1
---

You can specify the revenue center associated with the order.

For example, restaurants might use revenue centers to report on order volume in specific locations of a restaurant, such as the patio, bar, or dining room. They might also use revenue centers for delivery services, to track the volume of orders from each service.

To specify the revenue center, in the `Order` object, provide a `revenueCenter` object that specifies the Toast platform GUID of the revenue center. For example:

```
"revenueCenter": {
    "guid": "908f0483-ac03-4c9a-a5a4-43c37786e237",
    "entityType": "RevenueCenter"
  },
```

To retrieve the GUIDs of the available revenue centers for a restaurant, send a `GET` request to the `/revenueCenters` endpoint of the configuration API.

You can also retrieve the revenue center that is associated with a table or service area.

- When you send a `GET` request to the `/tables` endpoint of the configuration API, the response includes the revenue center for each table.


- When you send a `GET` request to the `/serviceAreas` endpoint of the configuration API, the response includes the revenue center for each service area.



For more information, see the [reference documentation for the configuration API](https://doc.toasttab.com/openapi/configuration/overview/).

