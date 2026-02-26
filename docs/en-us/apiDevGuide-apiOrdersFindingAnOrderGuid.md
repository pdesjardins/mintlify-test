---
title: "Finding an order or check GUID"
id: apiOrdersFindingAnOrderGuid
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiMarketplaceFacilitatorTaxInformation.md
previousSectionTitle: "Marketplace facilitator tax information"
nextSectionFile: apiDevGuide-apiDailyOrderForTrackingExcessFood.md
nextSectionTitle: "Daily order for tracking excess food"
excerpt: "The following sections detail multiple methods for locating either an order GUID or a check GUID."
procedures: 0
codeExamples: 0
---

The following sections detail multiple methods for locating either an order GUID or a check GUID.

## How to locate an order GUID

- If you have created an order using the orders API, the response from the `POST` request contains the order GUID. For more information about creating orders see [Creating orders](apiDevGuide-apiCreatingOrders).


- Send a `GET` request to the `/ordersBulk` endpoint and retrieve the details for orders updated during a specific time interval. The order details include the order GUID. See [Getting detailed information about multiple orders](apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders) for more information on using the `/ordersBulk` endpoint.


- Locate the order in Toast Web using the Orders report from Reports &gt; Sales &gt; Orders. Use the View filter, at the top of the report, to help locate your order. Once located, select the order, and the GUID is displayed as seen below.

![Shows the Order Details page with the order GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_order_guid.png)



## How to locate a check GUID

- If you know the order GUID, you can send a `GET`request to the `/orders` endpoint and retrieve the order details, which include the check GUID. See [Getting detailed information about one order](apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder).


- Locate the order in Toast Web using the Orders report from Reports &gt; Sales &gt; Orders. Use the date selector to locate your order. Once located, select the order, and find the check. The GUID is displayed as seen below.

![Shows the Order Details page with the check GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_check_guid.png)



