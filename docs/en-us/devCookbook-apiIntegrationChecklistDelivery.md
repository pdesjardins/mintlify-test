---
title: "Building a delivery dispatch integration"
id: apiIntegrationChecklistDelivery
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookOrderingOmitChunkFromSearchIndex.md
parentSectionTitle: "Ordering"
previousSectionFile: devCookbook-apiBuildingDigitalSignage.md
previousSectionTitle: "Building a digital menu signage integration"
nextSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
nextSectionTitle: "Reports"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/labor/overview/, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events]
excerpt: "Follow the steps below to build a delivery dispatch integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a delivery dispatch integration with the Toast platform.

This integration allows you to provide dispatch information to restaurants and guests for delivery orders throughout the delivery process. If you support [first-party delivery](adminGuide-adminDeliveryOverview), this integration also allows you to update the employee associated with delivery orders.

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `config:read`


- `delivery_info.address:read`


- `guest.pi:read`


- `labor:read`


- `labor.employees:read`


- `orders:read`


- `orders.delivery_info:write`


- `restaurants:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDevGuide-apiDeveloperPortal#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](apiDevGuide-integrationDevProcess)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Toast Web requirements

Within Toast Web, restaurants must enable first-party delivery in their delivery settings when using a delivery integration. Restaurants cannot use both Toast Delivery Services and a delivery integration simultaneously. For guidance on how restaurants can enable first-party delivery, see [Configuring delivery options](adminGuide-adminConfigureDelivery#adminConfigureDeliveryOptions).

### Learn order structure concepts

To successfully retrieve information relevant to delivery orders, familiarize yourself with the structure of an order by reading the [Orders API overview](apiDevGuide-portalOrdersApiOverview) and [Order object summary](apiDevGuide-apiOrdersOrderObjectSummary). For more information about the orders API, see the [reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

### Retrieve configuration information

Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve the dining options configuration you need to dispatch drivers and deliver orders.

Use the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/) to retrieve general information about the configuration of a restaurant. If you support [first-party delivery](adminGuide-adminDeliveryOverview), the delivery area configured by restaurants in Toast Web is available in the restaurants API. The delivery area is only configurable when restaurants have first-party delivery enabled. To learn more about how restaurants configure their delivery area, see [Configuring your delivery area](adminGuide-adminConfigureDeliveryArea).

To ensure you have the latest restaurant configuration, poll the configuration API and restaurants API once per restaurant location per day, and update configuration information in your system based on anything that was added, updated, or deleted.

### Determine what dining options you support

All Toast orders contain a dining option with a defined dining behavior. Your integration can only update orders whose `diningOption` has the `behavior` of `DELIVERY`. You can understand dining option dining behavior by calling the `/diningOptions` endpoint of the configuration API. Restaurants may have multiple dining options configured with the delivery behavior. Your integration should allow restaurants to choose which dining options they want your integration to deliver in your system's user interface.

For more information about the `/diningOptions`endpoint of the configuration API, see the [reference documentation](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/).

### Decide if you support delivery using a restaurant's own drivers

If your integration supports restaurants fulfilling delivery orders using the restaurant's own drivers (first-party delivery), versus using drivers provided by your integration, you need to pass the Toast platform GUID of the employee assigned as the delivery driver in your `PATCH` request to the `/deliveryInfo` endpoint of the orders API.

To get information about the employees of a restaurant, send a `GET` request to the `/employees` endpoint of the labor API.

For more information about the labor API, see the [reference documentation](https://doc.toasttab.com/openapi/labor/overview/).

### Decide if you will deliver catering orders

Information is limited in the orders API response for catering orders. Your integration will only have access to the data that is captured in the following sections of the Toast Catering and Events page under Create order in Toast Web.

In the Customer section, the guest's first and last name, email address, and phone number are exposed in the `customer` object of the orders API.

![Image](https://doc.toasttab.com/doc/media/cookbook-delivery-catering-customer.png)

In the Order details section, the Deliver to address and Delivery notes are exposed in the `deliveryInfo` object of the orders API.

![Image](https://doc.toasttab.com/doc/media/cookbook-delivery-catering-order.png)

Toast does not expose additional catering information in the orders API besides what is available in the two sections outlined above. When integrating with restaurants using the Toast Catering and Events module, it is important they understand what your integration can access. This way, they can build their catering orders so that your integration has the information needed to fulfill the delivery.

To understand if an order is a catering order, reference the `source` value in the orders API response. Catering orders have have a `source` value of any of the following:

- `Invoice`


- `Catering`


- `Catering Online Ordering`



For more information about Toast Catering and Events, see [Get Started with Toast Catering and Events](https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events).

## Handling orders

### Retrieve orders in real-time

Your integration will need real-time order data. Poll the `/ordersBulk` endpoint of the orders API using the `startDate` and `endDate` query parameters to understand new and modified orders placed within the specified timeframe. Your polling frequency should align with your polling window. For example, if you poll for a window of five minutes, you should poll roughly once every five minutes.

Ensure your integration adheres to the endpoint specific rate-limit for the `/ordersBulk` endpoint when retrieving order data. For more information about Toast rate limits, see [Rate limiting](apiDevGuide-apiRateLimiting).

### Filter orders based on dining option

Your integration can understand which orders to fulfill based on dining options. Allow restaurants to specify which dining options they would like fulfilled for delivery dispatch. A restaurant may not want your integration to deliver all delivery orders it receives. For example, a restaurant may use a third-party ordering source that submits and dispatches delivery for some dining options but not others.

### Understand relevant order data from the orders API

#### Understand when orders will be ready for delivery

The Toast platform supports as soon as possible (ASAP) orders and scheduled orders. Both of these order types return an `estimatedFulfillmentDate` in the `order` object of the orders API. The `estimatedFulfillmentDate` indicates the date and time the order is expected to be delivered. Scheduled orders also include a `promisedDate`, which is the time the order has been scheduled for delivery. Your integration should use the `promisedDate` to know when to dispatch drivers. Including delivery details for scheduled orders in your integration allows restaurants to understand future delivery schedules.

#### Understand customer delivery information

Examine the `deliveryInfo` object from the orders API to understand where orders will be delivered. The `deliveryInfo` object contains the delivery address and delivery notes.

The `customer` object in the orders API will provide the name, email address, and phone number of the guest who placed the order.

#### Understand payment information

Understand if an order has been paid and determine if your integration will collect cash on delivery. To understand if an order has been paid, examine the `paymentStatus` from the `order.check` object of the orders API for values `PAID` or `CLOSED`. The payment status of the check may be updated after the initial order creation. As you poll the `/ordersBulk` endpoint of the orders API, examine modified orders for updates to the `paymentStatus`.

If your integration supports the collection of cash payment on delivery, these orders will have a `paymentStatus` of `OPEN`, indicating there is a balance due.



> **Note**
> 
> Orders may contain multiple check objects.


## Update an order with delivery information

### Place a test update

Learn how the Toast platform structures delivery information `PATCH` requests. Follow the [Updating delivery information for an order](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder) guide to use the orders API to update the delivery information for orders using the `/deliveryInfo` endpoint of the orders API.

Place a test update by following the steps in the [Example API requests](apiDevGuide-apiExampleRequests) guide.

