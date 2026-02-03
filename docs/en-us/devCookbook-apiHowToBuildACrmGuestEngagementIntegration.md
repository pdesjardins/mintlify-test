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

#### Required scopes

To follow these instructions, you must have the following [scopes](apiScopes.html):

- `config:read`


- `labor:read`


- `labor.employees:read`


- `menus:read`


- `orders:read`


- `restaurants:read`


- `guest.pi:read`


- `delivery_info.address:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDeveloperPortal.html#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](integrationDevProcess.html)guide for instructions on requesting access.

#### Setup and planning

##### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](apiIntegrationChecklistGeneral.html).

##### Learn order structure concepts

To familiarize yourself with the structure of an order, read the [Orders API overview](portalOrdersApiOverview.html) and the [Order object summary](apiOrdersOrderObjectSummary.html). For more information about the orders API, see the [reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

The guest's first and last name, email address, and phone number are found in the `Customer` object of the orders API.

##### Learn menu hierarchy concepts

To familiarize yourself with menu structure, read the [menu hierarchy documentation](adminMenuHierarchy.html).

Use the [menus API](https://doc.toasttab.com/openapi/menus/overview/) to retrieve a full menu from a Toast POS location so that you understand the menu structure.

##### Retrieve configuration information

Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve the configuration information you will need to properly understand order information. Configuration options you may need include:

- [Dining options](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)


- [Discounts](https://doc.toasttab.com/openapi/configuration/operation/discountsGet/https://doc.toasttab.com/openapi/configuration/operation/discountsGet/)


- [Revenue centers](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/)


- [Service charges](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)



##### Understanding available customer data

All Toast orders contain a [dining option](adminDiningOptions.html) with defined behavior. When polling for Toast orders, the `Customer`object will only appear in orders where the `diningOption`behavior is `TAKE_OUT` or `DELIVERY`. You can understand `diningOption` behavior by polling the `/diningOptions` endpoint of the configuration API. Your integration should consume orders where the diningOption behavior is either `TAKE_OUT` or `DELIVERY`.

For more information about the `/diningOptions`endpoint of the configuration API, see the [reference documentation](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/).

##### Determine if your integration will include employee data

If your integration tracks the servers who have previously worked with a certain customer, you will need to use the labor API to retrieve relevant server information. To get information about all employees, make a `GET` request to the `/employees` endpoint of the labor API.

For more information about the labor API, see the r[eference documentation](https://doc.toasttab.com/openapi/labor/overview/).

##### Consider a historical backfill

When a restaurant first connects to your integration, they may expect to see some historical information already displayed in your system.

Define how many days of historical cash transactions you retrieve when a restaurant first connects to your integration.

Toast support recommends that you retrieve twelve weeks of historical data when a restaurant first connects to your integration. Requests to the `/ordersBulk` endpoint for historical data using the `startDate` and `endDate` query parameters must not exceed intervals greater than one month with calls spaced at least 5-10 seconds apart.

#### Handling Orders

##### Retrieving orders from the orders API

To report on order information, use the [orders updated webhook](devOrdersWebhookRef.html) to receive order updates as they occur.



> **Note**
> 
> You can also use the /ordersBulk [endpoint](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)of the orders API to retrieve orders using the startDate and endDate parameters.


##### Understand relevant data from the orders API

###### Understand customer information

The `Customer` object in the orders API includes the name, email address, and phone number of the guest who placed the order.



> **Note**
> 
> The `Customer` object will be `null` for in-store orders


The deliveryInfo object contains the delivery address and delivery notes.

###### Understand menu item information

The `Selections` object within the `Checks` object in the order response contains an `Item` object. Make a `GET` request to the `/menus` endpoint of the menus API to see relevant information for the item in the check.

###### Understand employee information

To get information about the employee associated with an order, you will need to map the `guid` in the `Server`object in the orders API response to the employees configured for the location. Make a `GET` request to the `/employees` endpoint of the labor API to see employee information.

#### Building CRM Functionality

When creating your integration functionality, consider tracking the following information as it relates to the customer.

| Object | Values | 
| --- | --- |
| Orders | Consider displaying the following reporting information for orders:- Dining option name
- Dining option behavior
- Revenue center name
- Server name
- Service area name
- Table name
- Number of guests
- Order source
- Restaurant service name
- Opened date
- Modified date
- Paid date
- Business Date
- Voided status

 | 
| Checks | Consider displaying the following reporting information for checks:- Display number
- Delivery information
- Customer information
- Tab name
- Total amount
- Tax amount
- Refunded amount
- Applied discount names
- Applied discount amounts
- Applied service charge names
- Applied service charge amounts
- Voided status

 | 
| Selections | Consider displaying the following reporting information for menu item selections:- Menu item name - use the `displayName`value on `Selection` object
- Item quantity
- Item group
- Applied modifier names- Modifiers may be nested arbitrarily deep on a menu item
- Price
- Applied tax values
- Applied discount names
- Applied discount amounts
- Sales category name
- Item tags
- Voided status

 | 
| Payments | Consider displaying the following reporting information for payments:- Amount
- Tip amount
- Refund information
- Payment type
- Card type
- Card entry mode
- Payment status
- Voided status

 | 

