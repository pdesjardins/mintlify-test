---
title: "Building a reservation integration"
id: apiIntegrationChecklistReservation
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookReservationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reservations"
previousSectionFile: devCookbook-cookbookReservationsOmitChunkFromSearchIndex.md
previousSectionTitle: "Reservations"
nextSectionFile: devCookbook-cookbookSecurityOmitChunkFromSearchIndex.md
nextSectionTitle: "Security"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/, https://doc.toasttab.com/openapi/orders/operation/ordersPost/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/, https://doc.toasttab.com/openapi/configuration/operation/tablesGet/, https://central.toasttab.com/s/article/Setting-Up-Other-Payment-Options, https://doc.toasttab.com/openapi/labor/operation/employeesGet/, https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=diningOption&t=response, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=numberOfGuests&t=response, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=closedDate&t=response, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=table&t=response, https://doc.toasttab.com/openapi/menus/operation/menusGet/]
excerpt: "Follow the steps below to build a reservation integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a reservation integration with the Toast platform.

This integration allows you to let guests place reservations at Toast restaurants, and provides restaurants with reporting on guest ordering preferences and order analytics.

In this guide, references to submitting reservation information to the Toast platform means using the Toast orders API to send reservation-specific details. Toast does not have a reservation API. Submitting reservation information to the Toast platform is done by submitting an order that only includes the information specific to the reservation. This approach enables your integration to share reservation information effectively and maintain consistency between your system and the Toast platform.

## Required scopes

To follow these instructions, you must have the following scopes:

- `config:read`


