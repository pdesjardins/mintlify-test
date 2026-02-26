---
title: "Order object summary"
id: apiOrdersOrderObjectSummary
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-portalOrdersApiOverview.md
previousSectionTitle: "Orders API overview"
nextSectionFile: apiDevGuide-apiOrdersFirstOrder.md
nextSectionTitle: "Submitting your first order to the orders API"
excerpt: "An..."
keywords: ["Order"]
procedures: 0
codeExamples: 0
---

An `Order` object contains details about an order. In the orders API, you use the `Order` object to create orders, update orders, and retrieve information about orders. You send `Order`objects in requests to create and update orders. The orders API returns `Order` objects in response to requests.

This topic discusses some related sets of values in the `Order` object and how they are populated.

## Overview of Order object content

An `Order` object contains details about:

- What the guest ordered


- How the order is prepared and processed


- How the guest receives the order


- What the guest is charged for the order


- How the guest pays for the order



The following diagram provides a high-level overview of the `Order` object contents:

![Image](https://doc.toasttab.com/doc/media/order-api-order-object-overview.png)

## GUIDs and identifiers in the order object

A GUID is a unique identifier that Toast generates when new objects are created.

You use GUIDs to identify configured objects that are relevant to the order, such as menu items, dining options, and discounts. Here is an example of a `DiningOption` object, which provides a dining option GUID to identify the dining option for an order.


```
"diningOption": {
  "guid": "18855a26-40d4-4a8f-b484-c6af211dd597"
},
```

To identify an object, you can use either `guid` or `multilocationId`. For more information about `multilocationId` and how to use it, see [Using multi-location IDs in orders](apiDevGuide-apiUsingMultiLocationIdsInOrders).

When you create an order, the Toast platform generates GUIDs for the `Order` object, `Check` objects, and `Selection` objects. These GUIDs are returned in orders API responses.

You use those GUIDs to identify an order, check, or menu item selection to retrieve or to modify.

## Order status information

In the `Order` object, the status information reflects the current status of the order, check, or menu item selection. Statuses can reflect the current status of fulfillment or payment.

Status information is returned in responses.

In most cases, the Toast platform updates the status values based on actions to an item, check, or order.

### Order status values

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





### Check status values

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





### Menu item selection status values

A menu item selection can have the following status values:



**`fulfillmentStatus`**
: The status of the preparation of the menu item selection. The `fulfillmentStatus` indicates whether the kitchen is currently working to prepare the item.

`NEW` menu item selections were added to a check but are not sent to the KDS for preparation.

`HOLD` menu item selections were paused by a restaurant employee. They are not sent to the KDS for preparation.

`SENT` menu item selections were fired and appear in the KDS for preparation.

`READY` menu item selections have completed preparation. They are fulfilled and do not appear on the KDS. The `READY` status is only used If your restaurant uses the Toast platform KDS.





## Order dates and times

In the `Order` object, the order, checks, and menu item selections have multiple dates and times associated with them. The dates and times track events related to the order placement and processing, including when the order entities are created, updated, completed, and paid for.

Many order-related dates and times are set by the Toast platform based on the creation or modification of an order entity. For example, when an order is created, the Toast platform sets the `createdDate`. Or when an order is voided, the Toast platform sets the `voidDate`. You do not set those dates, but you do see those dates when you retrieve order details.

The following timestamps are associated with orders, checks, and menu item selections.

### Order creation and scheduling dates

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





### Order fulfillment, payment, and delivery

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





### Order changes, deletions, and voids

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





## Order amounts

The order amount values determine the amount that guests are charged. Amount values are associated with menu item selections and checks.

For most of the amount values in the `Order` object, the Toast platform either retrieves the amount from the restaurant configuration, or uses an algorithm to calculate it based on other values. For example, prices for menu selection items are configured. Amounts such as taxes and check totals are calculated.

### Components of order amounts

Order amounts include the following components:



****Menu item prices****
: The prices of the selected menu items.

For most items, prices are specified in the menu configuration.

Some items are open price items, which means that you provide the price when you create the order.

For more information, see the [menu pricing section](adminGuide-adminPricingStrategiesOverview) of the *Platform Guide*.



****Taxes****
: The tax charged for the menu selection items.

Taxes are calculated based on the applicable taxes and tax rates.

For more information on taxes and tax rates, see the [taxes section](adminGuide-adminTaxesOverview) of the *Platform Guide*.



****Service charges****
: The service charges that are added to checks.

On the Toast platform, some service charges are added automatically based on the order type. Other service charges can be added by the restaurant employee. In the orders API, all service charges must be included in the order request. Service charges are never applied automatically to orders from the orders API.

Service charges might also be taxable.

For more information on service charges, see the [service charges section](adminGuide-adminServiceChargeOverview) in the *Platform Guide*.



****Discounts****
: The applicable discounts that reduce the amount of a check or a menu item selection.

For more information on configuring discounts, see [Managing discounts](adminGuide-adminAvailableDiscounts) in the *Platform Guide*.





### Amounts on menu item selections

A menu item selection has the following amounts associated with it.



**`receiptLinePrice`**
: The price of a menu item selection before the quantity, taxes, discounts, and modifier option adjustments are applied. For items that use size pricing, `receiptLinePrice` is the price of the selected size.

For example, if the menu item selection is for two orders of fries, `receiptLinePrice` is the price of one order of fries. If a menu item selection is for three large drinks, `receiptLinePrice` is the price of one large drink.

Populated based on the menu configuration, or using the value provided in `externalPriceAmount` or `openPriceAmount`.



**`externalPriceAmount`**
: Only used in orders that are created by marketplace facilitator organizations. Provided with new orders. Not returned for existing orders.

The price of the menu item selection as calculated by the marketplace facilitator. This is the price before the quantity, taxes, discounts, and modifier option adjustments are applied.

For more information about marketplace facilitator orders, see [Marketplace facilitator orders](apiDevGuide-apiMarketplaceFacilitatorOrders).

Used to populate `receiptLinePrice`.



**`openPriceAmount`**
: Provided with new orders for open price menu items. Not returned for existing orders.

The price of the menu item selection before the quantity, taxes, discounts, and modifier option adjustments are applied.

Used to populate `receiptLinePrice`.



**`preDiscountPrice`**
: Gross sales price for the item before tax and discounts. Reflects the ordered quantity.

`prediscountPrice = receiptLinePrice x quantity`



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

`price = preDiscountPrice - sum(Discount.discountAmount)`



**`AppliedTax.taxAmount`**
: The tax amount for a specific tax. Calculated by the Toast platform based on the specific tax configuration.



**`tax`**
: The total tax on the menu item selection.

`tax = sum(AppliedTax.taxAmount)`





### Amounts on checks

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

`amount = sum(Item.price) + sum(Service charge.filter(gratutity=false).chargeamount)`



**`taxAmount`**
: The total tax on the check. Includes the taxes on the menu item selections and service charges.

`taxAmount = sum(Item.tax) + sum(Service Charge.Applied Tax.taxAmount)`



**`totalAmount`**
: The total amount of the check. `totalAmount`includes discounts, service charges, and taxes.

`totalAmount = amount + taxAmount`

`totalAmount` is not affected by refunds. Refund information is provided in the menu item selection and payment details.

`totalAmount` is affected by voids. When you void a menu item selection, `totalAmount` is reduced by the amount charged for the menu item selection.





### Example order with order amounts

To demonstrate the item and check amounts, we'll use a simple example order.

The order contains a single menu item selection for two grilled cheese sandwiches. A grilled cheese sandwich costs $8.00.

The guest receives a $1.00 discount on the item.

The item is subject to a 5% state tax and a 4% city tax.

The check has a $3.00 delivery service charge that is not taxed.

For the menu item selection, the amounts are as follows:


<table>
  <thead>
    <tr>
      <th>Amount</th>
      <th>Value</th>
      <th>Calculation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`receiptLinePrice`</td>
      <td>8.0</td>
      <td>In the menu, a grilled sandwich costs $8.00</td>
    </tr>
    <tr>
      <td>`preDiscountPrice`</td>
      <td>16.0</td>
      <td>Multiply `receiptLinePrice` (8.0) by `quantity` (2).</td>
    </tr>
    <tr>
      <td>`Discount.discountAmount`</td>
      <td>1.0</td>
      <td>The applied discount is for $1.00.</td>
    </tr>
    <tr>
      <td>`Discount.nonTaxDiscountAmount`</td>
      <td>1.0</td>
      <td>The applied discount is for $1.00. The tax is not included in the price, and the discount is a fixed amount discount, so the two discount amount values are the same.</td>
    </tr>
    <tr>
      <td>`price`</td>
      <td>15.0</td>
      <td>Subtract the total `discountAmount` (1.0) from the `preDiscountPrice` (16.0).</td>
    </tr>
    <tr>
      <td>`AppliedTax.taxAmount` (State tax)</td>
      <td>0.75</td>
      <td>Multiply the `rate` for the state tax (.05) by the `price` (15.0).</td>
    </tr>
    <tr>
      <td>`AppliedTax.taxAmount` (City tax)</td>
      <td>0.65</td>
      <td>Multiply the `rate` for the city tax (.04) by the `price` (15.0).</td>
    </tr>
    <tr>
      <td>`tax`</td>
      <td>1.35</td>
      <td>Add the `taxAmount` values (0.75 and 0.65).</td>
    </tr>
  </tbody>
</table>

For the check, the amounts are as follows:


<table>
  <thead>
    <tr>
      <th>Amount</th>
      <th>Value</th>
      <th>Calculation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`appliedDiscounts`</td>
      <td>No values</td>
      <td>There are no discounts on the check, just on the item.</td>
    </tr>
    <tr>
      <td>`ServiceCharge.chargeAmount`</td>
      <td>3.0</td>
      <td>There is a $3.00 delivery charge.</td>
    </tr>
    <tr>
      <td>`ServiceCharge.appliedTaxes`</td>
      <td>No values</td>
      <td>The delivery charge is not taxed.</td>
    </tr>
    <tr>
      <td>`amount`</td>
      <td>18.0</td>
      <td>Add the `price` from the menu selection item (15.0) to the service charge (3.0).</td>
    </tr>
    <tr>
      <td>`taxAmount`</td>
      <td>1.35</td>
      <td>The total of the `tax` values on the menu selection items. The `tax` value for the single menu selection item is 1.35.</td>
    </tr>
    <tr>
      <td>`totalAmount`</td>
      <td>19.35</td>
      <td>Add `amount` (18.0) and `taxAmount` (1.35).</td>
    </tr>
  </tbody>
</table>

