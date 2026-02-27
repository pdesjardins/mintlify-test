---
title: "Building a CRM & Guest Engagement integration"
id: apiHowToBuildACrmGuestEngagementIntegration
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiIntegrationChecklistInventory.md
previousSectionTitle: "Building an inventory tracking integration"
nextSectionFile: devCookbook-cookbookReservationsOmitChunkFromSearchIndex.md
nextSectionTitle: "Reservations"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/menus/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/operation/discountsGet/https://doc.toasttab.com/openapi/configuration/operation/discountsGet/, https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/, https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/, https://doc.toasttab.com/openapi/labor/overview/, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/]
excerpt: "Follow the steps below to build a CRM & Guest Engagement integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a CRM & Guest Engagement integration with the Toast platform.

This integration allows you to provide a CRM solution using order history.

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `config:read`


- `labor:read`


- `labor.employees:read`


- `menus:read`


- `orders:read`


- `restaurants:read`


- `guest.pi:read`


- `delivery_info.address:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDevGuide-apiDeveloperPortal#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](apiDevGuide-integrationDevProcess)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Learn order structure concepts

To familiarize yourself with the structure of an order, read the [Orders API overview](apiDevGuide-portalOrdersApiOverview) and the [Order object summary](apiDevGuide-apiOrdersOrderObjectSummary). For more information about the orders API, see the [reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

The guest's first and last name, email address, and phone number are found in the `Customer` object of the orders API.

### Learn menu hierarchy concepts

To familiarize yourself with menu structure, read the [menu hierarchy documentation](adminGuide-adminMenuHierarchy).

Use the [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve a full menu from a Toast POS location so that you understand the menu structure.

### Retrieve configuration information

Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve the configuration information you will need to properly understand order information. Configuration options you may need include:

- [Dining options](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)


- [Discounts](https://doc.toasttab.com/openapi/configuration/operation/discountsGet/https://doc.toasttab.com/openapi/configuration/operation/discountsGet/)


- [Revenue centers](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/)


- [Service charges](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)



### Understanding available customer data

All Toast orders contain a [dining option](adminGuide-adminDiningOptions) with defined behavior. When polling for Toast orders, the `Customer`object will only appear in orders where the `diningOption`behavior is `TAKE_OUT` or `DELIVERY`. You can understand `diningOption` behavior by polling the `/diningOptions` endpoint of the configuration API. Your integration should consume orders where the diningOption behavior is either `TAKE_OUT` or `DELIVERY`.

For more information about the `/diningOptions`endpoint of the configuration API, see the [reference documentation](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/).

### Determine if your integration will include employee data

If your integration tracks the servers who have previously worked with a certain customer, you will need to use the labor API to retrieve relevant server information. To get information about all employees, make a `GET` request to the `/employees` endpoint of the labor API.

For more information about the labor API, see the r[eference documentation](https://doc.toasttab.com/openapi/labor/overview/).

### Consider a historical backfill

When a restaurant first connects to your integration, they may expect to see some historical information already displayed in your system.

Define how many days of historical cash transactions you retrieve when a restaurant first connects to your integration.

Toast support recommends that you retrieve twelve weeks of historical data when a restaurant first connects to your integration. Requests to the `/ordersBulk` endpoint for historical data using the `startDate` and `endDate` query parameters must not exceed intervals greater than one month with calls spaced at least 5-10 seconds apart.

## Handling Orders

### Retrieving orders from the orders API

To report on order information, use the [orders updated webhook](apiDevGuide-devOrdersWebhookRef) to receive order updates as they occur.



> **Note**
> 
> You can also use the /ordersBulk [endpoint](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)of the orders API to retrieve orders using the startDate and endDate parameters.


### Understand relevant data from the orders API

#### Understand customer information

The `Customer` object in the orders API includes the name, email address, and phone number of the guest who placed the order.



> **Note**
> 
> The `Customer` object will be `null` for in-store orders


The deliveryInfo object contains the delivery address and delivery notes.

#### Understand menu item information

The `Selections` object within the `Checks` object in the order response contains an `Item` object. Make a `GET` request to the `/menus` endpoint of the menus API to see relevant information for the item in the check.

#### Understand employee information

To get information about the employee associated with an order, you will need to map the `guid` in the `Server`object in the orders API response to the employees configured for the location. Make a `GET` request to the `/employees` endpoint of the labor API to see employee information.

## Building CRM Functionality

When creating your integration functionality, consider tracking the following information as it relates to the customer.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Object</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Values</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">Orders</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for orders:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Dining option name</p></li><li className=""><p className="text-base leading-relaxed">Dining option behavior</p></li><li className=""><p className="text-base leading-relaxed">Revenue center name</p></li><li className=""><p className="text-base leading-relaxed">Server name</p></li><li className=""><p className="text-base leading-relaxed">Service area name</p></li><li className=""><p className="text-base leading-relaxed">Table name</p></li><li className=""><p className="text-base leading-relaxed">Number of guests</p></li><li className=""><p className="text-base leading-relaxed">Order source</p></li><li className=""><p className="text-base leading-relaxed">Restaurant service name</p></li><li className=""><p className="text-base leading-relaxed">Opened date</p></li><li className=""><p className="text-base leading-relaxed">Modified date</p></li><li className=""><p className="text-base leading-relaxed">Paid date</p></li><li className=""><p className="text-base leading-relaxed">Business Date</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">Checks</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for checks:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Display number</p></li><li className=""><p className="text-base leading-relaxed">Delivery information</p></li><li className=""><p className="text-base leading-relaxed">Customer information</p></li><li className=""><p className="text-base leading-relaxed">Tab name</p></li><li className=""><p className="text-base leading-relaxed">Total amount</p></li><li className=""><p className="text-base leading-relaxed">Tax amount</p></li><li className=""><p className="text-base leading-relaxed">Refunded amount</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li><li className=""><p className="text-base leading-relaxed">Applied service charge names</p></li><li className=""><p className="text-base leading-relaxed">Applied service charge amounts</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">Selections</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for menu item selections:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Menu item name - use the <code className="font-mono text-sm">displayName</code> value on <code className="font-mono text-sm">Selection</code> object</p></li><li className=""><p className="text-base leading-relaxed">Item quantity</p></li><li className=""><p className="text-base leading-relaxed">Item group</p></li><li className=""><p className="text-base leading-relaxed">Applied modifier names- Modifiers may be nested arbitrarily deep on a menu item</p></li><li className=""><p className="text-base leading-relaxed">Price</p></li><li className=""><p className="text-base leading-relaxed">Applied tax values</p></li><li className=""><p className="text-base leading-relaxed">Applied discount names</p></li><li className=""><p className="text-base leading-relaxed">Applied discount amounts</p></li><li className=""><p className="text-base leading-relaxed">Sales category name</p></li><li className=""><p className="text-base leading-relaxed">Item tags</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">Payments</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Consider displaying the following reporting information for payments:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Amount</p></li><li className=""><p className="text-base leading-relaxed">Tip amount</p></li><li className=""><p className="text-base leading-relaxed">Refund information</p></li><li className=""><p className="text-base leading-relaxed">Payment type</p></li><li className=""><p className="text-base leading-relaxed">Card type</p></li><li className=""><p className="text-base leading-relaxed">Card entry mode</p></li><li className=""><p className="text-base leading-relaxed">Payment status</p></li><li className=""><p className="text-base leading-relaxed">Voided status</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

