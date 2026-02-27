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
      <th className=""><div className="">API</div></th>
      <th className=""><div className="">Scope Type</div></th>
      <th className=""><div className="">Scope Name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Cash management</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">cashmgmt:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/cashmanagement/overview/" className="">cash management API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Configuration</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">config:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/configuration/overview/" className="">configuration API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit cards</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">credit_cards.authorization:write</code></div></td>
      <td className=""><div className="">Allows authorization of payments through the <a href="https://doc.toasttab.com/openapi/creditcards/overview/" className="">credit cards API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Kitchen</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">kitchen:read</code></div></td>
      <td className=""><div className="">Allows reading from the<a href="https://doc.toasttab.com/openapi/kitchen/overview/" className=""> kitchen API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">labor:read</code></div></td>
      <td className=""><div className="">Allows reading all data except employees from the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">labor.employees:read</code></div></td>
      <td className=""><div className="">Allows reading employee information from the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">labor.employees:write</code></div></td>
      <td className=""><div className="">Allows updating employee information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">labor.jobs:write</code></div></td>
      <td className=""><div className="">Allows updating job information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Labor</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">labor.shifts:write</code></div></td>
      <td className=""><div className="">Allows updating shift information in the <a href="https://doc.toasttab.com/openapi/labor/overview/" className="">labor API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menus</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">menus.channel:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/menusv3/overview/" className="">menus API V3</a>. <blockquote><strong>Note</strong> Ordering partner integrations must use V3 of the menus API, which requires the <code className="">menus.channel:read</code> scope. Because V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the <code className="">menus:read</code> scope.</blockquote> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menus</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">menus:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/menus/overview/" className="">menus API V2</a>. <blockquote><strong>Note</strong> Because menus API V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the <code className="">menus:read</code> scope.</blockquote> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order management configuration</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">digital_schedule:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/" className="">order management configuration API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">orders:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a> with the exception of guest information. <br/> If your API client creates orders, then to read orders, it must have both the <code className="">orders:read</code> scope and the <code className="">orders.channel:read</code> scope.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">orders.channel:read</code></div></td>
      <td className=""><div className="">Allows API clients that submit orders to the Toast platform to read from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>. <br/> To read orders, the API client must have both the <code className="">orders:read</code> scope and the <code className="">orders.channel:read</code> scope. <br/> API clients that have the <code className="">orders.channel:read</code> scope can only read the orders that they submitted. They cannot read orders from any other source.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">delivery_info.address:read</code></div></td>
      <td className=""><div className="">Allows reading guest delivery address information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">guest.pi:read</code></div></td>
      <td className=""><div className="">Allows reading guest and curbside pickup information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">orders.delivery_info:write</code></div></td>
      <td className=""><div className="">Allows updating delivery information from the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">orders.discounts:write</code></div></td>
      <td className=""><div className="">Allows adding discounts to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">orders.items:write</code></div></td>
      <td className=""><div className="">Allows adding items to orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">orders.orders:write</code></div></td>
      <td className=""><div className="">Allows posting orders orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">orders.payments:write</code></div></td>
      <td className=""><div className="">Allows adding payments and tips to existing orders using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orders</div></td>
      <td className=""><div className="">Void</div></td>
      <td className=""><div className=""><code className="">orders.channel:void</code></div></td>
      <td className=""><div className="">Allows voiding an order using the <a href="https://doc.toasttab.com/openapi/orders/overview/" className="">orders API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Packaging preferences</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">packaging:read</code></div></td>
      <td className=""><div className="">Allows reading a restaurant's packaging preferences configuration using the <a href="https://doc.toasttab.com/openapi/packaging/overview/" className="">packaging configuration API</a>. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Restaurant availability <br/> Restaurants</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">restaurants:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/rx.availability.service/overview/" className="">restaurant availability API</a>. <br/> Allows reading from the <a href="https://doc.toasttab.com/openapi/restaurants/overview/" className="">restaurants API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Stock</div></td>
      <td className=""><div className="">Read</div></td>
      <td className=""><div className=""><code className="">stock:read</code></div></td>
      <td className=""><div className="">Allows reading from the <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Stock</div></td>
      <td className=""><div className="">Write</div></td>
      <td className=""><div className=""><code className="">stock:write</code></div></td>
      <td className=""><div className="">Allows updating stock status for menu items (and modifier option <a href="adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference" className="">item references</a>) using the <a href="https://doc.toasttab.com/openapi/stock/overview/" className="">stock API</a>.</div></td>
    </tr>
  </tbody>
</table>
</div>

## Getting API client scopes

The scopes that give your Toast API client permission to use APIs, endpoints, and endpoint functions are assigned based on your organization's business requirements. Some Toast API scopes are available to all API clients and some scopes are assigned to clients after specific certification of the integration function they are used for.

If your API client does not have the scope required to perform an action, you can contact the Toast integrations team to learn about the requirements for getting access to the scope. The business requirements of your organization and the status of your integration affect the scopes assigned your API client.