- `labor:read` (this is optional. For more information, see [Determine what optional functionality you will support](devCookbook-apiIntegrationChecklistReservation#reservationIntegWriteOptional))


- `labor.employees:read` (this is optional. For more information, see [Determine what optional functionality you will support](devCookbook-apiIntegrationChecklistReservation#reservationIntegWriteOptional))


- `menus:read`


- `orders.channel:read`


- `orders:read`


- `orders.orders:write` (for read-write integration only. For more information, see [Building a read-write reservation integration](devCookbook-apiIntegrationChecklistReservation#reservationIntegWrite))


- `restaurants:read`



You can retrieve a list of your current scopes through your [Toast developer portal](apiDevGuide-apiDeveloperPortal#apiDeveloperPortalScopes) account. If you lack the required scopes, refer to the [Integration partnership process](apiDevGuide-integrationDevProcess)guide for instructions on requesting access.

## Setup and planning

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Determine if you will pass reservation information to the Toast platform

Reservation integrations can follow one of two methods:

- [Read-only reservation integration](devCookbook-apiIntegrationChecklistReservation#reservationIntegReadOnly): Manage reservations within your system without sharing details with the Toast platform.


- [Read-write reservation integration](devCookbook-apiIntegrationChecklistReservation#reservationIntegWrite): Your integration will pass reservation information to the Toast platform.



With either method, your system will be the source of truth for reservation requests and availability. Toast recommends building a read-write integration to ensure consistency between your system and the Toast platform.

### Retrieve configuration information

Retrieve restaurant configurations using the following endpoints of [configuration API](https://doc.toasttab.com/openapi/configuration/overview/). To ensure you have the latest restaurant configuration, poll the configuration API once per restaurant location per day, and update configuration information in your system based on newly added, updated, or deleted information.

- Alternative payment types (this is optional. For more information, see [Determine what optional functionality you will support](devCookbook-apiIntegrationChecklistReservation#reservationIntegWriteOptional))


- Dining options


- Revenue centers


- Service charges (this is optional. For more information, see [Determine what optional functionality you will support](devCookbook-apiIntegrationChecklistReservation#reservationIntegWriteOptional))


- Tables



Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve the restaurant configuration you will need for reporting. Configuration options you may need include:

- Alternative payment types


- Dining options


- Discounts


- Revenue centers


- Sales categories


- Service areas


- Service charges


- Tables



Use the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/) to retrieve information about the configuration of a restaurant, including restaurant service hours and location information. Use the restaurant information to ensure guests cannot create reservations outside of the restaurant's hours of operation.

### Learn order structure concepts

Familiarize yourself with the structure of an order by reading the [Orders API overview](apiDevGuide-portalOrdersApiOverview) and [Order object summary](apiDevGuide-apiOrdersOrderObjectSummary). For more information about the orders API, see the [reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

Poll the `[/ordersBulk](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/)`endpoint of the orders API using the `startDate` and `endDate` query parameters to understand new and modified orders placed within the specified timeframe. Your polling frequency should align with your polling window. For example, if you poll for a window of five minutes, you should poll roughly once every five minutes.

Ensure your integration adheres to the endpoint specific rate-limit for the `/ordersBulk` endpoint when retrieving order data. For more information about Toast rate limits, see [Rate limiting](apiDevGuide-apiRateLimiting).

To understand which order elements are relevant to your integration, see [Understanding reservation order data](devCookbook-apiIntegrationChecklistReservation#reservationIntegData).

## Building a read-only reservation integration

Since your integration will handle reservations entirely within your system, you will rely on the response from the orders API to obtain the necessary order data for updating reservation information in your system. For more information, see [Understanding reservation order data](devCookbook-apiIntegrationChecklistReservation#reservationIntegData).

## Building a read-write reservation integration

If your integration is passing reservation information to the Toast platform, you will submit an order without menu item selections and include the required information listed below. Your integration will do this by sending a `POST` request to the [`/orders`](https://doc.toasttab.com/openapi/orders/operation/ordersPost/)endpoint of the orders API. For more information, see [Creating orders](apiDevGuide-apiCreatingOrders).

### Understand required information

When passing reservation information to the Toast platform, your integration must include the following information.

#### Dining option

Include a `diningOption` with a `DINE_IN`dining behavior in the order. Send a `GET` request to the `[/diningOptions](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/)`endpoint of the configuration API to retrieve the restaurant's dining options. Your integration should allow restaurants to choose which dining options they want your integration to use in your system's user interface.

#### Revenue center

Include a `revenueCenter` in the order. Assigning a revenue center to orders allows restaurants to categorize reservation orders in their revenue reporting. Send a `GET` request to the `[/revenueCenters](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/)`endpoint of the configuration API to retrieve the restaurant's revenue centers. Your integration should allow restaurants to choose which revenue center they want your integration to use in your system's user interface.

#### Table

Include a `table` in the order. This links the reservation details to the specific table at the restaurant where the guest will be dining. Send a `GET` request to the [`/tables`](https://doc.toasttab.com/openapi/configuration/operation/tablesGet/)endpoint of the configuration API to retrieve information about a restaurant's tables. Your table configurations should match the table configurations in the Toast platform.

#### Guest count

Include the `numberOfGuests` value in the order to identify guest count. This helps restaurant staff prepare and manage the table effectively by knowing how many guests are dining. Additionally, the `numberOfGuests` provides useful information for building reports.

#### Tab name

Include a `tabName` value in the order to identify your integration and guest information. Use the naming convention: `&#123;Partner name} - &#123;Guest first name} &#123;Guest last initial&#125;`. Your integration should allow restaurants to customize tab naming conventions in your system's user interface based on restaurant requirements.

For more information about where tab names appear in the Toast platform, see [Guest personal identifiable information](adminGuide-platformOrdersPii).

### Determine what optional functionality you will support

When passing reservation information to the Toast platform, your integration may include the following optional functionality.

#### Deposits

If your system collects deposits with reservations, you must communicate this information to the Toast platform when you submit the reservation so that the guest is not asked to repay their deposit amount. Deposits are processed through your system when the guest makes the reservation and is communicated to Toast when you submit the order. Deposits are not processed through Toast and use an alternative payment type in the reservation order submission. You are responsible for paying the restaurant for deposits made outside of the Toast platform.

To retrieve your alternative payment type identifier, send a `GET` request to the `/alternativePaymentTypes`endpoint of the configuration API and submit this payment type in the `payments` object of your reservation order. For more information, see [Alternative payment types](apiDevGuide-apiCreatingAnOrderWithPaymentInformation) to learn more about submitting payments using the orders API.

If you support deposits, your onboarding process should include working with restaurants to create an alternative payment type specific to your integration. [This guide](https://central.toasttab.com/s/article/Setting-Up-Other-Payment-Options) outlines how to create alternative payment types in the Toast platform. Creating an alternative payment type cannot be done via API.

#### Employee information

You can optionally allow restaurant operators to assign servers to reservations when guests check in. If your integration will support this, send a `GET` request to the `[/employees](https://doc.toasttab.com/openapi/labor/operation/employeesGet/)`endpoint of the labor API to retrieve information about restaurant employees. Include the identifier of the employee in the `server` field in your order submission.

#### Service charges

You can optionally pass service charges with reservation orders. Including a service charge enables restaurants to add additional fees to reservation orders, such as gratuity. To retrieve service charge information, send a `GET` request to the `[/serviceCharges](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/)`endpoint of the configuration API. Your integration should allow restaurants to choose which service charges they want your integration to use in your system's user interface. For more information, see [Service charge overview](adminGuide-adminServiceChargeOverview)to learn more.

### Reservation creation workflow

#### Create and submit a reservation to the Toast platform

The workflow below outlines how to create a reservation in your system and submit the reservation information to the Toast platform:

1. The guest creates a reservation in your system.

- If your system requires a deposit, collect it now.


- Ensure guests cannot create reservations outside of the restaurant's hours of operation.


- Collect the [reservation information](devCookbook-apiIntegrationChecklistReservation#reservationIntegWriteRequired) required by Toast for order submission.




2. When the guest arrives at the restaurant, the restaurant operator checks in the guest through your reservation system. Once checked in:

- Send a `POST` request to `/orders` endpoint the orders API containing information about the reservation, including the dining option, revenue center, table, number of guests, and tab name.


- Optionally include payment information for the deposit.


- Optionally include employee information to indicate the server assigned to the reservation.


- Optionally include a service charge.




3. Update the reservation in your system using the information outlined in [Understanding reservation order data](devCookbook-apiIntegrationChecklistReservation#reservationIntegData).



**Example 1.1. Example POST request to the orders API**


```
{
  "diningOption": {
    "guid": "374d500f-c6d8-44d0-a18d-43fe5e7f750c"
  },
  "revenueCenter": {
    "guid": "81665a60-c20d-41da-a362-6474eab830d3"
  },
  "table": {
    "guid": "880a2f72-8960-4a3f-b2a2-60b7a19975e7"
  },
  "numberOfGuests": 4,
  "server": {
    "guid": "90d97fb8-931f-4196-aae9-d71bbcd5d3df"
  },
  "checks": [
    {
      "tabName": "Reservation Partner - Ann M"
    },
    {
      "appliedServiceCharges": [
        {
          "serviceCharge": {
            "guid": "9b2dd3cc-f4ab-4586-8c5a-2bbf6a9eef8d"
           }
         }
       ]
     },

    {
      "payments": [
        {
          "type": "OTHER",
          "amount": "20.00",
          "tipAmount": "0.00",
          "otherPayment": {
            "guid": "40dbc841-7f29-47d0-9834-9cf9c5b591d2"
          }
        }
      ]
    }
  ]
}
```



    <tr>
      <td>[(1)](#co-res-diningOption)</td>
      <td>The `diningOption` used by restaurants for orders with a dining behavior of `DINE_IN`.</td>
    </tr>
    <tr>
      <td>[(2)](#co-res-revenueCenter)</td>
      <td>The `revenueCenter` used by the restaurant for reservation orders.</td>
    </tr>
    <tr>
      <td>[(3)](#co-res-table)</td>
      <td>The `table` the guest has been assigned to.</td>
    </tr>
    <tr>
      <td>[(4)](#co-res-numberOfGuests)</td>
      <td>The number of guests for the reservation.</td>
    </tr>
    <tr>
      <td>[(5)](#co-res-server)</td>
      <td>The employee guid of the `server` assigned to the reservation.</td>
    </tr>
    <tr>
      <td>[(6)](#co-res-tabName)</td>
      <td>The `tabName` for the order to identify your reservation and guest information.</td>
    </tr>
    <tr>
      <td>[(7)](#co-res-serviceCharge)</td>
      <td>The `serviceCharge` used by the restaurant for reservation orders.</td>
    </tr>
    <tr>
      <td>[(8)](#co-res-deposit)</td>
      <td>The deposit amount.</td>
    </tr>
    <tr>
      <td>[(9)](#co-res-otherPayment)</td>
      <td>The guid used to identify the `alternativePaymentType` used for reservation deposits.</td>
    </tr>
  
## Understanding reservation order data

Use the following information from the orders API response to update the reservation in your system in real-time.


<table>
  <thead>
    <tr>
      <th>Information type</th>
      <th>Transactional information</th>
      <th>Additional information</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Dining option</td>
      <td>`order.diningOption.guid`</td>
      <td>Review the `guid` value associated with the `diningOption` assigned to the order to understand dining behavior.  <br/> Orders associated with reservations will have a `diningOption` with a `DINE_IN` dining behavior.  <br/> For more information, see the orders API reference documentation on the [`diningOption`](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=diningOption&t=response) object.</td>
    </tr>
    <tr>
      <td>Guest count</td>
      <td>`order.numberOfGuests`</td>
      <td>Review the value associated with the `numberOfGuests` assigned to the order to understand guest count.  <br/> For more information, see the orders API reference documentation on the [`numberOfGuests`](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=numberOfGuests&t=response) key.</td>
    </tr>
    <tr>
      <td>Order status</td>
      <td>`order.closedDate`</td>
      <td>Review the date to understand when guests have paid for their meal. This indicates that the table will be available soon.  <br/> For more information, see the orders API reference documentation on the [`closedDate`](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=closedDate&t=response).</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>`order.table.guid`</td>
      <td>Review the `guid` value associated with the `table` assigned to the order to understand `table` assignment.  <br/> For more information, see the orders API reference documentation on the [`table`](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/#!c=200&path=table&t=response) object.  <br/> To understand the `table guid` values, send a `GET` request to the [`/tables`](https://doc.toasttab.com/openapi/configuration/operation/tablesGet/) endpoint of the configuration API to retrieve the restaurant's tables.</td>
    </tr>
  </tbody>
</table>

## Reporting

The `/ordersBulk` endpoint response of the orders API response will allow you to understand order details required for reporting. Consider reporting on item selection and check amount, including discounts and service charges. Information about orders can also be related to guest profiles managed within your system. Options for reporting categorization that can be understood from the orders API include:

- Dining options


- Revenue center


- Sales categories


- Service areas



Use the [menus API](https://doc.toasttab.com/openapi/menus/operation/menusGet/) to retrieve menu and item information to understand guest selections for reporting.

See [Building a sales report](devCookbook-apiIntegrationChecklistAccounting) for additional guidance on order reporting.

