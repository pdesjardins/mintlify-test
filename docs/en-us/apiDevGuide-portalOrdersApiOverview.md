---
title: "Orders API overview"
id: portalOrdersApiOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
previousSectionTitle: "About the orders API"
nextSectionFile: apiDevGuide-apiOrdersOrderObjectSummary.md
nextSectionTitle: "Order object summary"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/]
excerpt: "The orders API allows you to create orders, update existing orders, and retrieve information about orders."
procedures: 0
codeExamples: 0
---

### Orders API overview

The orders API allows you to create orders, update existing orders, and retrieve information about orders.

#### Components of an order

Here is a high-level overview of the information contained in an order. For the full list of values in the `Order` object, see the [Orders section of the API reference](https://doc.toasttab.com/openapi/orders/overview/). For a summary of the `Order`object, including descriptions of the status, date-time, and amount fields associated with an order, see [Order object summary](apiOrdersOrderObjectSummary.html).

Each `Order` object in the orders API provides information about the order and its processing.

The order dining option determines whether the order is dine-in, takeout, curbside pickup (a variation of the takeout dining behavior), or delivery. Some dining options allow or require additional order information.

- Takeout and delivery orders require guest information.


- Delivery orders require a delivery address.


- Curbside pickup orders can include vehicle information.


- For dine-in orders, you can specify a table and identify a restaurant employee.



For more information about order values for dining options, see [Order details based on the order dining option](apiOrderTypeDetails.html).

Each order contains one or more checks. The order checks contain the majority of the order information. Orders often contain only one check. When guests split an order so that they can pay separately, then the order contains multiple checks.

An order check contains:



****Menu item selections****
: The selected items from the menu.

Each `Selection` object refers to a single menu item.

Each menu item can have modifiers that provide additional details and modifications. See [Applying modifiers and pre-modifiers](apiSpecifyingModifiersAndInstructions.html#apiApplyingModifiers).



****Price information****
: Information about the amount that the guest was charged.

Price information includes:

- The price information for the menu item selections.

The `receiptLinePrice` value is the original price of a menu item selection before any adjustments.

The `amount` value is the actual amount that the guest is charged. It includes any discounts and service charges.


- Applied discounts. A discount can be applied to the entire check or to an individual menu item selection. See [Working with order discounts](apiDiscountingOrders.html).


- Applied service charges.


- Applied taxes.



For more information about order price information, see [Order prices](apiOrderPrices.html).



****Guest information****
: Information about the guest.

Guest information in the orders API is only included under specific circumstances and varies by dining option.

For takeout and delivery orders, this information is required and will always be present. For dine-in orders, this information is typically not present but may be included in some situations. For example, some Toast Tables orders include customer information.

Note that the orders API sometimes uses the term "customer" to refer to a guest. For example, guest information is provided in the `customer` object.

Note that the `customer` object does not contain loyalty program information.



****Payment information****
: Payments that are applied to the check.





#### Diagrams of basic order structures

The following diagram shows the basic structure of a typical delivery order.

![Image](https://doc.toasttab.com/doc/media/order-api-overview-diagram-delivery.png)

The following diagram shows the basic structure of a typical curbside pickup order, which is a takeout order with curbside pickup enabled.

![Image](https://doc.toasttab.com/doc/media/order-api-overview-diagram-curbside.png)

The following diagram shows the basic structure of a typical dine-in order that has multiple checks.

![Image](https://doc.toasttab.com/doc/media/order-api-overview-diagram-dinein.png)

#### Orders API tasks

You can use the orders API to perform the following tasks:



****Create an order****
: For an overview of the order creation process, see [Creating orders](apiCreatingOrders.html).

The order creation process includes retrieving price information for the order checks. See [Getting check prices before you submit an order](apiOrderPrices.html#apiGettingCheckPrices).

You can provide the revenue center for an order. See [Providing revenue center information for an order](apiOrdersRevenueCenters.html).

For information about dining options and the required information for types of dining options, see [Order details based on the order dining option](apiOrderTypeDetails.html).



****Update an order****
: You can use the orders API to update an existing order. Examples of order updates include:

- [Adding items to an order check](apiAddingItemsToACheck.html)


- [Adding discounts to an order check](apiDiscountingOrders.html#apiAddingDiscountsToChecks)


- [Updating the tip information for a payment](apiUpdatingTipsInAPayment.html)


- [Adding a credit card payment to an order check](apiAddingPaymentsToACheck.html).


- [Changing the delivery information for an order](apiUpdatingDeliveryInfoForAnOrder.html)





****Retrieve information about orders****
: You can use an order GUID to retrieve the details for that order. See [Getting detailed information about one order](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).

You can retrieve details about orders that were either modified during a specific date range, or that were created on a specific business date. See [Getting detailed information about multiple orders](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutMultipleOrders).

You can only retrieve order details for orders that were created after December 1, 2015 (2015-12-01).

If your integration submits orders to the Toast platform, your integration is an ordering channel integration. In that case, your API client has both the `orders:read` and the `orders.channel:read`[scopes](apiScopes.html), and can only retreive orders from the Toast platform if your integration submitted them.





#### Orders API limitations

When using the orders API to create an order, be aware of the following limitations and default behavior.

##### Order scheduling

By default, the orders API creates an order that is to be fulfilled as soon as possible. It does not verify the restaurant service hours.

You are responsible for submitting orders while the restaurant is open. For more information, see [Getting information about a specific restaurant](apiRestaurantInformation.html).

You also can create an order to be fulfilled at a specific time. For example, you can create an order when the restaurant is closed, but indicate to fulfill the order when the restaurant is open. See [Scheduling future orders](orders_api_future_orders.html).

##### Order menu selection items

For the menu selection items in API orders, the following limitations apply:

- You cannot add open menu items to an `Order` object. An open menu item is one where the restaurant employee specifies both the item description and price.

However, you can add open priced menu items. An open priced menu item has a specified description. The restaurant employee only specifies the item price.


- The orders API cannot verify the availability of items based on time, menu visibility, or inventory.

You are responsible for preventing guests from ordering items that are not available.



##### Order payment

Orders created using the orders API are limited to the `CREDIT` and `OTHER` payment types.

Note that the orders API ignores the tax exempt setting for `OTHER` payment types. The order is taxed regardless of whether the payment type is configured to be tax exempt.

The orders API does not allow you to create cash orders or orders that use Toast gift cards.

##### Loyalty programs

You cannot use Toast loyalty functionality with orders that are created using the orders API.

You can use the orders API to apply a third-party loyalty program that is integrated with Toast. For details, see [Working with loyalty programs](apiDiscountingOrders.html#orders-api-loyalty-programs).

##### Gift card programs

You cannot use Toast or third-party gift card functionality with orders that are created using the orders API.

##### Order communication to the kitchen

If a restaurant uses a Kitchen Display System (KDS) device, and has properly configured an auto-firing device, then the order is sent straight to the kitchen.

The order is not subject to approval rules or manual approval.

##### Order text messages

Orders that are entered using the orders API do not [initiate SMS text messages](platformKitchenTextMessaging.html#adminSendTextMessage). Guests or servers only receive text messages when an order is entered in the Toast platform, for example, from a Toast POS device.

When building the functionality to send an order fulfillment text message from your platform, your code should inspect the `fulfillmentStatus` value of an order and ensure it is set to `READY` before it sends any messages. The `fulfillmentStatus` value is in the `selections`object which is a part of the `checks` object.

##### Order size

The orders API returns an HTTP status code 400 response when your integration attempts to:

- Post an order with more than 1,000 top-level selections.


- Post an item to an order that causes the order to have more than 1,000 top-level selections. For example, if an order has 995 top-level selections and your integration posts six items to that order in a single request, that request will be rejected.


- Post an order with a message body parameter that is greater than 1 megabyte (1 MB).



A top-level selection is defined as a selection that is not the child of another selection in the order.

To avoid exceeding the 1,000 top-level selection limit, Toast support encourages the grouping of identical items together, so:

- 1 soda


- 1 lemonade


- 1 energy drink


- 1 soda


- 1 lemonade


- 1 soda



Can be combined into:

- 3 sodas


- 2 lemonades


- 1 energy drink



This reduces the number of top-level selections in the request from six to three while providing the same order data.

