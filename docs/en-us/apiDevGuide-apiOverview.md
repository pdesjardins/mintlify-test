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
      <th className=""><div className="">API</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Supported Methods by Integration Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Analytics API (<code className="">era</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/analytics/overview/" className="">analytics (<code className="">era</code>) API</a> provides access to information for reporting and performance.  <br/> For more information about using the analytics API, see <a href="apiDevGuide-apiAnalyticsOverview" className="">Analytics API overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>: Analytics API access <br/> <code className="">POST</code>: Analytics API access</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash management (<code className="">cashmgmt</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/" className="">cash management (<code className="">cashmgmt</code>) API</a> provides access to information about cash drawer events such as cash received and cash paid out. <br/> For information about using the cash management API, see <a href="apiDevGuide-apiWorkingWithCashEntriesAndDeposits" className="">Cash management overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Configuration (<code className="">config</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/configuration/overview/" className="">configuration (<code className="">config</code>) API</a> provides access to information about the configuration of a location. You can use the configuration API to get information about the revenue centers, dining options, payment options, and other aspects of a location. <br/> The configuration API returns the Globally Unique Identifiers (GUIDs) that the Toast platform assigns to configuration objects. You can use these GUIDs to interact with other Toast APIs. <br/> For information about using the configuration API, see <a href="apiDevGuide-menu_information_config_api" className="">Getting menu information from the configuration API</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit cards (<code className="">ccpartner</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/creditcards/overview/" className="">credit cards (<code className="">ccpartner</code>) API</a> authorizes credit card payments that you can apply to checks in the orders API. <br/> For information about using the credit cards API, see <a href="apiDevGuide-authorizingCcPayments" className="">Credit card payments</a>.</div></td>
      <td className=""><div className=""><code className="">PUT</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gift cards</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/giftcards/overview/" className="">gift cards API specification</a> describes an API that you can implement to enable the Toast platform to process gift card transactions through your gift card provider service. <br/> For information about implementing the gift card integration API, see <a href="apiDevGuide-apiGiftCardIntegrationOverview" className="">Gift card integration overview</a>.</div></td>
      <td className=""><div className="">This API is outbound. You must host an HTTPS endpoint that accepts <code className="">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Kitchen (<code className="">kitchen</code>)</div></td>
      <td className=""><div className="">The kitchen API provides access to kitchen prep station information.  <br/> For more information about the kitchen API, see <a href="https://doc.toasttab.com/openapi/kitchen/overview/" className="">Kitchen API reference</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor (<code className="">labor</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a> provides access to employment and work schedule configuration information. You can use the labor API to get information about and configure employee records, job types, scheduled work shifts, and work shift time entries. <br/> For information about using the labor API, see <a href="apiDevGuide-api_get_all_employees" className="">Getting all employees of a restaurant</a> and <a href="apiDevGuide-apiAddingAnEmployee" className="">Adding an employee</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul> <br/> <code className="">POST</code>, <code className="">PUT</code>, <code className="">PATCH</code>, <code className="">DELETE</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Loyalty</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/loyalty/overview/" className="">loyalty integration API specification</a> describes an API that you can implement to enable the Toast platform to process loyalty program transactions through your loyalty service. <br/> For information about implementing the loyalty integration API, see <a href="apiDevGuide-apiLoyaltyProgramIntegrationOverview" className="">Loyalty program integration overview</a>.</div></td>
      <td className=""><div className="">This API is outbound. You must host an HTTPS endpoint that accepts <code className="">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menus (<code className="">menus</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/menus/overview/" className="">menus API</a> lets you retrieve a fully resolved set of menus for the location you specify. With this data, you can construct a menu that satisfies your business requirements. <br/> For information about using the menus API, see <a href="apiDevGuide-apiGettingMenuInformationFromTheMenusAPI" className="">Menus API overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders (<code className="">orders</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a> provides access to information about menu orders. You can use the <code className="">orders</code> API to get information about and create menu orders, checks, and payment. <br/> For information about using the orders API, see <a href="apiDevGuide-portalOrdersApiOverview" className="">Orders API overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul> <br/> <code className="">POST</code>, <code className="">PATCH</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order management configuration (<code className="">ordermgmt-config</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/" className="">order management configuration (<code className="">ordermgmt-config</code>) API</a> provides information about a location's online ordering schedule.  <br/> For information about using the order management configuration API, see <a href="apiDevGuide-apiGettingOnlineOrderingSchedules" className="">Getting online ordering schedules</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Packaging configuration (<code className="">packaging</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/packaging/overview/" className="">packaging configuration (<code className="">packaging</code>) API</a> provides information about a location's packaging preference configurations.  <br/> For information about using the packing configuration API, see <a href="apiDevGuide-apiOrdersPackagingPreferences" className="">Packaging preferences</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Partners (<code className="">partners</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/partners/overview/" className="">partners API</a> provides information about locations an API client has access to.  <br/> For information about using the partners API, see <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants" className="">Location access</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Restaurant availability (<code className="">restaurant-availability</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/" className="">restaurant availability API</a> provides access to information about a location's availability to accept online orders.  <br/> For more information about using the restaurant availability API, see <a href="apiDevGuide-apiGettingRxOnlineOrderingAvailability" className="">Getting a restaurant's online ordering availability</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Restaurants (<code className="">restaurants</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/restaurants/overview/" className="">restaurants API</a> provides access to configuration information for a location. You can use the restaurants API to get information such as location name, address, hours, and schedules. <br/> For information about using the restaurants API, see <a href="apiDevGuide-apiRestaurantInfo" className="">Restaurant information overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Stock (<code className="">stock</code>)</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a> provides access to information about inventory for menu items and modifier options at a location. You can use the stock API to determine whether a menu item or modifier option is in stock or what quantity is in stock. <br/> For information about using the stock API, see <a href="apiDevGuide-apiStock" className="">Stock overview</a>.</div></td>
      <td className=""><div className=""><code className="">GET</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li><li className="">Standard API access</li></ul> <br/> <code className="">POST</code>, <code className="">PUT</code>:<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tender</div></td>
      <td className=""><div className="">The <a href="https://doc.toasttab.com/openapi/tender/overview/" className="">tender integration API specification</a> describes an API that you can implement to allow the Toast platform to provide information about tender transactions processed by the Toast POS system. Your tender system can use this data to maintain a complete record of payments, refunds, and other transaction activity. <br/> For information about implementing the tender integration API, see <a href="apiDevGuide-apiTenderProviderIntegrationsOverview" className="">Tender provider integrations overview</a>.</div></td>
      <td className=""><div className="">This API is outbound. You must host an HTTPS endpoint that accepts <code className="">POST</code> requests from the Toast platform and returns one of the predefined acceptable responses.<ul className=""><li className="">Partner integrations</li><li className="">Custom integrations</li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

