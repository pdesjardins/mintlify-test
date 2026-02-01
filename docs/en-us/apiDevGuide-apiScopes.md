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

### Scopes

Access to Toast APIs, specific endpoints, and specific API endpoint operations is controlled by the scopes that are associated with your [API account](apiClientAccounts.html). Toast API scopes and their capabilities are described below.

To see the scopes associated with your API client, you must decrypt the authentication token you receive after you request an authentication token. For more information about the contents of a Toast API authentication token, see [Authentication return data for a partner API client](authentication.html#apiAuthenticationReturnDataPartner) and [Authentication return data for a restaurant management group API client](authentication.html#apiAuthenticationReturnDataRestaurant).

#### API client scope reference

The following table describes the scopes that determine what actions your Toast API client has permission to perform.

| API | Scope Type | Scope Name | Description | 
| --- | --- | --- | --- |
| Cash management | Read | `cashmgmt:read` | Allows reading from the [cash management API](https://doc.toasttab.com/openapi/cashmanagement/overview/). | 
| Configuration | Read | `config:read` | Allows reading from the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/). | 
| Credit cards | Write | `credit_cards.authorization:write` | Allows authorization of payments through the [credit cards API](https://doc.toasttab.com/openapi/creditcards/overview/). | 
| Kitchen | Read | `kitchen:read` | Allows reading from the[kitchen API](https://doc.toasttab.com/openapi/kitchen/overview/). | 
| Labor | Read | `labor:read` | Allows reading all data except employees from the [labor API](https://doc.toasttab.com/openapi/labor/overview/). | 
| Labor | Read | `labor.employees:read` | Allows reading employee information from the [labor API](https://doc.toasttab.com/openapi/labor/overview/). | 
| Labor | Write | `labor.employees:write` | Allows updating employee information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/). | 
| Labor | Write | `labor.jobs:write` | Allows updating job information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/). | 
| Labor | Write | `labor.shifts:write` | Allows updating shift information in the [labor API](https://doc.toasttab.com/openapi/labor/overview/). | 
| Menus | Read | `menus.channel:read` | Allows reading from the [menus API V3](https://doc.toasttab.com/openapi/menusv3/overview/).

> **Note**
> 
> Ordering partner integrations must use V3 of the menus API, which requires the `menus.channel:read` scope. Because V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the `menus:read` scope.


 | 
| Menus | Read | `menus:read` | Allows reading from the [menus API V2](https://doc.toasttab.com/openapi/menus/overview/).

> **Note**
> 
> Because menus API V3 currently only supports ordering partner integrations, all other integration partners should continue to use menus API V2, which requires the `menus:read` scope.


 | 
| Order management configuration | Read | `digital_schedule:read` | Allows reading from the [order management configuration API](https://doc.toasttab.com/openapi/ordermgmt.configuration/overview/). | 
| Orders | Read | `orders:read` | Allows reading from the [orders API](https://doc.toasttab.com/openapi/orders/overview/) with the exception of guest information.If your API client creates orders, then to read orders, it must have both the `orders:read` scope and the `orders.channel:read` scope. | 
| Orders | Read | `orders.channel:read` | Allows API clients that submit orders to the Toast platform to read from the [orders API](https://doc.toasttab.com/openapi/orders/overview/).To read orders, the API client must have both the `orders:read` scope and the `orders.channel:read` scope.API clients that have the `orders.channel:read` scope can only read the orders that they submitted. They cannot read orders from any other source. | 
| Orders | Read | `delivery_info.address:read` | Allows reading guest delivery address information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Read | `guest.pi:read` | Allows reading guest and curbside pickup information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Write | `orders.delivery_info:write` | Allows updating delivery information from the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Write | `orders.discounts:write` | Allows adding discounts to orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Write | `orders.items:write` | Allows adding items to orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Write | `orders.orders:write` | Allows posting orders orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Orders | Write | `orders.payments:write` | Allows adding payments and tips to existing orders using the [orders API](https://doc.toasttab.com/openapi/orders/overview/).  | 
| Orders | Void | `orders.channel:void` | Allows voiding an order using the [orders API](https://doc.toasttab.com/openapi/orders/overview/). | 
| Packaging preferences | Read | `packaging:read` | Allows reading a restaurant's packaging preferences configuration using the [packaging configuration API](https://doc.toasttab.com/openapi/packaging/overview/).  | 
| Restaurant availabilityRestaurants | Read | `restaurants:read` | Allows reading from the [restaurant availability API](https://doc.toasttab.com/openapi/rx.availability.service/overview/).Allows reading from the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/). | 
| Stock | Read | `stock:read` | Allows reading from the [stock API](https://doc.toasttab.com/openapi/stock/overview/). | 
| Stock | Write | `stock:write` | Allows updating stock status for menu items (and modifier option [item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference)) using the [stock API](https://doc.toasttab.com/openapi/stock/overview/). | 

#### Getting API client scopes

The scopes that give your Toast API client permission to use APIs, endpoints, and endpoint functions are assigned based on your organization's business requirements. Some Toast API scopes are available to all API clients and some scopes are assigned to clients after specific certification of the integration function they are used for.

If your API client does not have the scope required to perform an action, you can contact the Toast integrations team to learn about the requirements for getting access to the scope. The business requirements of your organization and the status of your integration affect the scopes assigned your API client.

