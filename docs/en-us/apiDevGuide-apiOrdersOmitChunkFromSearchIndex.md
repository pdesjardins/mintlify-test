---
title: "Chapter 2. Orders"
id: apiOrdersOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-integrationTestPlans.md
previousSectionTitle: "Integration test plans"
nextSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating order information"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/orders/operation/ordersGuidGet/, https://tools.ietf.org/html/rfc5988, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/]
procedures: 0
codeExamples: 0
---

# Chapter 2. Orders

## About the orders API

### Orders API overview

The orders API allows you to create orders, update existing orders, and retrieve information about orders.

#### Components of an order

Here is a high-level overview of the information contained in an order. For the full list of values in the `Order` object, see the [Orders section of the API reference](https://doc.toasttab.com/openapi/orders/overview/). For a summary of the `Order`object, including descriptions of the status, date-time, and amount fields associated with an order, see [Order object summary](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersOrderObjectSummary).

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
: For an overview of the order creation process, see [Creating orders](portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.html#apiCreatingOrders).

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
: You can use an order GUID to retrieve the details for that order. See [Getting detailed information about one order](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).

You can retrieve details about orders that were either modified during a specific date range, or that were created on a specific business date. See [Getting detailed information about multiple orders](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutMultipleOrders).

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

Orders that are entered using the orders API do not [initiate SMS text messages](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminSendTextMessage). Guests or servers only receive text messages when an order is entered in the Toast platform, for example, from a Toast POS device.

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

### Order object summary

An `Order` object contains details about an order. In the orders API, you use the `Order` object to create orders, update orders, and retrieve information about orders. You send `Order`objects in requests to create and update orders. The orders API returns `Order` objects in response to requests.

This topic discusses some related sets of values in the `Order` object and how they are populated.

#### Overview of Order object content

An `Order` object contains details about:

- What the guest ordered


- How the order is prepared and processed


- How the guest receives the order


- What the guest is charged for the order


- How the guest pays for the order



The following diagram provides a high-level overview of the `Order` object contents:

![Image](https://doc.toasttab.com/doc/media/order-api-order-object-overview.png)

#### GUIDs and identifiers in the order object

A GUID is a unique identifier that Toast generates when new objects are created.

You use GUIDs to identify configured objects that are relevant to the order, such as menu items, dining options, and discounts. Here is an example of a `DiningOption` object, which provides a dining option GUID to identify the dining option for an order.

```
"diningOption": {
  "guid": "18855a26-40d4-4a8f-b484-c6af211dd597"
},
```

To identify an object, you can use either `guid` or `multilocationId`. For more information about `multilocationId` and how to use it, see [Using multi-location IDs in orders](apiUsingMultiLocationIdsInOrders.html).

When you create an order, the Toast platform generates GUIDs for the `Order` object, `Check` objects, and `Selection` objects. These GUIDs are returned in orders API responses.

You use those GUIDs to identify an order, check, or menu item selection to retrieve or to modify.

#### Order status information

In the `Order` object, the status information reflects the current status of the order, check, or menu item selection. Statuses can reflect the current status of fulfillment or payment.

Status information is returned in responses.

In most cases, the Toast platform updates the status values based on actions to an item, check, or order.

##### Order status values

An order can have the following status values:



**`approvalStatus`**
: This status indicates the current status of the order in the fulfillment process. It only reflects whether the order is sent to the kitchen. It does not reflect whether the order is completed, delivered, or paid for.

For future orders, `approvalStatus` is `FUTURE`. Restaurant employees do not receive the order until it is time to fulfill it.

For new orders that need to be approved by a restaurant employee, `approvalStatus` is `NEEDS_APPROVAL`.

When the order is approved, `approvalStatus`changes to `APPROVED`. New orders that do not require approval are automatically `APPROVED`.

If an order is not approved after a specific amount of time, `approvalStatus` changes from `NEEDS_APPROVAL` to `NOT_APPROVED`.



**`deliveryInfo.deliveryState`**
: For delivery orders, the `deliveryState` value indicates the current status of the order delivery.

Until the order is ready to be delivered, `deliveryState` is `PENDING`.

When the delivery driver picks up the order, `deliveryState` is `PICKED_UP`.

When the delivery driver is on their way to the delivery address, `deliveryState` is `IN_PROGRESS`.

When the delivery is complete, `deliveryState` is `DELIVERED`.





##### Check status values

A check can have the following status values:



**`paymentStatus`**
: The overall status of the check payment.

The `paymentStatus` is `OPEN` until a payment is applied.

The `paymentStatus` is `PAID` when a payment is applied but has not been adjusted for the tip.

The `paymentStatus` is `CLOSED` when the check is fully paid.



**`Payment.paymentStatus`**
: For credit card payments, the status of the credit card processing.

The status indicates the current approval and capture status of the credit card payment. It also reflects when a payment is cancelled or voided.



**`Payment.refundStatus`**
: The status of a refund on a payment.

`NONE` indicates that the refund was not processed.

`PARTIAL` indicates that a partial refund was issued.

`FULL` indicates that a full refund was issued.





##### Menu item selection status values

A menu item selection can have the following status values:



**`fulfillmentStatus`**
: The status of the preparation of the menu item selection. The `fulfillmentStatus` indicates whether the kitchen is currently working to prepare the item.

`NEW` menu item selections were added to a check but are not sent to the KDS for preparation.

`HOLD` menu item selections were paused by a restaurant employee. They are not sent to the KDS for preparation.

`SENT` menu item selections were fired and appear in the KDS for preparation.

`READY` menu item selections have completed preparation. They are fulfilled and do not appear on the KDS. The `READY` status is only used If your restaurant uses the Toast platform KDS.





#### Order dates and times

In the `Order` object, the order, checks, and menu item selections have multiple dates and times associated with them. The dates and times track events related to the order placement and processing, including when the order entities are created, updated, completed, and paid for.

Many order-related dates and times are set by the Toast platform based on the creation or modification of an order entity. For example, when an order is created, the Toast platform sets the `createdDate`. Or when an order is voided, the Toast platform sets the `voidDate`. You do not set those dates, but you do see those dates when you retrieve order details.

The following timestamps are associated with orders, checks, and menu item selections.

##### Order creation and scheduling dates

The following dates are set when an order is created.



**`createdDate`**
: **Applies to:**`Order`, `Check`, `Selection`

**Populated by:** Toast platform

**Format:** Date-time string

The date and time when the Toast platform received the order, check or menu item selection.

Populated by Toast when it receives the order, check, or menu item selection.



**`openedDate`**
: **Applies to:**`Order`, `Check`

**Populated by:** Either provided in the `Order` object or populated by the Toast platform.

**Format:** Date-time string

The date and time when the order or check was opened.

For dine-in and as soon as possible (ASAP) orders, `openedDate` should match `createdDate`.

For future orders, `openedDate` should match `promisedDate`.

If you do not provide a value for `openedDate`, then the Toast platform sets `openedDate` to the current date and time, which will be nearly identical to `createdDate`.



**`promisedDate`**
: **Applies to:**`Order`

**Populated by:** Provided in the order request

**Format:** Date-time string

For future orders, the date and time that the order is scheduled to be fulfilled.

For dine-in and ASAP orders, `promisedDate` is `null`.



**`estimatedFulfillmentDate`**
: **Applies to:**`Order`

**Populated by:** Toast platform

**Format:** Date-time string

The date and time when a delivery or takeout order is expected to be ready.

For dine-in and ASAP orders, calculated by the Toast platform based on the `openedDate` and the required preparation time. For takeout and delivery orders, the calculation also includes any throttling that is currently in effect.

For future orders, matches `promisedDate`.





##### Order fulfillment, payment, and delivery

The following dates and times are set based on when an order is fulfilled, delivered, and paid for.



**`businessDate`**
: **Applies to:**`Order`

**Populated by:** Toast platform

**Format:** Integer (`yyyymmdd`)

The date when the order was fulfilled.

Calculated by the Toast platform based on the business date cutoff time for the restaurant. The cutoff time is configured In Toast Web. In the restaurants API, the cutoff time is returned as the value of `closeoutHour`.

By default, the cutoff time is 4:00 AM. For example, an order that is fulfilled at 1:00 AM on December 3 would be considered fulfilled on December 2.



**`dispatchedDate`**
: **Applies to:**`Order`

**Populated by:** Toast platform

**Format:** Date-time string

For delivery orders, the date and time when the order is ready to be delivered and assigned to a driver.

Set when the order is marked as ready to deliver on a Toast POS device.



**`deliveredDate`**
: **Applies to:**`Order`

**Populated by:** Toast platform

**Format:** Date-time string

For delivery orders, the date and time when the order was marked as delivered.

Set when the employee marks the order as delivered on a Toast POS device.



**`paidDate`**
: **Applies to:**`Order`, `Check`

**Populated by:** Either provided in the `Order` object or calculated by the Toast platform

**Format:** Date-time string

The most recent date when the order or check received a payment.

If you provide a payment without a payment date, the Toast platform sets `paidDate` to the current system time.



**`closedDate`**
: **Applies to:**`Order`, `Check`

**Populated by:** Toast platform

**Format:** Date-time string

The date when the order and check are paid.

For orders with tips, the Toast platform populates `closedDate` when the payment and tip are added.

For orders without tips, the Toast platform populates `closedDate` during the nightly closeout batch.





##### Order changes, deletions, and voids

The following dates are set based on changes to an order.



**`modifiedDate`**
: **Applies to:**`Order`, `Check`, `Selection`

**Populated by:** Toast platform

**Format:** Date-time string

The most recent date that the order, check, or menu item selection was modified.

Populated when an order entity is created and when a change occurs to the order, check, or menu item selection.



**`deletedDate`**
: **Applies to:**`Order`, `Check`

**Populated by:** Toast platform

**Format:** Date-time string

The date and time when the order or check was deleted.

Populated when `deleted` is set to `true`.

If `deleted` is `false`, then `deletedDate` uses the Unix epoch as a placeholder value.

When an order is deleted, the checks are deleted and inherit the `deleted` and `deletedDate`values.



**`voidDate`**
: **Applies to:**`Order`, `Check`, `Selection`

**Populated by:** Toast platform

**Format:** Date-time string

The date and time when the order, check, or menu item selection was voided.

Populated when the order, check, or menu item selection is voided.

When an order is voided, the checks and menu item selections are voided and inherit the `voidDate`.

When a check is voided, the menu item selections for that check are voided and inherit the `voidDate`.



**`voidBusinessDate`**
: **Applies to:**`Order`, `Check`, `Selection`

**Populated by:** Toast platform

**Format:** Integer (`yyyymmdd`)

The business date that corresponds to the value of `voidDate`.

Populated based on `voidDate` and the business date cutoff time for a restaurant.

The cutoff time is set in Toast Web. In the restaurants API, the cutoff time is returned as the value of `closeoutHour`.

By default, the cutoff time is 4:00 AM. For example, if a check is voided at 1:00 AM on January 5, `voidedBusinessDate` would be January 4.





#### Order amounts

The order amount values determine the amount that guests are charged. Amount values are associated with menu item selections and checks.

For most of the amount values in the `Order` object, the Toast platform either retrieves the amount from the restaurant configuration, or uses an algorithm to calculate it based on other values. For example, prices for menu selection items are configured. Amounts such as taxes and check totals are calculated.

##### Components of order amounts

Order amounts include the following components:



****Menu item prices****
: The prices of the selected menu items.

For most items, prices are specified in the menu configuration.

Some items are open price items, which means that you provide the price when you create the order.

For more information, see the [menu pricing section](adminPricingStrategyDetailsOmitChunkFromSearchIndex.html#adminPricingStrategiesOverview) of the *Platform Guide*.



****Taxes****
: The tax charged for the menu selection items.

Taxes are calculated based on the applicable taxes and tax rates.

For more information on taxes and tax rates, see the [taxes section](adminTaxesOmitChunkFromSearchIndex.html#adminTaxesOverview) of the *Platform Guide*.



****Service charges****
: The service charges that are added to checks.

On the Toast platform, some service charges are added automatically based on the order type. Other service charges can be added by the restaurant employee. In the orders API, all service charges must be included in the order request. Service charges are never applied automatically to orders from the orders API.

Service charges might also be taxable.

For more information on service charges, see the [service charges section](adminServiceChargesOmitChunkFromSearchIndex.html#adminServiceChargeOverview) in the *Platform Guide*.



****Discounts****
: The applicable discounts that reduce the amount of a check or a menu item selection.

For more information on configuring discounts, see [Managing discounts](adminAvailableDiscounts.html) in the *Platform Guide*.





##### Amounts on menu item selections

A menu item selection has the following amounts associated with it.



**`receiptLinePrice`**
: The price of a menu item selection before the quantity, taxes, discounts, and modifier option adjustments are applied. For items that use size pricing, `receiptLinePrice` is the price of the selected size.

For example, if the menu item selection is for two orders of fries, `receiptLinePrice` is the price of one order of fries. If a menu item selection is for three large drinks, `receiptLinePrice` is the price of one large drink.

Populated based on the menu configuration, or using the value provided in `externalPriceAmount` or `openPriceAmount`.



**`externalPriceAmount`**
: Only used in orders that are created by marketplace facilitator organizations. Provided with new orders. Not returned for existing orders.

The price of the menu item selection as calculated by the marketplace facilitator. This is the price before the quantity, taxes, discounts, and modifier option adjustments are applied.

For more information about marketplace facilitator orders, see [Marketplace facilitator orders](apiMarketplaceFacilitatorOrders.html).

Used to populate `receiptLinePrice`.



**`openPriceAmount`**
: Provided with new orders for open price menu items. Not returned for existing orders.

The price of the menu item selection before the quantity, taxes, discounts, and modifier option adjustments are applied.

Used to populate `receiptLinePrice`.



**`preDiscountPrice`**
: Gross sales price for the item before tax and discounts. Reflects the ordered quantity.

`prediscountPrice = receiptLinePrice x
            quantity`



**`Discount.discountAmount`**
: The currency amount of the discount.

For open discounts, you provide `discountAmount`when you add the discount.

Otherwise, the Toast platform populates `discountAmount` based on the discount configuration.

Returned for all discounts.



**`Discount.discountPercent`**
: For a percent discount, the percentage of the discount. For example, for a 10% discount, `discountPercent` is 10.

Used to calculate `discountAmount` for percent discounts.



**`Discount.nonTaxDiscountAmount`**
: The currency amount of the discount on the non-taxable portion of the menu item selection.

In most cases, `nonTaxDiscountAmount` is identical to `discountAmount`.

The values are only different when you apply a percent discount to an item that has the tax included in the price. In that case, `nonTaxDiscountAmount` is less than `discountAmount`.



**`price`**
: Final price charged to the guest for the item. Includes the ordered quantity and discounts. Does not include tax.

`price = preDiscountPrice -
            sum(Discount.discountAmount)`



**`AppliedTax.taxAmount`**
: The tax amount for a specific tax. Calculated by the Toast platform based on the specific tax configuration.



**`tax`**
: The total tax on the menu item selection.

`tax = sum(AppliedTax.taxAmount)`





##### Amounts on checks

A check can have the following amount values associated with it:



**`Discount.discountAmount`**
: The currency amount of a discount on the check.

For open discounts, provided in new orders.

Otherwise, populated by the Toast platform based on the discount configuration.

Returned for all discounts.



**`Discount.discountPercent`**
: For a percent discount, the percentage of the discount.

For example, for a 10% discount, `discountPercent` is 10.

Used to calculate `discountAmount` for percent discounts.



**`Discount.nonTaxDiscountAmount`**
: The currency amount of the discount on the non-taxable portion of the check.

In most cases, `nonTaxDiscountAmount` is identical to `discountAmount`.

The values are only different when you apply a percent discount to a check that contains items that have the tax included in the price. In that case, `nonTaxDiscountAmount` is less than `discountAmount`.



**`ServiceCharge.chargeAmount`**
: The amount of a service charge.

For open amount service charges, provided with the order.

Otherwise, the Toast platform populates the amount based on the service charge configuration.



**`ServiceCharge.AppliedTax.taxAmount`**
: The amount of an applicable tax on the service charge.

Calculated by the Toast platform based on the specific tax configuration.



**`amount`**
: The total calculated price of the check including discounts and service charges. The `amount` does not include gratuity or taxes. Response only.

`amount = sum(Item.price) + sum(Service
            charge.filter(gratutity=false).chargeamount)`



**`taxAmount`**
: The total tax on the check. Includes the taxes on the menu item selections and service charges.

`taxAmount = sum(Item.tax) + sum(Service Charge.Applied
            Tax.taxAmount)`



**`totalAmount`**
: The total amount of the check. `totalAmount`includes discounts, service charges, and taxes.

`totalAmount = amount + taxAmount`

`totalAmount` is not affected by refunds. Refund information is provided in the menu item selection and payment details.

`totalAmount` is affected by voids. When you void a menu item selection, `totalAmount` is reduced by the amount charged for the menu item selection.





##### Example order with order amounts

To demonstrate the item and check amounts, we'll use a simple example order.

The order contains a single menu item selection for two grilled cheese sandwiches. A grilled cheese sandwich costs $8.00.

The guest receives a $1.00 discount on the item.

The item is subject to a 5% state tax and a 4% city tax.

The check has a $3.00 delivery service charge that is not taxed.

For the menu item selection, the amounts are as follows:

| Amount | Value | Calculation | 
| --- | --- | --- |
| `receiptLinePrice` | 8.0 | In the menu, a grilled sandwich costs $8.00 | 
| `preDiscountPrice` | 16.0 | Multiply `receiptLinePrice` (8.0) by `quantity` (2). | 
| `Discount.discountAmount` | 1.0 | The applied discount is for $1.00. | 
| `Discount.nonTaxDiscountAmount` | 1.0 | The applied discount is for $1.00. The tax is not included in the price, and the discount is a fixed amount discount, so the two discount amount values are the same. | 
| `price` | 15.0 | Subtract the total `discountAmount`(1.0) from the `preDiscountPrice`(16.0). | 
| `AppliedTax.taxAmount` (State tax) | 0.75 | Multiply the `rate` for the state tax (.05) by the `price` (15.0). | 
| `AppliedTax.taxAmount` (City tax) | 0.65 | Multiply the `rate` for the city tax (.04) by the `price` (15.0). | 
| `tax` | 1.35 | Add the `taxAmount` values (0.75 and 0.65). | 

For the check, the amounts are as follows:

| Amount | Value | Calculation | 
| --- | --- | --- |
| `appliedDiscounts` | No values | There are no discounts on the check, just on the item. | 
| `ServiceCharge.chargeAmount` | 3.0 | There is a $3.00 delivery charge. | 
| `ServiceCharge.appliedTaxes` | No values | The delivery charge is not taxed. | 
| `amount` | 18.0 | Add the `price` from the menu selection item (15.0) to the service charge (3.0). | 
| `taxAmount` | 1.35 | The total of the `tax` values on the menu selection items. The `tax` value for the single menu selection item is 1.35. | 
| `totalAmount` | 19.35 | Add `amount` (18.0) and `taxAmount` (1.35). | 

### Submitting your first order to the orders API

This topic describes how to authenticate, gather required information, build an order JSON payload, and submit your first order to the Toast orders API.

#### Prerequisites

Before you begin, ensure you have the following:

- **API client credentials** - You need a `clientId` and `clientSecret` for authentication. For information about setting up an API client, see [Authentication](authenticationOmitChunkFromSearchIndex.html#authentication).


- **Required scopes** - Your API client must have access to the following scopes:

- `orders.orders:write` - Required to submit orders.


- `config:read` - Required to retrieve dining options, menu groups, and menu items.



For more information about scopes, see [Scopes](apiScopes.html).


- **Location GUID** - The unique identifier for the Toast location you are submitting orders for. You can find this in Toast Web or retrieve it using the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/).



#### Order object overview

Every order requires, at minimum, a dining option and a check with menu item selections. The following example shows the basic `Order` object structure.

```
{
  "diningOption": {
    "guid": "`{diningOption GUID}`"
  },
  "checks": [
    {
      "selections": [
        {
          "item": {
            "guid": "`{selection item GUID}`"
          },
          "itemGroup": {
            "guid": "`{itemGroup GUID}`"
          },
          "quantity": 1
        }
      ]
    }
  ]
}
```

The following table describes the required fields:

| Field | Type | Description | 
| --- | --- | --- |
| `diningOption` | Object | Specifies the dining option for the order. Must contain a `guid` that references a valid dining option configured for the location. | 
| `checks` | Array | An array of `Check` objects. Most orders have one check. Each check must contain at least one menu item selection. | 
| `checks.selections` | Array | An array of `Selection` objects representing the menu items being ordered. | 
| `checks.selections.item` | Object | A reference to the menu item being ordered. Must contain the `guid` of a valid menu item. | 
| `checks.selections.itemGroup` | Object | A reference to the menu group that contains the menu item. Must contain the `guid` of the parent menu group. | 
| `checks.selections.quantity` | Number | The number of this menu item to order. Use a whole number for discrete items or a decimal for items sold by weight. | 

For detailed information about all values in an `Order`object, see [Order object summary](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersOrderObjectSummary) and the [orders API reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

##### Required headers

All requests to the Toast platform APIs require the following headers:

| Header | Description | 
| --- | --- |
| `Toast-Restaurant-External-ID` | The GUID of the Toast location for the request. | 
| `Authorization` | The access token in the format *`Bearer
              {accessToken}`*. | 
| `Content-Type` | Required for `POST`requests. Must be set to `application/json`. | 

#### Submitting your first order

Complete the following steps to submit your first order.

##### To submit your first order

1. **Authenticate and get an access token**

Before making any API requests, you must obtain an access token using your client credentials.

Send a `POST` request to the `/authentication/v1/authentication/login` endpoint with the following request body:

```
{
  "clientId": "`clientId`",
  "clientSecret": "`clientSecret`",
  "userAccessType": "TOAST_MACHINE_CLIENT"
}
```

The response includes an access token to use in the `Authorization` header for subsequent requests:

```
{
  "token": {
    "tokenType": "Bearer",
    "scope": "orders:write,orders:read",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#authResponseScopeCO)
    "expiresIn": 86400,
    "accessToken": "eyJ0eXAiOiJKV1Q..."[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#authResponseAccessTokenCO)
  },
  "status": "SUCCESS"
}
```



(1) The list of scopes assigned to your API client.

(2) The authentication bearer token needed to place API calls.

Store the `accessToken` value for use in the following steps.

For more information about authentication, see [Authentication](authenticationOmitChunkFromSearchIndex.html#authentication).


2. **Retrieve the available dining options**

Every order requires a dining option. Send a `GET` request to the `/config/v2/diningOptions` endpoint to retrieve the dining options configured for the location.

The response returns an array of dining options:

```
[
  {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption",
    "name": "Dine-in",
    "curbside": false,
    "behavior": "DINE_IN"
  },
  {
    "guid": "7c6843f3-db7d-4096-bdd2-4eefd99b900f",
    "entityType": "DiningOption",
    "name": "Takeout",
    "curbside": false,
    "behavior": "TAKE_OUT"
  },
  {
    "guid": "b1b10604-a8f9-4a21-ae86-7db974ee9dbf",
    "entityType": "DiningOption",
    "name": "Delivery",
    "curbside": false,
    "behavior": "DELIVERY"
  }
]
```

Note the `guid` of the dining option you want to use. This example uses "Dine-in" with GUID `23fc2559-fc37-46ce-a963-cc5fdb88af0c`.

For more information, see [Retrieving the available dining options](apiOrderTypeDetails.html#apiOrdersGetDiningOptions).


3. **Retrieve menu groups**

Menu items belong to menu groups. Send a `GET` request to the `/config/v2/menuGroups` endpoint to retrieve the menu groups.

The response returns an array of menu groups with their GUIDs and names. Note the `guid` of the menu group that contains the item you want to order.

```
[
  {
    "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
    "entityType": "MenuGroup",
    "externalId": null,
    "name": "Hamburgers",
    "menu": {
      "guid": "a9b6e0d4-5c3f-4e2a-b1d8-7f9e6c5a4b3d",
      "entityType": "Menu"
    },
    "visibility": "ALL",
    "menuItems": [
      {
        "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
        "entityType": "MenuItem"
      }
    ]
  },
  {
    "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
    "entityType": "MenuGroup",
    "externalId": null,
    "name": "Smoothies",
    "menu": {
      "guid": "a9b6e0d4-5c3f-4e2a-b1d8-7f9e6c5a4b3d",
      "entityType": "Menu"
    },
    "visibility": "ALL",
    "menuItems": [
      {
        "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
        "entityType": "MenuItem"
      }
    ]
  }
]
```


4. **Retrieve menu items**

Send a `GET` request to the `/config/v2/menuItems` endpoint to retrieve menu items.

The response includes each menu item's `guid`, `name`, and `menuGroups` array:

```
[
  {
    "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
    "entityType": "MenuItem",
    "externalId": null,
    "name": "Good Burger",
    "sku": "BURG-001",
    "plu": null,
    "visibility": "ALL",
    "orderableOnline": "YES",
    "menuGroups": [
      {
        "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
        "entityType": "MenuGroup"
      }
    ],
    "optionGroups": [
      {
        "guid": "47d73134-03da-4fb5-b564-5358b3b37d34",
        "entityType": "MenuOptionGroup"
      }
    ]
  },
  {
    "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
    "entityType": "MenuItem",
    "externalId": null,
    "name": "Smoothie",
    "sku": "SMO-002",
    "plu": null,
    "visibility": "ALL",
    "orderableOnline": "YES",
    "menuGroups": [
      {
        "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
        "entityType": "MenuGroup"
      }
    ],
    "optionGroups": []
  }
]
```

Note the `guid` of the menu items you want to order and the corresponding menu group GUIDs in the `menuGroups` array.

Menu items can belong to multiple menu groups. If a menu item belongs to more than one menu group, the `menuGroups`array contains multiple entries. When you submit an order, you must specify which menu group you're ordering from by including the correct menu group GUID in the `itemGroup` field. This is important because different menu groups can have different modifier groups, pricing, and other properties. The orders API validates that the menu item belongs to the specified menu group.


5. **Build your order JSON**

Using the GUIDs you collected, build your order JSON. The following example shows a simple dine-in order with two menu items:

```
{
  "entityType": "Order",
  "diningOption": {[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderDiningOptionCO)
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderChecksCO)
    {
      "entityType": "Check",
      "selections": [[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderSelectionsCO)
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderItemGuidCO)
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",[(5)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderItemGroupCO)
            "entityType": "MenuGroup"
          },
          "quantity": 1[(6)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderQuantityCO)
        },
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
            "entityType": "MenuGroup"
          },
          "quantity": 2
        }
      ]
    }
  ]
}
```



(1) The diningOption object specifies the dining option for the order such as dine-in or takeout. Use the GUID of a valid dining option from step 2.

(2) The checks array contains one or more Check objects. Most orders have a single check.

(3) The selections array contains the menu items being ordered.

(4) The GUID of the menu item. Retrieve this from the configuration API.

(5) The GUID of the menu group that contains this item. The item must belong to this group.

(6) The quantity of this item being ordered.


6. **Get the order price (optional but recommended)**

Before submitting the order, you can validate the order and retrieve pricing information by sending the order to the `/orders/v2/prices` endpoint.

Send a `POST` request to the `/orders/v2/prices` endpoint. Include your order JSON as the message body.

The response returns the order with calculated prices, taxes, and totals. This step also validates your order structure and confirms that all referenced entities exist:

```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "amount": 25.00,[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#pricesResponseAmountCO)
      "taxAmount": 2.19,[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#pricesResponseTaxCO)
      "totalAmount": 27.19,[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#pricesResponseTotalCO)
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
            "entityType": "MenuGroup"
          },
          "quantity": 1,
          "preDiscountPrice": 12.00,
          "price": 12.00,[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#pricesResponseItemPriceCO)
          "tax": 1.05
        },
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
            "entityType": "MenuGroup"
          },
          "quantity": 2,
          "preDiscountPrice": 13.00,
          "price": 13.00,
          "tax": 1.14
        }
      ],
      "appliedTaxes": [],
      "appliedServiceCharges": []
    }
  ]
}
```



(1) The subtotal of the check before taxes.

(2) The total tax amount for the check.

(3) The total amount due including taxes.

(4) The calculated price for each menu item selection.

For more information, see [Getting check prices](apiOrderPrices.html#apiGettingCheckPrices).


7. **Submit the order**

Send a `POST` request to the `/orders/v2/orders` endpoint to submit your order. Include your order JSON as the message body.

A successful response (HTTP 200) returns the complete `Order` object with generated GUIDs, calculated prices, and status information:

```
{
  "guid": "89488287-f259-435b-a654-0bc391596af0",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderResponseGuidCO)
  "entityType": "Order",
  "source": "API",[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderResponseSourceCO)
  "approvalStatus": "NEEDS_APPROVAL",[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderResponseStatusCO)
  "businessDate": 20250115,
  "createdDate": "2025-01-15T14:30:00.000+0000",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "guid": "6e1bb8e0-534d-437f-bbad-0f08045f463e",[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderResponseCheckGuidCO)
      "entityType": "Check",
      "amount": 25.00,[(5)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderResponseAmountCO)
      "taxAmount": 2.19,
      "totalAmount": 27.19,
      "selections": [
        {
          "guid": "f520f731-8164-41a8-b261-23b9df3bf861",
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
            "entityType": "MenuGroup"
          },
          "quantity": 1,
          "price": 12.00,
          "tax": 1.05
        }
      ],
      "paymentStatus": "OPEN"
    }
  ]
}
```



(1) The Toast platform generates a unique GUID for the order. Use this GUID to retrieve or modify the order later.

(2) The orders API sets the source value to API for orders you submit.

(3) The approvalStatus indicates the order's position in the fulfillment process. Depending on location configuration, the order may require approval before the kitchen receives it.

(4) Each check receives a unique GUID. Use this to add items or payments to the check.

(5) The amount, taxAmount, and totalAmount values show the calculated check totals.



#### Adding modifiers to menu items

Many menu items have associated modifiers, such as toppings or preparation options. To add modifiers to a menu item selection, include a `modifiers` array within the selection.

First, retrieve the modifier options for a menu item by sending a `GET` request to the `/config/v2/menuOptionGroups/`{guid}``endpoint.

The following example shows a selection with a modifier:

```
{
  "entityType": "MenuItemSelection",
  "item": {
    "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
    "entityType": "MenuItem"
  },
  "itemGroup": {
    "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
    "entityType": "MenuGroup"
  },
  "quantity": 1,
  "modifiers": [[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderModifiersCO)
    {
      "entityType": "MenuItemSelection",
      "item": {
        "guid": "58e6629f-5a1e-42f8-b6c7-4351d628b92d",[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderModifierItemCO)
        "entityType": "MenuItem"
      },
      "optionGroup": {
        "guid": "47d73134-03da-4fb5-b564-5358b3b37d34",[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#firstOrderOptionGroupCO)
        "entityType": "MenuOptionGroup"
      },
      "quantity": 1
    }
  ]
}
```



(1) The modifiers array contains modifier selections that apply to the parent menu item.

(2) The GUID of the modifier item (for example, a topping or add-on option).

(3) The GUID of the option group that contains the modifier. This is required for modifier selections.

For more information, see [Applying modifiers to orders](apiSpecifyingModifiersAndInstructions.html#apiApplyingModifiers).

#### Error handling

When submitting orders, you may encounter the following HTTP status codes:

| Status Code | Description | Resolution | 
| --- | --- | --- |
| 200 | Success | The API created the order successfully. The response body contains the complete order details. | 
| 400 | Bad Request | The request contains invalid data. Check the error message for details. Common causes include invalid GUIDs, missing required fields, or items that do not belong to the specified menu group. | 
| 401 | Unauthorized | The access token is missing, invalid, or expired. Obtain a new access token and retry the request. | 
| 403 | Forbidden | The API client does not have access to the location or does not have the required scope (`orders.orders:write`). | 
| 404 | Not Found | A referenced entity (such as a menu item or dining option) does not exist or belongs to a different location. | 
| 413 | Payload Too Large | The number of checks in the order exceeds the allowed limit. | 
| 415 | Unsupported Media Type | The request does not include the `Content-Type:
            application/json` header. | 
| 500 | Internal Server Error | An unexpected error occurred. Note the `requestId` from the error response and contact Toast support if the issue persists. | 

##### Common error messages

The following table describes common error messages and their resolutions:

| Error Message | Resolution | 
| --- | --- |
| `Could not parse as Order
              object` | Your request body contains malformed JSON or invalid data types. Common causes include missing or extra commas, unclosed brackets or braces, unquoted strings, or numeric values that exceed allowed limits. Validate your JSON syntax before submitting the request. | 
| Item (`item GUID`) does not belong to the group (`item group GUID`) | The menu item you specified is not part of the referenced menu group. Verify the item's menu group by checking the `menuGroups` array in the menu items response. If the menu item belongs to multiple menu groups, ensure you're using the correct menu group GUID from the `menuGroups` array. | 
| `Referenced entity (type=MenuItem) must
              contain either a GUID or MultiLocationId` | A menu item in your request is missing its GUID. Ensure every `item` object contains a valid `guid` value. | 
| `Referenced entity (type=DiningOption) must
              contain a GUID` | The `diningOption` object is missing its GUID. Retrieve valid dining option GUIDs from the configuration API. | 

#### Next steps

After successfully submitting your first order, you can explore additional capabilities of the orders API:

- **Add payments** - Add payment information to close the check. For more information, see [Adding payments to an existing check](apiAddingPaymentsToACheck.html).


- **Create different order types** - Learn about creating takeout, delivery, and curbside orders. For more information, see [Order details based on the order dining option](apiOrderTypeDetails.html).


- **Apply discounts** - Add discounts to items or checks. For more information, see [Working with order discounts](apiDiscountingOrders.html).


- **Schedule future orders** - Create orders to be fulfilled at a specific date and time. For more information, see [Scheduling future orders](orders_api_future_orders.html).


- **Retrieve order details** - Get information about existing orders. For more information, see [Getting detailed information about one order](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).


- **Void an order** - Cancel an order that was accidentally placed or is no longer needed. For more information, see [Void an order](apiVoidOrder.html).



For complete API reference documentation, see the [orders API reference](https://doc.toasttab.com/openapi/orders/overview/).

### Getting order information

#### Required scopes to retrieve order data

To retrieve order data from the Toast platform, your Toast API client must at least have the `orders:read` scope. API clients that submit orders to the Toast platform must have both the `orders:read` scope and the `orders.channel:read`scope.

The following scopes allow you to view guest data:



**`delivery_info.address:read`**
: This scope is needed to view the `deliveryInfo`information, which provides details about the address to deliver the order to.

If your Toast API client does not have the `delivery_info.address:read` scope, then the `deliveryInfo` value is `null`.



**`guest.pi:read`**
: This scope is needed to view the following values:

- `Check.customer` - Name and contact information for the guest.


- `curbsidePickupInfo` - Information about the vehicle the guest uses for a curbside pickup.



If your Toast API client does not have the `guest.pi:read` scope, then the response does not include the `customer` or `curbsidePickupInfo`values.





For more information about scopes and how they work, see [Scopes](apiScopes.html).

#### Getting detailed information about one order

You can use the orders API to retrieve detailed information about a single order. To identify the order to return, you use the order GUID.

##### How to make the request

To request details for a single order, you must have the order GUID.

You send a `GET` request to the `/orders/`{guid}`` endpoint.

##### Example request for detailed information about one order

The following example shows a request for detailed information about one order.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e12909EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e13109EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
"https://`[toast-api-hostname]`/orders/v2/orders/
017fdd94-4a30-4657-9475-b1a684758531"[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e13309EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the GUID of the restaurant that created the orders. This must be the GUID of an individual restaurant. It cannot be the GUID of a restaurant group.

(3) Send a GET request to the /orders/{guid} endpoint of the orders API. Specify the GUID of the order as a path parameter.

##### Example response data

The following example shows the response data from the `/orders/{guid}` endpoint. It contains detailed information about one order.

```
{
  "guid": "017fdd94-4a30-4657-9475-b1a684758531",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e15009EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": {
      "guid": "9ab6a5cf-32e0-47ee-9fd3-c73507ef3c01",
      "entityType": "RevenueCenter",
      "externalId": null
  },
  "server": {
    "guid": "5c305143-183f-49cf-b4d5-49a610826822",
    "entityType": "RestaurantUser",
    "externalId": null
  },
  "lastModifiedDevice": {
    "id": "175785aa78a7c4dc"
  },
  "createdDevice": {
      "id": "175785aa78a7c4dc"
  },
  "deliveryInfo": {[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersDeliveryInfo2)
    "address1": "401 Park Drive",
    "address2": "Suite 801",
    "city": "Boston",
    "state": "MA",
    "zipCode": "02215",
    "latitude": 42.3446671,
    "longitude": -71.1023575,
    "notes": ""
  },
  "serviceArea": null,
  "curbsidePickupInfo": {[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersCurbsideInfo2)
    "entityType": "CurbsidePickup",
    "notes": "Convertible with top down",
    "transportColor": "blue",
    "transportDescription": "Street Cruiser"
  },
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "d527b5cf-96d2-41dc-92e6-8e9ca1ed36bd",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "In Store",
  "voidDate": null,
  "openedDate": "2019-02-24T13:48:44.206+0000",
  "duration": 54,
  "businessDate": 20190224,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": "9f42438a-a375-4983-9f80-c0dae5c33196",
      "entityType": "Check",
      "externalId": null,
      "displayNumber": "2",
      "amount": 1.0,
      "tabName": "Toasty Toaster",
      "taxExempt": false,
      "payments": [
        {
          "guid": "e8cee462-78b4-4d83-a8ac-6006903f36d7",
          "entityType": "OrderPayment",
          "externalId": null,
          "originalProcessingFee": 0.04,
          "amount": 1.06,
          "tipAmount": 0,
          "amountTendered": 0,
          "cashDrawer": null,
          "cardType": "VISA",
          "lastModifiedDevice": {
              "id": "175785aa78a7c4dc"
          },
          "createdDevice": {
              "id": "175785aa78a7c4dc"
          },
          "refundStatus": "NONE",
          "houseAccount": null,
          "type": "CREDIT",
          "voidInfo": null,
          "otherPayment": null,
          "paidDate": "2019-02-24T13:49:38.617+0000",
          "cardEntryMode": "PRE_AUTHED",
          "paymentStatus": "CAPTURED",
          "paidBusinessDate": 20190224,
          "last4Digits": "1111",
          "refund": null
        }
      ],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2019-02-24T13:48:44.206+0000",
      "totalAmount": 1.06,
      "lastModifiedDevice": {
          "id": "175785aa78a7c4dc"
      },
      "createdDevice": {
          "id": "d64b3fd17cad3db2"
      },
      "selections": [
        {
          "guid": "69684faa-c35d-4ab4-9bff-41805ae52276",
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "a7b9ee4d-e41b-46ac-9ba4-d56dd7b2fb20",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "receiptLinePrice": 1,[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#co-receiptLinePrice)
          "preDiscountPrice": 1,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "test",
          "appliedDiscounts": [],
          "tax": 0.06,
          "modifiers": [],
          "seatNumber": -1,[(5)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#coSeatNumber)
          "voidDate": null,
          "fulfillmentStatus": "SENT",
          "optionGroupPricingMode": null,
          "salesCategory": {
              "guid": "b6a5fa5c-5b4f-49ca-a49f-d35814110f81",
              "entityType": "SalesCategory",
              "externalId": null
          },
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": "2019-02-24T13:48:44.806+0000",
          "preModifier": null,
          "price": 1,
          "modifiedDate": "2019-02-24T13:49:39.252+0000",
          "voided": false,
          "diningOption": {
              "guid": "d527b5cf-96d2-41dc-92e6-8e9ca1ed36bd",
              "entityType": "DiningOption",
              "externalId": null
          },
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.06,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": "2019-02-24T13:49:38.616+0000",
      "closedDate": "2019-02-25T11:05:00.024+0000",
      "deletedDate": "1970-01-01T00:00:00.000+0000",
      "modifiedDate": "2019-02-25T11:05:00.024+0000",
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.06,
      "appliedServiceCharges": [],
      "paymentStatus": "CLOSED",
      "customer": {[(6)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersCustomer2)
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
      }
    }
  ],
  "deleted": false,
  "paidDate": "2019-02-24T13:49:38.616+0000",
  "closedDate": "2019-02-25T11:05:00.024+0000",
  "deletedDate": "1970-01-01T00:00:00.000+0000",
  "restaurantService": {
      "guid": "9d57bbfc-c0e1-4bb0-9cec-ebcb186306bb",
      "entityType": "RestaurantService",
      "externalId": null
  },
  "modifiedDate": "2019-02-25T11:05:00.024+0000",
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": null,
  "requiredPrepTime": "PT0S",
  "table": null
}

```



(1) The /orders/{guid}endpoint returns an Order JSON object. For more information about the values in the Order object, see the orders API reference documentation.

 The deliveryInfo JSON value is only populated if your Toast API client has the delivery_info.address:readscope. For more information about scopes, see Scopes.

 The curbsidePickupInfo JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

 The receiptLinePrice JSON value is the base price of a menu item without modifiers or quantity applied.

 When creating orders, restaurant employees can select the physical seat in which a guest sits. If a seat number is specified, then the seatNumber value on a Selectionobject represents the seat number associated with the menu item selection. If the menu item selection is shared among multiple seats, then seatNumber is 0. If no seat number is associated with the menu item selection, then seatNumberis -1.

 The customer JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

#### Getting detailed information about multiple orders

You can use the orders API to retrieve details about orders that were modified or created during a specified time period.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk` endpoint. 


##### How to make the request

To retrieve the orders, you send a `GET`request to the `/ordersBulk` endpoint.

The `/ordersBulk` endpoint returns an array of `Order` objects for each order that is selected based on the specified time period.

##### Specifying the time period for the request

When you send a `GET` request to the `/ordersBulk` endpoint, you specify the period of time that you want to return orders.

To specify the time period, you use one of the following options:

- **Select the orders that were last modified during a specified time period.**

To use this option, specify dates and times in the `startDate` and `endDate` query parameters.

Order creation is considered an order modification. The request results include orders that were created during the specified time period.


- **Select the orders that were created during a single restaurant business day.**

To use this option, set the `businessDate` query parameter.

In the restaurants API, the restaurant's business day cutoff is determined by the `closeoutHour` value in the `General` object within the `RestaurantInfo`object.



Toast support recommends that you use the `startDate` and `endDate` query parameters. These parameters select orders based on the *modification* time stamp. The request returns orders that were either created or modified during that time period.

The `businessDate` query parameter selects orders based on the *creation* date. The request only returns orders that were created on that business day. It does not return orders that were modified on that business day, but created on an earlier day.

##### Paginating the request results

To control the number of `Order` objects that the `/ordersBulk` endpoint returns for each request, use the `pageSize` query parameter. The maximum `pageSize`that you can specify is 100.

If the number of matching orders is greater than the value of `pageSize`, use the `page` parameter to specify the sequence number of the set of objects to return.

For example, the time period you specify selects 100 orders. You set `pageSize` to `10`. To return the first ten orders, set `page` to `1`. To return the next ten orders, set `page` to `2`.

The response header fields for the `/ordersBulk` endpoint include a set of response pagination links that you can use to send requests that return each `Order` object in the set of orders you select in a time period. These link header fields follow the pattern described in the [proposed Internet Engineering Task Force (IETF) web linking standard](https://tools.ietf.org/html/rfc5988).

For an example of the pagination links in a `/ordersBulk`endpoint response, see [Example response data pagination header fields](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersBulkPaginationHeaderFieldsExample). For more information about Toast API response pagination, see [Paginating response data](apiResponseDataPagination.html).



> **Note**
> 
> Unlike the endpoints of the Toast configuration API, the `/ordersBulk` endpoint does not return a `last`link field.




> **Note**
> 
> The `/ordersBulk` endpoint has a lower rate limit than most other Toast API endpoints. API clients can poll the `/orderBulk` endpoint up to five times per location per second. For more information about API rate limits, see [Toast rate limit values](apiRateLimiting.html#apiToastRateLimits).


##### Example request for detailed information about multiple orders

The following example shows a request for detailed information about orders that were last modified during a period of time.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e91E21797AD-1776-4ECD-AC81-2F50EFAA6320-co)
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e93E21797AD-1776-4ECD-AC81-2F50EFAA6320-co)
"https://`[toast-api-hostname]`/orders/v2/ordersBulk?[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e98E21797AD-1776-4ECD-AC81-2F50EFAA6320-co)
startDate=2020-03-02T19:10:30.000Z&endDate=2020-03-02T22:00:00.000Z&[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e100E21797AD-1776-4ECD-AC81-2F50EFAA6320-co)
pageSize=10&page=2"[(5)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e103E21797AD-1776-4ECD-AC81-2F50EFAA6320-co)
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the GUID of the restaurant that created the orders. This must be the GUID of an individual restaurant. It cannot be the GUID of a restaurant group.

(3) Send a GET request to the /ordersBulk endpoint of the orders API.

(4) To specify a period of time to return orders for, use the startDate and endDatequery parameters.

(5) In the pageSize query parameter, specify the maximum number of objects to include in the response. In the page query parameter, specify the sequence number of the set of objects to return. For more information, see Paginating response data.

##### Example response data containing multiple orders

The following example shows the response data from the `/ordersBulk` endpoint. It contains detailed information about multiple orders.

```
[
  {
    "guid": "5274c0f8-bf61-4e37-ad04-cf4ca1326822",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e21648C855F0-89F9-4824-A080-F12BBC4F767E-co)
    "entityType": "Order",
    "externalId": null,
    "revenueCenter": null,
    "server": {
      "guid": "dc9b7cd6-4389-4a6d-83c3-2fde7f033567",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "lastModifiedDevice": {
      "id": null
    },
    "source": "API",
    "voidDate": null,
    "duration": null,
    "businessDate": 20200302,
    "paidDate": null,
    "restaurantService": null,
    "voided": false,
    "estimatedFulfillmentDate": "2020-03-03T19:55:00.000+0000",
    "table": null,
    "requiredPrepTime": "PT30M",
    "approvalStatus": "FUTURE",
    "deliveryInfo": {[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersBulkDeliveryInfo2)
      "address1": "401 Park Drive",
      "address2": "Suite 801",
      "city": "Boston",
      "state": "MA",
      "zipCode": "02215",
      "latitude": 42.3446671,
      "longitude": -71.1023575,
      "notes": ""
    },
    "serviceArea": null,
    "curbsidePickupInfo": {[(3)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersBulkCurbsideInfo2)
      "entityType": "CurbsidePickup",
      "notes": "Convertible with top down",
      "transportColor": "blue",
      "transportDescription": "Street Cruiser"
    },
    "numberOfGuests": 1,
    "diningOption": {
      "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
      "entityType": "DiningOption",
      "externalId": null
    },
    "openedDate": "2020-03-02T19:17:02.552+0000",
    "voidBusinessDate": null,
    "checks": [
      {
        "guid": "df38b30c-04b3-4eb3-923e-7cec05357674",
        "entityType": "Check",
        "externalId": null,
        "displayNumber": "pdesjardins-api-1583176621",
        "payments": [],
        "appliedDiscounts": [],
        "lastModifiedDevice": {
          "id": null
        },
        "voidDate": null,
        "paidDate": null,
        "appliedLoyaltyInfo": null,
        "voided": false,
        "paymentStatus": "OPEN",
        "amount": 111,
        "tabName": null,
        "taxExempt": false,
        "openedDate": "2020-03-02T19:17:02.552+0000",
        "totalAmount": 111,
        "selections": [
          {
            "guid": "2e917d92-04e5-4a2b-bb1a-bde41009feb3",
            "entityType": "MenuItemSelection",
            "externalId": null,
            "deferred": false,
            "preDiscountPrice": 111,
            "voidReason": null,
            "optionGroup": null,
            "displayName": "Rejected",
            "appliedDiscounts": [],
            "modifiers": [],
            "seatNumber": -1,
            "voidDate": null,
            "fulfillmentStatus": "NEW",
            "salesCategory": {
              "guid": "c0915e46-341e-4ec0-b46e-cb87fab729fd",
              "entityType": "SalesCategory",
              "externalId": null
            },
            "selectionType": "NONE",
            "price": 111,
            "voided": false,
            "appliedTaxes": [],
            "itemGroup": {
              "guid": "c639a684-7245-4259-b9c5-f913e481347e",
              "entityType": "MenuGroup",
              "externalId": null
            },
            "item": {
              "guid": "88aebc5f-4635-4141-9c0f-5a9be6324218",
              "entityType": "MenuItem",
              "externalId": null
            },
            "taxInclusion": "INCLUDED",
            "quantity": 1,
            "unitOfMeasure": "NONE",
            "tax": 0,
            "diningOption": {
              "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
              "entityType": "DiningOption",
              "externalId": null
            },
            "voidBusinessDate": null,
            "createdDate": "2020-03-02T19:17:02.583+0000",
            "preModifier": null,
            "modifiedDate": "2020-03-02T19:17:02.583+0000"
          }
        ],
        "voidBusinessDate": null,
        "deleted": false,
        "createdDevice": {
          "id": null
        },
        "closedDate": null,
        "deletedDate": null,
        "modifiedDate": "2020-03-02T19:17:02.609+0000",
        "taxAmount": 0,
        "appliedServiceCharges": [],
        "customer": {[(4)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#apiOrdersBulkCustomer2)
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
         }
      }
    ],
    "deleted": false,
    "createdDevice": {
      "id": null
    },
    "closedDate": null,
    "deletedDate": null,
    "modifiedDate": "2020-03-02T19:17:02.612+0000",
    "promisedDate": "2020-03-03T19:55:00.000+0000",
    "pricingFeatures": [
      "TAXESV2"
    ]
  },
  {
    "guid": "529d9853-e28a-482b-9ee7-41580b0a53d0",[(5)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e21848C855F0-89F9-4824-A080-F12BBC4F767E-co)
    "entityType": "Order",

    `[contents omitted]`

  },
  {
    "guid": "c3f0c5bd-3b06-4b5d-8035-be57ae38a02a",
    "entityType": "Order",

    `[contents omitted]`

  }
]
```



(1) The first Order object in the array provides detailed information about a single order.

 The deliveryInfo JSON value is only populated if your Toast API client has the delivery_info.address:readscope. For more information about scopes, see Scopes.

 The curbsidePickupInfo JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

 The customer JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

(5) Each subsequent Order object in the array provides detailed information about a different order.

##### Example response data pagination header fields

The following example shows the header fields that provide response data pagination URLs for the `/ordersBulk` endpoint. For more information, see [Paginating response data](apiResponseDataPagination.html).

```
link: <https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &startDate=2020-03-30T20%3A00%3A00.000Z&pageSize=1>; rel="first"
link: <https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &startDate=2020-03-30T20%3A00%3A00.000Z&pageSize=1&page=3>; rel="self"
link: <https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &pageSize=1&page=2&startDate=2020-03-30T20%3A00%3A00.000Z>; rel="prev"
link: <https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &pageSize=1&page=4&startDate=2020-03-30T20%3A00%3A00.000Z>; rel="next"
```

#### Calculating net sales using the orders API

The reports in Toast Web include net sales values. You can also use [amount values from the orders API](apiOrdersOmitChunkFromSearchIndex.html#apiOrderObjectAmounts) to calculate the net sales.

##### Orders API information to include in net sales



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


A typical definition of net sales is the total price paid by guests for menu item selections and services.

Your integration can calculate net sales from orders API information by including:

- Prices of the menu item selections.


- Discounts that were deducted from menu item selections and checks.


- Non-gratuity service charges that were added to checks.



A typical calculation of net sales using orders API information does not include:

- Taxes or other amounts that are paid to other entities, such as gratuity service charges and credit card tips.


- Voided menu item selections, checks, and orders.


- Deleted checks and orders.


- Purchases of gift cards or house account payments.



Include the orders API information for any orders and checks *that are not excluded* in the list above. For example, include open and unpaid orders in the net sales calculation for your integration.

##### How to calculate net sales from orders API information



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


Here is an overview of the process to calculate net sales for a group of orders using information from the orders API:

1. Use the [Get multiple orders](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/) request to retrieve the orders that were opened during the period of time that you want to do the calculation for.


2. [Calculate the net sales values for each order](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersNetSalesSingleOrder).


3. Sum the order net sales values to get the total net sales.



During the calculation:

- Exclude orders and checks where `voided` is `true`.


- Exclude orders and checks where `deleted` is `true`.



**Procedure 2.1. To calculate net sales for an order**

1. Within a check, calculate the net sales amount for each menu item selection.

Exclude the following menu item selections:

- Menu item selections where `voided` is `true`.


- Menu item selections where `displayName` is `Gift Card`.



For the applicable menu item selections:

1. Get the `preDiscountPrice` value for the menu item selection.


2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.




  1. Get the `preDiscountPrice` value for the menu item selection.


  2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.


2. Sum the net sales amounts for the menu item selections in a check. This is the initial check net sales value.


3. Add the non-gratuity service charge amounts to the check net sales value.

1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


2. Add that total to the check net sales value.




  1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


  2. Add that total to the check net sales value.


4. Subtract check-level discounts from the check net sales value.

1. In the check, sum `Discount.nonTaxableDiscountAmount`.


2. Subtract that total from the check net sales value.




  1. In the check, sum `Discount.nonTaxableDiscountAmount`.


  2. Subtract that total from the check net sales value.


5. Sum the check net sales values for the checks in the order.



#### Marketplace facilitator tax information

For orders submitted by a marketplace facilitator, the prices and tax amounts are either populated by the Toast platform, or provided by the marketplace facilitator.

##### About marketplace facilitators

For Toast platform restaurants, a marketplace facilitator is a business that:

- Takes guest orders, processes guest payments, and then directly submits those orders to a Toast platform restaurant for fulfillment.


- Is required by a taxing authority to pay tax amounts for the orders they process.



For example, a restaurant ordering service such as Grubhub™, Uber Eats™, or Doordash® accepts orders for a large number of restaurants. The service might take guest orders and payments and then submit the order to the Toast platform for fulfillment at a Toast platform restaurant. The ordering service receives the guest payment and then remits the applicable tax amounts.

For Toast Takeout and Toast Local orders, Toast acts as the marketplace facilitator and remits tax amounts on behalf of the restaurant. In these cases, Toast pays the tax amounts for the orders.

For more information about marketplace facilitator orders in the Toast platform, see [Marketplace facilitator tax payments](adminMarketplaceFacilitatorTaxPayments.html).

##### Indicating the source of prices and tax amounts

The orders API return data indicates whether the prices and tax amounts were populated by the Toast platform, or specified by the marketplace facilitator. It also indicates whether the marketplace facilitator collected and remitted the taxes on behalf of the restaurant.

In the `appliedTaxes` object, the `type` value indicates whether the value came from the Toast platform or was calculated by the marketplace facilitator:

- If `type` is `EXTERNAL`, then the prices and tax amounts were provided by the marketplace facilitator. The prices should match the current menu prices for the restaurant. The tax amounts are usually calculated by a tax partner.


- If `type` is any value other than `EXTERNAL`, then the prices and tax amounts were calculated by the Toast platform.



The `facilitatorCollectAndRemitTax` value indicates whether the marketplace facilitator remitted the tax on behalf of the restaurant. If set to `true`, then the marketplace facilitator remitted the tax.

###### Reviewing marketplace facilitator tax calculations

To review the tax calculation for a marketplace facilitator, refer to the `AppliedTaxRate` object. This object contains the following details:

- `entityType`: The type of object.


- `name`: The name of the tax rate. For marketplace facilitator taxes, this field is always Toast Marketplace Facilitator Taxes.


- `rate`: The tax rate. This value can be a fixed amount, percentage or `null`.


- `taxAmount`: The tax amount applied.


- `type`: The tax rate type. Possible tax types for marketplace facilitators are: 

- FIXED: The tax rate is a fixed amount that is calculated by a third-party provider.


- EXTERNAL: The tax is for a marketplace facilitator order, and the marketplace facilitator organization, such as a third-party ordering platform, calculated the tax amount.




- `displayName`:The name of the tax rate as it appears on guest receipts.


- `jurisdiction`: The area the tax rate applies to, such as a state or province, for reporting purposes.


- `facilitatorCollectAndRemitTax`: Indicates whether the marketplace facilitator remitted the tax amount on behalf of the restaurant. If set to `true`, the marketplace facilitator remitted the tax. If set to `false` or `null`, the marketplace facilitator did not remit the tax.



###### Calculating total marketplace facilitator tax paid

To calculate the total marketplace facilitator tax amount that was remitted on behalf of a restaurant for an order, sum the `taxAmount` values from all `AppliedTaxRate`objects where `facilitatorCollectAndRemitTax` is `true`.

You need to check all `AppliedTaxRate` objects in the order, which can be found in:

- The `appliedTaxes` array on each `MenuItemSelection` object in each check.


- The `appliedTaxes` array on each `AppliedServiceCharge` object, if service charges are present.



For example, to calculate the total marketplace facilitator tax paid for an order:

1. Iterate through all checks in the order.


2. For each check, iterate through all menu item selections and service charges.


3. For each `AppliedTaxRate` object where `facilitatorCollectAndRemitTax` is `true`, add the `taxAmount` value to your total.





> **Note**
> 
> For some Toast Takeout and Toast Local orders, Toast remits the tax amounts on behalf of the restaurant. In these cases, the `facilitatorCollectAndRemitTax` value will be `true` for taxes that Toast remitted.


The following example shows how to identify marketplace facilitator taxes that were remitted:

```
{
  "checks": [
    {
      "selections": [
        {
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "name": "State Tax",
              "taxAmount": 0.31,
              "facilitatorCollectAndRemitTax": true
            },
            {
              "entityType": "AppliedTaxRate",
              "name": "Local Tax",
              "taxAmount": 0.15,
              "facilitatorCollectAndRemitTax": true
            }
          ]
        }
      ]
    }
  ]
}
```

In this example, the total marketplace facilitator tax paid would be `0.46` (the sum of `taxAmount` values where `facilitatorCollectAndRemitTax` is `true`). 

##### Example return data with Toast platform prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the Toast platform calculated and populated the prices and tax amounts.

```
{
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",

     [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "26aa5680-3233-4d3b-9504-051a622ae76d",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "rate": 0.0625,
              "name": "State Tax",
              "taxAmount": 0.31,
              "type": "PERCENT",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e31CC34B3B2-D5E8-41EC-A472-B380E595E5A4-co)
              "facilitatorCollectAndRemitTax": true[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e33CC34B3B2-D5E8-41EC-A472-B380E595E5A4-co)
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },

          [contents omitted]

          "receiptLinePrice": 5,
          "tax": 0.31,

          [contents omitted]

        }
      ],

      [contents omitted]

      "taxAmount": 0.31,

      [contents omitted]

   }
  ],

  [contents omitted]

}
```



(1) Any value other thanEXTERNALindicates that the marketplace facilitator used the prices and tax amounts calculated by the Toast platform for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

##### Example return data with specified prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the marketplace facilitator specifies the prices and tax amounts.

The prices should correspond to the prices from the restaurant menu. The tax amounts are usually calculated by a tax partner.

The marketplace facilitator submits those prices and tax amounts to the Toast platform.

```
{
  "guid": "cdef26f4-68bd-42a1-a1e0-be43c4fb52f0",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",
 
      [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "688cdc21-ab92-427e-9837-c981cc2d55c5",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "a19eaf97-c0b9-47bf-9af2-ed833c3e4051",
                "entityType": "TaxRate"
              },
              "rate": null,
              "name": "Marketplace Facilitator Taxes Paid",
              "taxAmount": 0.1,
              "type": "EXTERNAL",[(1)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e47CC34B3B2-D5E8-41EC-A472-B380E595E5A4-co)
              "facilitatorCollectAndRemitTax": true[(2)](apiDevGuide-apiOrdersOmitChunkFromSearchIndex.html#d1e49CC34B3B2-D5E8-41EC-A472-B380E595E5A4-co)
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },
 
          [contents omitted]

          "receiptLinePrice": 20,

          [contents omitted]

        }
      ],

     [contents omitted]

      "taxAmount": 0.1,

     [contents omitted]

    }
  ],

  [contents omitted]

}
```



(1) The value EXTERNAL indicates that the marketplace facilitator specified the prices and tax amounts for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

#### Finding an order or check GUID

The following sections detail multiple methods for locating either an order GUID or a check GUID.

##### How to locate an order GUID

- If you have created an order using the orders API, the response from the `POST` request contains the order GUID. For more information about creating orders see [Creating orders](portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.html#apiCreatingOrders).


- Send a `GET` request to the `/ordersBulk` endpoint and retrieve the details for orders updated during a specific time interval. The order details include the order GUID. See [Getting detailed information about multiple orders](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutMultipleOrders) for more information on using the `/ordersBulk` endpoint.


- Locate the order in Toast Web using the Orders report from Reports > Sales > Orders. Use the View filter, at the top of the report, to help locate your order. Once located, select the order, and the GUID is displayed as seen below.

![Shows the Order Details page with the order GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_order_guid.png)



##### How to locate a check GUID

- If you know the order GUID, you can send a `GET`request to the `/orders` endpoint and retrieve the order details, which include the check GUID. See [Getting detailed information about one order](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).


- Locate the order in Toast Web using the Orders report from Reports > Sales > Orders. Use the date selector to locate your order. Once located, select the order, and find the check. The GUID is displayed as seen below.

![Shows the Order Details page with the check GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_check_guid.png)



#### Daily order for tracking excess food

The orders API returns a daily *excess food order*for restaurants that use the Toast platform's waste tracking feature. An excess food order, also referred to as a waste order, is a special type of order created in the Toast platform to track excess food in a restaurant. Like guest orders, excess food orders may contain menu items, modifiers, or both.

Currently, the Toast platform creates one excess food order per day at each restaurant using the waste tracking feature. The Toast platform creates the daily excess food order the first time a restaurant employee uses the waste tracking feature to identify excess food. If restaurant employees identify additional excess food over the course of the business day, that excess food is added to the daily excess food order. If no excess food is identified on a given day, no excess food order is created for that day.

The orders API indicates that an order is an excess food order using the `excessFood` value on the [Order](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/)object. Excess food orders are structurally the same as standard guest orders. However, certain behavior is applied to these orders automatically by the waste tracking feature:

- The `excessFood` field is set to `true`.


- Exactly one check is created on each excess food order.


- Each selection on the check is discounted to $0 using an item-level 100% discount. This discount is created automatically by the Toast platform and has the name `Waste`.


- If the restaurant has configured waste reasons and the employee identifying the waste selects one of those reasons when tracking the item in the POS, that reason is applied to the discounted selection. Note that waste reasons are not returned in orders API responses.



Because all selections on the check are discounted, the `price` value on each selection and the `amount` value of the check is always $0. The `preDiscountPrice` value on each selection, however, reflects the retail value of each selection. If you use the `preDiscountPrice` field in order to report on gross sales, you might want to exclude excess food orders from this calculation.

