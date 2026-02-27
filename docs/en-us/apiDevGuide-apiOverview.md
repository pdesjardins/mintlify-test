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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">API</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Supported Methods by Integration Type</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Analytics API (<code className="font-mono text-sm">era</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/analytics/overview/" className="">analytics (<code className="font-mono text-sm">era</code>) API</a> provides access to information for reporting and performance. </p> <p className="text-base leading-relaxed">For more information about using the analytics API, see <a href="apiDevGuide-apiAnalyticsOverview" className="">Analytics API overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>: Analytics API access</p> <p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code>: Analytics API access</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash management (<code className="font-mono text-sm">cashmgmt</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/" className="">cash management (<code className="font-mono text-sm">cashmgmt</code>) API</a> provides access to information about cash drawer events such as cash received and cash paid out.</p> <p className="text-base leading-relaxed">For information about using the cash management API, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">Cash management overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Configuration (<code className="font-mono text-sm">config</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/configuration/overview/" className="">configuration (<code className="font-mono text-sm">config</code>) API</a> provides access to information about the configuration of a location. You can use the configuration API to get information about the revenue centers, dining options, payment options, and other aspects of a location.</p> <p className="text-base leading-relaxed">The configuration API returns the Globally Unique Identifiers (GUIDs) that the Toast platform assigns to configuration objects. You can use these GUIDs to interact with other Toast APIs.</p> <p className="text-base leading-relaxed">For information about using the configuration API, see <a href="apiDevGuide-menu_information_config_api" className="">Getting menu information from the configuration API</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Credit cards (<code className="font-mono text-sm">ccpartner</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/creditcards/overview/" className="">credit cards (<code className="font-mono text-sm">ccpartner</code>) API</a> authorizes credit card payments that you can apply to checks in the orders API.</p> <p className="text-base leading-relaxed">For information about using the credit cards API, see <a href="apiDevGuide-authorizingCcPayments" className="">Credit card payments</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">PUT</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gift cards</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/giftcards/overview/" className="">gift cards API specification</a> describes an API that you can implement to enable the Toast platform to process gift card transactions through your gift card provider service.</p> <p className="text-base leading-relaxed">For information about implementing the gift card integration API, see <a href="apiDevGuide-apiGiftCardIntegrationOverview" className="">Gift card integration overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This API is outbound. You must host an HTTPS endpoint that accepts <code className="font-mono text-sm">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen (<code className="font-mono text-sm">kitchen</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The kitchen API provides access to kitchen prep station information. </p> <p className="text-base leading-relaxed">For more information about the kitchen API, see <a href="https://doc.toasttab.com/openapi/kitchen/overview/" className="">Kitchen API reference</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor (<code className="font-mono text-sm">labor</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a> provides access to employment and work schedule configuration information. You can use the labor API to get information about and configure employee records, job types, scheduled work shifts, and work shift time entries.</p> <p className="text-base leading-relaxed">For information about using the labor API, see <a href="apiDevGuide-api_get_all_employees" className="">Getting all employees of a restaurant</a> and <a href="apiDevGuide-apiAddingAnEmployee" className="">Adding an employee</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul> <p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code>, <code className="font-mono text-sm">PUT</code>, <code className="font-mono text-sm">PATCH</code>, <code className="font-mono text-sm">DELETE</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Loyalty</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/loyalty/overview/" className="">loyalty integration API specification</a> describes an API that you can implement to enable the Toast platform to process loyalty program transactions through your loyalty service.</p> <p className="text-base leading-relaxed">For information about implementing the loyalty integration API, see <a href="apiDevGuide-apiLoyaltyProgramIntegrationOverview" className="">Loyalty program integration overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This API is outbound. You must host an HTTPS endpoint that accepts <code className="font-mono text-sm">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus (<code className="font-mono text-sm">menus</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/menus/overview/" className="">menus API</a> lets you retrieve a fully resolved set of menus for the location you specify. With this data, you can construct a menu that satisfies your business requirements.</p> <p className="text-base leading-relaxed">For information about using the menus API, see <a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI" className="">Menus API overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders (<code className="font-mono text-sm">orders</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a> provides access to information about menu orders. You can use the <code className="font-mono text-sm">orders</code> API to get information about and create menu orders, checks, and payment.</p> <p className="text-base leading-relaxed">For information about using the orders API, see <a href="apiDevGuide-portalOrdersApiOverview" className="">Orders API overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul> <p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code>, <code className="font-mono text-sm">PATCH</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order management configuration (<code className="font-mono text-sm">ordermgmt-config</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/" className="">order management configuration (<code className="font-mono text-sm">ordermgmt-config</code>) API</a> provides information about a location's online ordering schedule. </p> <p className="text-base leading-relaxed">For information about using the order management configuration API, see <a href="apiDevGuide-apiGettingOnlineOrderingSchedules" className="">Getting online ordering schedules</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Packaging configuration (<code className="font-mono text-sm">packaging</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/packaging/overview/" className="">packaging configuration (<code className="font-mono text-sm">packaging</code>) API</a> provides information about a location's packaging preference configurations. </p> <p className="text-base leading-relaxed">For information about using the packing configuration API, see <a href="apiDevGuide-apiOrdersPackagingPreferences" className="">Packaging preferences</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Partners (<code className="font-mono text-sm">partners</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/partners/overview/" className="">partners API</a> provides information about locations an API client has access to. </p> <p className="text-base leading-relaxed">For information about using the partners API, see <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants" className="">Location access</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant availability (<code className="font-mono text-sm">restaurant-availability</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/" className="">restaurant availability API</a> provides access to information about a location's availability to accept online orders. </p> <p className="text-base leading-relaxed">For more information about using the restaurant availability API, see <a href="apiDevGuide-apiGettingRxOnlineOrderingAvailability" className="">Getting a restaurant's online ordering availability</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurants (<code className="font-mono text-sm">restaurants</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/restaurants/overview/" className="">restaurants API</a> provides access to configuration information for a location. You can use the restaurants API to get information such as location name, address, hours, and schedules.</p> <p className="text-base leading-relaxed">For information about using the restaurants API, see <a href="apiDevGuide-apiRestaurantInfo" className="">Restaurant information overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Stock (<code className="font-mono text-sm">stock</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a> provides access to information about inventory for menu items and modifier options at a location. You can use the stock API to determine whether a menu item or modifier option is in stock or what quantity is in stock.</p> <p className="text-base leading-relaxed">For information about using the stock API, see <a href="apiDevGuide-apiStock" className="">Stock overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li><li className=""><p className="text-base leading-relaxed">Standard API access</p></li></ul> <p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code>, <code className="font-mono text-sm">PUT</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tender</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="https://doc.toasttab.com/openapi/tender/overview/" className="">tender integration API specification</a> describes an API that you can implement to allow the Toast platform to provide information about tender transactions processed by the Toast POS system. Your tender system can use this data to maintain a complete record of payments, refunds, and other transaction activity.</p> <p className="text-base leading-relaxed">For information about implementing the tender integration API, see <a href="apiDevGuide-apiTenderProviderIntegrationsOverview" className="">Tender provider integrations overview</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This API is outbound. You must host an HTTPS endpoint that accepts <code className="font-mono text-sm">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Partner integrations</p></li><li className=""><p className="text-base leading-relaxed">Custom integrations</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

