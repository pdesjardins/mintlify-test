---
title: "API overview"
id: apiOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "API overview"
previousSectionFile: apiDevGuide-apiOverviewOmitChunkFromSearchIndex.md
previousSectionTitle: "API overview"
nextSectionFile: apiDevGuide-authenticationOmitChunkFromSearchIndex.md
nextSectionTitle: "Authentication"
externalReferences: [https://doc.toasttab.com/openapi/analytics/overview/, https://doc.toasttab.com/openapi/cashmanagement/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/creditcards/overview/, https://doc.toasttab.com/openapi/giftcards/overview/, https://doc.toasttab.com/openapi/kitchen/overview/, https://doc.toasttab.com/openapi/labor/overview/, https://doc.toasttab.com/openapi/loyalty/overview/, https://doc.toasttab.com/openapi/menus/overview/, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/, https://doc.toasttab.com/openapi/packaging/overview/, https://doc.toasttab.com/openapi/partners/overview/, https://doc.toasttab.com/openapi/rx.availability.service/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/stock/overview/, https://doc.toasttab.com/openapi/tender/overview/]
excerpt: "The Toast platform REST web service APIs make it easier and more efficient to work with location data. This guide is intended..."
keywords: ["GET", "POST", "PUT", "PATCH", "DELETE"]
procedures: 0
codeExamples: 0
---

The Toast platform REST web service APIs make it easier and more efficient to work with location data. This guide is intended for software engineers, technical managers, and other staff responsible for integrating third-party systems with the Toast platform. 

Toast APIs support both read and write operations. Read access is performed using `GET` requests. Write access includes `POST`, `PUT`, `PATCH`, and `DELETE` methods, as well as interaction with outbound APIs, which send data from the Toast platform to your system and await your response. 

Access to the APIs is further classified by the integration type. To determine what integration access type you have (partner integrations, custom integrations, standard API access, or analytics API access), see [Integration types](apiDevGuide-apiIntegrationTypes).



> **Note**
> 
> Partner and custom integration access is granted based on specific implementation requirements. While the methods listed represent the full range of possible access, actual permissions are limited to only what is necessary to support each integration's functionality.


Toast provides the following APIs:


<table>
  <thead>
    <tr>
      <th>API</th>
      <th>Description</th>
      <th>Supported Methods by Integration Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Analytics API (`era`)</td>
      <td>The [analytics (`era`) API](https://doc.toasttab.com/openapi/analytics/overview/) provides access to information for reporting and performance. <br/>For more information about using the analytics API, see [Analytics API overview](apiDevGuide-apiAnalyticsOverview).</td>
      <td>`GET`: Analytics API access<br/>`POST`: Analytics API access</td>
    </tr>
    <tr>
      <td>Cash management (`cashmgmt`)</td>
      <td>The [cash management (`cashmgmt`) API](https://doc.toasttab.com/openapi/cashmanagement/overview/) provides access to information about cash drawer events such as cash received and cash paid out.<br/>For information about using the cash management API, see [Cash management overview](apiDevGuide-apiWorkingWithCashEntriesAndDeposits).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Configuration (`config`)</td>
      <td>The [configuration (`config`) API](https://doc.toasttab.com/openapi/configuration/overview/) provides access to information about the configuration of a location. You can use the configuration API to get information about the revenue centers, dining options, payment options, and other aspects of a location.<br/>The configuration API returns the Globally Unique Identifiers (GUIDs) that the Toast platform assigns to configuration objects. You can use these GUIDs to interact with other Toast APIs.<br/>For information about using the configuration API, see [Getting menu information from the configuration API](apiDevGuide-menu_information_config_api).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Credit cards (`ccpartner`)</td>
      <td>The [credit cards (`ccpartner`) API](https://doc.toasttab.com/openapi/creditcards/overview/) authorizes credit card payments that you can apply to checks in the orders API.<br/>For information about using the credit cards API, see [Credit card payments](apiDevGuide-authorizingCcPayments).</td>
      <td>`PUT`:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Gift cards</td>
      <td>The [gift cards API specification](https://doc.toasttab.com/openapi/giftcards/overview/) describes an API that you can implement to enable the Toast platform to process gift card transactions through your gift card provider service.<br/>For information about implementing the gift card integration API, see [Gift card integration overview](apiDevGuide-apiGiftCardIntegrationOverview).</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts `POST` requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen (`kitchen`)</td>
      <td>The kitchen API provides access to kitchen prep station information. <br/>For more information about the kitchen API, see [Kitchen API reference](https://doc.toasttab.com/openapi/kitchen/overview/).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Labor (`labor`)</td>
      <td>The [labor API](https://doc.toasttab.com/openapi/labor/overview/) provides access to employment and work schedule configuration information. You can use the labor API to get information about and configure employee records, job types, scheduled work shifts, and work shift time entries.<br/>For information about using the labor API, see [Getting all employees of a restaurant](apiDevGuide-api_get_all_employees) and [Adding an employee](apiDevGuide-apiAddingAnEmployee).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul><br/>`POST`, `PUT`, `PATCH`, `DELETE`:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Loyalty</td>
      <td>The [loyalty integration API specification](https://doc.toasttab.com/openapi/loyalty/overview/) describes an API that you can implement to enable the Toast platform to process loyalty program transactions through your loyalty service.<br/>For information about implementing the loyalty integration API, see [Loyalty program integration overview](apiDevGuide-apiLoyaltyProgramIntegrationOverview).</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts `POST` requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Menus (`menus`)</td>
      <td>The [menus API](https://doc.toasttab.com/openapi/menus/overview/) lets you retrieve a fully resolved set of menus for the location you specify. With this data, you can construct a menu that satisfies your business requirements.<br/>For information about using the menus API, see [Menus API overview](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Orders (`orders`)</td>
      <td>The [orders API](https://doc.toasttab.com/openapi/orders/overview/) provides access to information about menu orders. You can use the `orders` API to get information about and create menu orders, checks, and payment.<br/>For information about using the orders API, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul><br/>`POST`, `PATCH`:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Order management configuration (`ordermgmt-config`)</td>
      <td>The [order management configuration (`ordermgmt-config`) API](https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/)provides information about a location's online ordering schedule. <br/>For information about using the order management configuration API, see [Getting online ordering schedules](apiDevGuide-apiGettingOnlineOrderingSchedules).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Packaging configuration (`packaging`)</td>
      <td>The [packaging configuration (`packaging`) API](https://doc.toasttab.com/openapi/packaging/overview/) provides information about a location's packaging preference configurations. <br/>For information about using the packing configuration API, see [Packaging preferences](apiDevGuide-apiOrdersPackagingPreferences).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Partners (`partners`)</td>
      <td>The [partners API](https://doc.toasttab.com/openapi/partners/overview/) provides information about locations an API client has access to. <br/>For information about using the partners API, see [Location access](apiDevGuide-apiPartnersGettingAccessibleRestaurants).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Restaurant availability (`restaurant-availability`)</td>
      <td>The [restaurant availability API](https://doc.toasttab.com/openapi/rx.availability.service/overview/) provides access to information about a location's availability to accept online orders. <br/>For more information about using the restaurant availability API, see [Getting a restaurant's online ordering availability](apiDevGuide-apiGettingRxOnlineOrderingAvailability).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Restaurants (`restaurants`)</td>
      <td>The [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/) provides access to configuration information for a location. You can use the restaurants API to get information such as location name, address, hours, and schedules.<br/>For information about using the restaurants API, see [Restaurant information overview](apiDevGuide-apiRestaurantInfo).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Stock (`stock`)</td>
      <td>The [stock API](https://doc.toasttab.com/openapi/stock/overview/) provides access to information about inventory for menu items and modifier options at a location. You can use the stock API to determine whether a menu item or modifier option is in stock or what quantity is in stock.<br/>For information about using the stock API, see [Stock overview](apiDevGuide-apiStock).</td>
      <td>`GET`:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul><br/>`POST`, `PUT`:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Tender</td>
      <td>The [tender integration API specification](https://doc.toasttab.com/openapi/tender/overview/) describes an API that you can implement to allow the Toast platform to provide information about tender transactions processed by the Toast POS system. Your tender system can use this data to maintain a complete record of payments, refunds, and other transaction activity.<br/>For information about implementing the tender integration API, see [Tender provider integrations overview](apiDevGuide-apiTenderProviderIntegrationsOverview).</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts `POST` requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
  </tbody>
</table>

