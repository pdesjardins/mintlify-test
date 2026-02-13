---
title: "Creating orders"
id: apiCreatingOrders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating order information"
nextSectionFile: apiDevGuide-apiVoidOrder.md
nextSectionTitle: "Void an order"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/orders/operation/pricesPost/]
excerpt: "To create an order in the Toast platform, you send a POST request that contains a JSON Order object to the /orders endpoint of the orders API."
keywords: ["Order", "POST"]
procedures: 0
codeExamples: 0
---

To create an order in the Toast platform, you send a `POST` request that contains a JSON `Order` object to the `/orders` endpoint of the orders API.

Before you `POST` the order, you must retrieve the check prices (calculated by the Toast platform) from the `/prices`endpoint. The `/prices` endpoint is the only reliable and supported way to determine the payment amount for a check.

If you `POST` an order with a payment amount that does not match the results from the `/prices` endpoint, then restaurant employees must handle the underpayment or overpayment during order fulfillment.

## Building shopping cart orders

A shopping cart order, also called a draft order, is an order that is created by adding items to an online ordering shopping cart before it is submitted to the orders API.

The orders API does not support shopping cart functionality. Your integration must implement a shopping cart feature to save added items before you create an order using the orders API. Items that guests add to a shopping cart are not saved in the Toast platform until you create the order.

## Order creation process for the orders API

To use the orders API to create and `POST` a new order:

1. Create a JSON `Order` object that includes the dining option, checks, and menu item selections for the order. You can also include a revenue center.

For information about the required details for different dining options, as well as example order objects for each type, see [Order details based on the order dining option](apiDevGuide-apiOrderTypeDetails).

For other limitations on menu selection items, scheduling, and how orders from the API are processed, see [Orders API limitations](apiDevGuide-portalOrdersApiOverview#ordersAPILimitations).

For information on providing revenue center information in an order, see [Providing revenue center information for an order](apiDevGuide-apiOrdersRevenueCenters).

To create a scheduled order to be fulfilled at later time, provide a `promisedDate` value. See [Scheduling future orders](apiDevGuide-orders_api_future_orders).

For detailed information about all of the values in an `Order` object, see the [reference documentation for the orders API](https://doc.toasttab.com/openapi/orders/overview/).


2. Retrieve the price information for the order.

To do this, send a `POST` request to the `/prices` endpoint of the orders API. In the message body of the `POST` request, include the JSON `Order`object. See [Get order prices](https://doc.toasttab.com/openapi/orders/operation/pricesPost/).

The `Order` object returned by the `/prices`endpoint includes the base price, tax amount, and total price of each check.

For more information, see [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).


3. Optionally, add payment information for the checks to the `Order` object.

To include payment information for a check, add a `payments` value to the `Check` object.

The payment type must be either `CREDIT` or `OTHER`.

For more information about `CREDIT` payments, see [Credit card payments](apiDevGuide-authorizingCcPayments).

For an `OTHER` type payment, include in the `Payment` object the GUID of a previously configured alternative payment type. Note that the orders API ignores the tax exempt setting for the payment type. The order is taxed regardless of whether the payment type is configured to be tax exempt.

Payment information is optional. If an order is not yet paid for, you can omit the `payments` value. When the order is paid for, you can update the order to add the payment information. See [Adding payments to an existing check](apiDevGuide-apiAddingPaymentsToACheck).


4. Send a `POST` request to the `/orders` endpoint of the orders API.

The body of the `POST` request contains the JSON `Order` object for the order.



> **Note**
> 
> The `externalId` values for the `Order`, `Check`, and `Selection` objects must be unique. If you submit an order containing an `externalId` that already exists for another `Order`, `Check`, or `Selection`, the request will fail.



5. The response from the `/orders` endpoint indicates whether the order was created successfully.

The orders API does not verify the restaurant service hours before it creates the order. It creates the order even if the restaurant is closed.

If a restaurant uses a Kitchen Display System (KDS) device, and has properly configured an auto-firing device, then the order is sent directly to the kitchen. The order is not subject to approval rules or manual approval when an auto-firing device is used.



