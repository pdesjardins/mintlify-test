---
title: "Scopes"
id: apiScopes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiResponseDataPagination.md
previousSectionTitle: "Paginating response data"
nextSectionFile: apiDevGuide-apiResponsesAndErrors.md
nextSectionTitle: "API responses and errors"
externalReferences: [https://doc.toasttab.com/openapi/cashmanagement/overview/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/creditcards/overview/, https://doc.toasttab.com/openapi/kitchen/overview/, https://doc.toasttab.com/openapi/labor/overview/, https://doc.toasttab.com/openapi/menusv3/overview/, https://doc.toasttab.com/openapi/menus/overview/, https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/packaging/overview/, https://doc.toasttab.com/openapi/rx.availability.service/overview/, https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/stock/overview/]
excerpt: "Access to Toast APIs, specific endpoints, and specific API endpoint operations is controlled by the scopes that are associated with your API account. Toast API scopes and their capabilities are..."
procedures: 0
codeExamples: 0
---

Access to Toast APIs, specific endpoints, and specific API endpoint operations is controlled by the scopes that are associated with your [API account](apiDevGuide-apiClientAccounts). Toast API scopes and their capabilities are described below.

To see the scopes associated with your API client, you must decrypt the authentication token you receive after you request an authentication token. For more information about the contents of a Toast API authentication token, see [Authentication return data for a partner API client](apiDevGuide-authentication#apiAuthenticationReturnDataPartner) and [Authentication return data for a restaurant management group API client](apiDevGuide-authentication#apiAuthenticationReturnDataRestaurant).

## API client scope reference

The following table describes the scopes that determine what actions your Toast API client has permission to perform.


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>API</th>
      <th>Scope Type</th>
      <th>Scope Name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Cash management</td>
      <td>Read</td>
      <td><code>cashmgmt:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/">cash management API</a>.</td>
    </tr>
    <tr>
      <td>Configuration</td>
      <td>Read</td>
      <td><code>config:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/configuration/overview/">configuration API</a>.</td>
    </tr>
    <tr>
      <td>Credit cards</td>
      <td>Write</td>
      <td><code>credit_cards.authorization:write</code></td>
      <td>Allows authorization of payments through the <a href="https://doc.toasttab.com/openapi/creditcards/overview/">credit cards API</a>.</td>
    </tr>
    <tr>
      <td>Kitchen</td>
      <td>Read</td>
      <td><code>kitchen:read</code></td>
      <td>Allows reading from the<a href="https://doc.toasttab.com/openapi/kitchen/overview/"> kitchen API</a>.</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Read</td>
      <td><code>labor:read</code></td>
      <td>Allows reading all data except employees from the <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a>.</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Read</td>
      <td><code>labor.employees:read</code></td>
      <td>Allows reading employee information from the <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a>.</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td><code>labor.employees:write</code></td>
      <td>Allows updating employee information in the <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a>.</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td><code>labor.jobs:write</code></td>
      <td>Allows updating job information in the <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a>.</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td><code>labor.shifts:write</code></td>
      <td>Allows updating shift information in the <a href="https://doc.toasttab.com/openapi/labor/overview/">labor API</a>.</td>
    </tr>
    <tr>
      <td>Menus</td>
      <td>Read</td>
      <td><code>menus.channel:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/menusv3/overview/">menus API V3</a>. <blockquote><strong>Note</strong> Ordering partner integrations must use V3 of the menus API, which requires the <code>menus.channel:read</code> scope. Because V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the <code>menus:read</code> scope.</blockquote> </td>
    </tr>
    <tr>
      <td>Menus</td>
      <td>Read</td>
      <td><code>menus:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/menus/overview/">menus API V2</a>. <blockquote><strong>Note</strong> Because menus API V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the <code>menus:read</code> scope.</blockquote> </td>
    </tr>
    <tr>
      <td>Order management configuration</td>
      <td>Read</td>
      <td><code>digital_schedule:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/">order management configuration API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td><code>orders:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a> with the exception of guest information. <br/> If your API client creates orders, then to read orders, it must have both the <code>orders:read</code> scope and the <code>orders.channel:read</code> scope.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td><code>orders.channel:read</code></td>
      <td>Allows API clients that submit orders to the Toast platform to read from the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>. <br/> To read orders, the API client must have both the <code>orders:read</code> scope and the <code>orders.channel:read</code> scope. <br/> API clients that have the <code>orders.channel:read</code> scope can only read the orders that they submitted. They cannot read orders from any other source.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td><code>delivery_info.address:read</code></td>
      <td>Allows reading guest delivery address information from the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td><code>guest.pi:read</code></td>
      <td>Allows reading guest and curbside pickup information from the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td><code>orders.delivery_info:write</code></td>
      <td>Allows updating delivery information from the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td><code>orders.discounts:write</code></td>
      <td>Allows adding discounts to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td><code>orders.items:write</code></td>
      <td>Allows adding items to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td><code>orders.orders:write</code></td>
      <td>Allows posting orders orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td><code>orders.payments:write</code></td>
      <td>Allows adding payments and tips to existing orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>. </td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Void</td>
      <td><code>orders.channel:void</code></td>
      <td>Allows voiding an order using the <a href="https://doc.toasttab.com/openapi/orders/overview/">orders API</a>.</td>
    </tr>
    <tr>
      <td>Packaging preferences</td>
      <td>Read</td>
      <td><code>packaging:read</code></td>
      <td>Allows reading a restaurant's packaging preferences configuration using the <a href="https://doc.toasttab.com/openapi/packaging/overview/">packaging configuration API</a>. </td>
    </tr>
    <tr>
      <td>Restaurant availability <br/> Restaurants</td>
      <td>Read</td>
      <td><code>restaurants:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/">restaurant availability API</a>. <br/> Allows reading from the <a href="https://doc.toasttab.com/openapi/restaurants/overview/">restaurants API</a>.</td>
    </tr>
    <tr>
      <td>Stock</td>
      <td>Read</td>
      <td><code>stock:read</code></td>
      <td>Allows reading from the <a href="https://doc.toasttab.com/openapi/stock/overview/">stock API</a>.</td>
    </tr>
    <tr>
      <td>Stock</td>
      <td>Write</td>
      <td><code>stock:write</code></td>
      <td>Allows updating stock status for menu items (and modifier option <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference">item references</a>) using the <a href="https://doc.toasttab.com/openapi/stock/overview/">stock API</a>.</td>
    </tr>
  </tbody>
</table>
</div>

## Getting API client scopes

The scopes that give your Toast API client permission to use APIs, endpoints, and endpoint functions are assigned based on your organization's business requirements. Some Toast API scopes are available to all API clients and some scopes are assigned to clients after specific certification of the integration function they are used for.

If your API client does not have the scope required to perform an action, you can contact the Toast integrations team to learn about the requirements for getting access to the scope. The business requirements of your organization and the status of your integration affect the scopes assigned your API client.

