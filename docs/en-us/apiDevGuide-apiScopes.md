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
      <td>`cashmgmt:read`</td>
      <td>Allows reading from the [cash management API](https://doc.toasttab.com/openapi/cashmanagement/overview/).</td>
    </tr>
    <tr>
      <td>Configuration</td>
      <td>Read</td>
      <td>`config:read`</td>
      <td>Allows reading from the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/).</td>
    </tr>
    <tr>
      <td>Credit cards</td>
      <td>Write</td>
      <td>`credit_cards.authorization:write`</td>
      <td>Allows authorization of payments through the [credit cards API](https://doc.toasttab.com/openapi/creditcards/overview/).</td>
    </tr>
    <tr>
      <td>Kitchen</td>
      <td>Read</td>
      <td>`kitchen:read`</td>
      <td>Allows reading from the[ kitchen API](https://doc.toasttab.com/openapi/kitchen/overview/).</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Read</td>
      <td>`labor:read`</td>
      <td>Allows reading all data except employees from the [labor API](https://doc.toasttab.com/openapi/labor/overview/).</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Read</td>
      <td>`labor.employees:read`</td>
      <td>Allows reading employee information from the [labor API](https://doc.toasttab.com/openapi/labor/overview/).</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td>`labor.employees:write`</td>
      <td>Allows updating employee information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/).</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td>`labor.jobs:write`</td>
      <td>Allows updating job information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/).</td>
    </tr>
    <tr>
      <td>Labor</td>
      <td>Write</td>
      <td>`labor.shifts:write`</td>
      <td>Allows updating shift information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/).</td>
    </tr>
    <tr>
      <td>Menus</td>
      <td>Read</td>
      <td>`menus.channel:read`</td>
      <td>Allows reading from the [menus API V3](https://doc.toasttab.com/openapi/menusv3/overview/). <blockquote><strong>Note</strong> Ordering partner integrations must use V3 of the menus API, which requires the `menus.channel:read` scope. Because V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the `menus:read` scope.</blockquote> </td>
    </tr>
    <tr>
      <td>Menus</td>
      <td>Read</td>
      <td>`menus:read`</td>
      <td>Allows reading from the [menus API V2](https://doc.toasttab.com/openapi/menus/overview/). <blockquote><strong>Note</strong> Because menus API V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the `menus:read` scope.</blockquote> </td>
    </tr>
    <tr>
      <td>Order management configuration</td>
      <td>Read</td>
      <td>`digital_schedule:read`</td>
      <td>Allows reading from the [order management configuration API](https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td>`orders:read`</td>
      <td>Allows reading from the [orders API](https://doc.toasttab.com/openapi/orders/overview/) with the exception of guest information. <br/> If your API client creates orders, then to read orders, it must have both the `orders:read` scope and the `orders.channel:read` scope.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td>`orders.channel:read`</td>
      <td>Allows API clients that submit orders to the Toast platform to read from the [orders API](https://doc.toasttab.com/openapi/orders/overview/). <br/> To read orders, the API client must have both the `orders:read` scope and the `orders.channel:read` scope. <br/> API clients that have the `orders.channel:read` scope can only read the orders that they submitted. They cannot read orders from any other source.</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td>`delivery_info.address:read`</td>
      <td>Allows reading guest delivery address information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Read</td>
      <td>`guest.pi:read`</td>
      <td>Allows reading guest and curbside pickup information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td>`orders.delivery_info:write`</td>
      <td>Allows updating delivery information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td>`orders.discounts:write`</td>
      <td>Allows adding discounts to orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td>`orders.items:write`</td>
      <td>Allows adding items to orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td>`orders.orders:write`</td>
      <td>Allows posting orders orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Write</td>
      <td>`orders.payments:write`</td>
      <td>Allows adding payments and tips to existing orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/). </td>
    </tr>
    <tr>
      <td>Orders</td>
      <td>Void</td>
      <td>`orders.channel:void`</td>
      <td>Allows voiding an order using the [orders API](https://doc.toasttab.com/openapi/orders/overview/).</td>
    </tr>
    <tr>
      <td>Packaging preferences</td>
      <td>Read</td>
      <td>`packaging:read`</td>
      <td>Allows reading a restaurant's packaging preferences configuration using the [packaging configuration API](https://doc.toasttab.com/openapi/packaging/overview/). </td>
    </tr>
    <tr>
      <td>Restaurant availability <br/> Restaurants</td>
      <td>Read</td>
      <td>`restaurants:read`</td>
      <td>Allows reading from the [restaurant availability API](https://doc.toasttab.com/openapi/rx.availability.service/overview/). <br/> Allows reading from the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/).</td>
    </tr>
    <tr>
      <td>Stock</td>
      <td>Read</td>
      <td>`stock:read`</td>
      <td>Allows reading from the [stock API](https://doc.toasttab.com/openapi/stock/overview/).</td>
    </tr>
    <tr>
      <td>Stock</td>
      <td>Write</td>
      <td>`stock:write`</td>
      <td>Allows updating stock status for menu items (and modifier option [item references](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference)) using the [stock API](https://doc.toasttab.com/openapi/stock/overview/).</td>
    </tr>
  </tbody>
</table>

## Getting API client scopes

The scopes that give your Toast API client permission to use APIs, endpoints, and endpoint functions are assigned based on your organization's business requirements. Some Toast API scopes are available to all API clients and some scopes are assigned to clients after specific certification of the integration function they are used for.

If your API client does not have the scope required to perform an action, you can contact the Toast integrations team to learn about the requirements for getting access to the scope. The business requirements of your organization and the status of your integration affect the scopes assigned your API client.

