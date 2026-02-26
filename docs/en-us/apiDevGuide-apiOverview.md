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
      <td>Analytics API (<code>era</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/analytics/overview/">analytics (<code>era</code>) API</a> provides access to information for reporting and performance.  <br/> For more information about using the analytics API, see <a href="apiDevGuide-apiAnalyticsOverview">Analytics API overview</a>.</td>
      <td><code>GET</code>: Analytics API access <br/> <code>POST</code>: Analytics API access</td>
    </tr>
    <tr>
      <td>Cash management (<code>cashmgmt</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/">cash management (<code>cashmgmt</code>) API</a> provides access to information about cash drawer events such as cash received and cash paid out. <br/> For information about using the cash management API, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits">Cash management overview</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Configuration (<code>config</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/configuration/overview/">configuration (<code>config</code>) API</a> provides access to information about the configuration of a location. You can use the configuration API to get information about the revenue centers, dining options, payment options, and other aspects of a location. <br/> The configuration API returns the Globally Unique Identifiers (GUIDs) that the Toast platform assigns to configuration objects. You can use these GUIDs to interact with other Toast APIs. <br/> For information about using the configuration API, see <a href="apiDevGuide-menu_information_config_api">Getting menu information from the configuration API</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Credit cards (<code>ccpartner</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/creditcards/overview/">credit cards (<code>ccpartner</code>) API</a> authorizes credit card payments that you can apply to checks in the orders API. <br/> For information about using the credit cards API, see <a href="apiDevGuide-authorizingCcPayments">Credit card payments</a>.</td>
      <td><code>PUT</code>:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Gift cards</td>
      <td>The <a href="https://doc.toasttab.com/openapi/giftcards/overview/">gift cards API specification</a> describes an API that you can implement to enable the Toast platform to process gift card transactions through your gift card provider service. <br/> For information about implementing the gift card integration API, see <a href="apiDevGuide-apiGiftCardIntegrationOverview">Gift card integration overview</a>.</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts <code>POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen (<code>kitchen</code>)</td>
      <td>The kitchen API provides access to kitchen prep station information.  <br/> For more information about the kitchen API, see <a href="https://doc.toasttab.com/openapi/kitchen/overview/">Kitchen API reference</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Labor (<code>labor</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a> provides access to employment and work schedule configuration information. You can use the labor API to get information about and configure employee records, job types, scheduled work shifts, and work shift time entries. <br/> For information about using the labor API, see <a href="apiDevGuide-api_get_all_employees">Getting all employees of a restaurant</a> and <a href="apiDevGuide-apiAddingAnEmployee">Adding an employee</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul> <br/> <code>POST</code>, <code>PUT</code>, <code>PATCH</code>, <code>DELETE</code>:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Loyalty</td>
      <td>The <a href="https://doc.toasttab.com/openapi/loyalty/overview/">loyalty integration API specification</a> describes an API that you can implement to enable the Toast platform to process loyalty program transactions through your loyalty service. <br/> For information about implementing the loyalty integration API, see <a href="apiDevGuide-apiLoyaltyProgramIntegrationOverview">Loyalty program integration overview</a>.</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts <code>POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Menus (<code>menus</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/menus/overview/">menus API</a> lets you retrieve a fully resolved set of menus for the location you specify. With this data, you can construct a menu that satisfies your business requirements. <br/> For information about using the menus API, see <a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI">Menus API overview</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Orders (<code>orders</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a> provides access to information about menu orders. You can use the <code>orders</code> API to get information about and create menu orders, checks, and payment. <br/> For information about using the orders API, see <a href="apiDevGuide-portalOrdersApiOverview">Orders API overview</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul> <br/> <code>POST</code>, <code>PATCH</code>:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Order management configuration (<code>ordermgmt-config</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/">order management configuration (<code>ordermgmt-config</code>) API</a> provides information about a location's online ordering schedule.  <br/> For information about using the order management configuration API, see <a href="apiDevGuide-apiGettingOnlineOrderingSchedules">Getting online ordering schedules</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Packaging configuration (<code>packaging</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/packaging/overview/">packaging configuration (<code>packaging</code>) API</a> provides information about a location's packaging preference configurations.  <br/> For information about using the packing configuration API, see <a href="apiDevGuide-apiOrdersPackagingPreferences">Packaging preferences</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Partners (<code>partners</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/partners/overview/">partners API</a> provides information about locations an API client has access to.  <br/> For information about using the partners API, see <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants">Location access</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Restaurant availability (<code>restaurant-availability</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/">restaurant availability API</a> provides access to information about a location's availability to accept online orders.  <br/> For more information about using the restaurant availability API, see <a href="apiDevGuide-apiGettingRxOnlineOrderingAvailability">Getting a restaurant's online ordering availability</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Restaurants (<code>restaurants</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/restaurants/overview/">restaurants API</a> provides access to configuration information for a location. You can use the restaurants API to get information such as location name, address, hours, and schedules. <br/> For information about using the restaurants API, see <a href="apiDevGuide-apiRestaurantInfo">Restaurant information overview</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul></td>
    </tr>
    <tr>
      <td>Stock (<code>stock</code>)</td>
      <td>The <a href="https://doc.toasttab.com/openapi/stock/overview/">stock API</a> provides access to information about inventory for menu items and modifier options at a location. You can use the stock API to determine whether a menu item or modifier option is in stock or what quantity is in stock. <br/> For information about using the stock API, see <a href="apiDevGuide-apiStock">Stock overview</a>.</td>
      <td><code>GET</code>:<ul><li>Partner integrations</li><li>Custom integrations</li><li>Standard API access</li></ul> <br/> <code>POST</code>, <code>PUT</code>:<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
    <tr>
      <td>Tender</td>
      <td>The <a href="https://doc.toasttab.com/openapi/tender/overview/">tender integration API specification</a> describes an API that you can implement to allow the Toast platform to provide information about tender transactions processed by the Toast POS system. Your tender system can use this data to maintain a complete record of payments, refunds, and other transaction activity. <br/> For information about implementing the tender integration API, see <a href="apiDevGuide-apiTenderProviderIntegrationsOverview">Tender provider integrations overview</a>.</td>
      <td>This API is outbound. You must host an HTTPS endpoint that accepts <code>POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul><li>Partner integrations</li><li>Custom integrations</li></ul></td>
    </tr>
  </tbody>
</table>

