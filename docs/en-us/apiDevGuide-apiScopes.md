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
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">API</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Scope Type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Scope Name</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash management</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">cashmgmt:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/" className="">cash management API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">config:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/configuration/overview/" className="">configuration API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Credit cards</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">credit_cards.authorization:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows authorization of payments through the <a href="https://doc.toasttab.com/openapi/creditcards/overview/" className="">credit cards API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">kitchen:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the<a href="https://doc.toasttab.com/openapi/kitchen/overview/" className=""> kitchen API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">labor:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading all data except employees from the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">labor.employees:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading employee information from the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">labor.employees:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows updating employee information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">labor.jobs:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows updating job information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Labor</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">labor.shifts:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows updating shift information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menus.channel:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">menus:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Order management configuration</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">digital_schedule:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/" className="">order management configuration API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a> with the exception of guest information.</p> <p className="text-base leading-relaxed">If your API client creates orders, then to read orders, it must have both the <code className="font-mono text-sm">orders:read</code> scope and the <code className="font-mono text-sm">orders.channel:read</code> scope.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.channel:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows API clients that submit orders to the Toast platform to read from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p> <p className="text-base leading-relaxed">To read orders, the API client must have both the <code className="font-mono text-sm">orders:read</code> scope and the <code className="font-mono text-sm">orders.channel:read</code> scope.</p> <p className="text-base leading-relaxed">API clients that have the <code className="font-mono text-sm">orders.channel:read</code> scope can only read the orders that they submitted. They cannot read orders from any other source.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">delivery_info.address:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading guest delivery address information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">guest.pi:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading guest and curbside pickup information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.delivery_info:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows updating delivery information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.discounts:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows adding discounts to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.items:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows adding items to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.orders:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows posting orders orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.payments:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows adding payments and tips to existing orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Orders</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Void</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orders.channel:void</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows voiding an order using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Packaging preferences</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">packaging:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading a restaurant's packaging preferences configuration using the <a href="https://doc.toasttab.com/openapi/packaging/overview/" className="">packaging configuration API</a>. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant availability</p> <p className="text-base leading-relaxed">Restaurants</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurants:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/" className="">restaurant availability API</a>.</p> <p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/restaurants/overview/" className="">restaurants API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Stock</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">stock:read</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows reading from the <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Stock</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Write</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">stock:write</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows updating stock status for menu items (and modifier option <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">item references</a>) using the <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Getting API client scopes

The scopes that give your Toast API client permission to use APIs, endpoints, and endpoint functions are assigned based on your organization's business requirements. Some Toast API scopes are available to all API clients and some scopes are assigned to clients after specific certification of the integration function they are used for.

If your API client does not have the scope required to perform an action, you can contact the Toast integrations team to learn about the requirements for getting access to the scope. The business requirements of your organization and the status of your integration affect the scopes assigned your API client.

