---
title: "Submitting your first order to the orders API"
id: apiOrdersFirstOrder
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-apiOrdersOrderObjectSummary.md
previousSectionTitle: "Order object summary"
nextSectionFile: apiDevGuide-apiOrdersErrors.md
nextSectionTitle: "Orders API errors"
externalReferences: [https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/configuration/overview/]
excerpt: "This topic describes how to authenticate, gather required information, build an order JSON payload, and submit your first order to the Toast orders API."
procedures: 0
codeExamples: 0
---

This topic describes how to authenticate, gather required information, build an order JSON payload, and submit your first order to the Toast orders API.

## Prerequisites

Before you begin, ensure you have the following:

- **API client credentials** - You need a `clientId` and `clientSecret` for authentication. For information about setting up an API client, see [Authentication](apiDevGuide-authentication).


- **Required scopes** - Your API client must have access to the following scopes:

- `orders.orders:write` - Required to submit orders.


- `config:read` - Required to retrieve dining options, menu groups, and menu items.



For more information about scopes, see [Scopes](apiDevGuide-apiScopes).


- **Location GUID** - The unique identifier for the Toast location you are submitting orders for. You can find this in Toast Web or retrieve it using the [restaurants API](https://doc.toasttab.com/openapi/restaurants/overview/).



## Order object overview

Every order requires, at minimum, a dining option and a check with menu item selections. The following example shows the basic `Order` object structure.


```
{
  "diningOption": {
    "guid": "`{diningOption GUID}`"
  },
  "checks": [
    {
      "selections": [
        {
          "item": {
            "guid": "`{selection item GUID}`"
          },
          "itemGroup": {
            "guid": "`{itemGroup GUID}`"
          },
          "quantity": 1
        }
      ]
    }
  ]
}
```

The following table describes the required fields:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Field</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">diningOption</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Object</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specifies the dining option for the order. Must contain a <code className="font-mono text-sm">guid</code> that references a valid dining option configured for the location.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checks</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Array</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An array of <code className="font-mono text-sm">Check</code> objects. Most orders have one check. Each check must contain at least one menu item selection.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checks.selections</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Array</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An array of <code className="font-mono text-sm">Selection</code> objects representing the menu items being ordered.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checks.selections.item</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Object</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A reference to the menu item being ordered. Must contain the <code className="font-mono text-sm">guid</code> of a valid menu item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checks.selections.itemGroup</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Object</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A reference to the menu group that contains the menu item. Must contain the <code className="font-mono text-sm">guid</code> of the parent menu group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">checks.selections.quantity</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Number</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of this menu item to order. Use a whole number for discrete items or a decimal for items sold by weight.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

For detailed information about all values in an `Order`object, see [Order object summary](apiDevGuide-apiOrdersOrderObjectSummary) and the [orders API reference documentation](https://doc.toasttab.com/openapi/orders/overview/).

### Required headers

All requests to the Toast platform APIs require the following headers:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Header</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Restaurant-External-ID</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the Toast location for the request.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Authorization</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The access token in the format <em className=""><code className="font-mono text-sm">Bearer &#123;accessToken&#125;</code></em> .</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Content-Type</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for <code className="font-mono text-sm">POST</code> requests. Must be set to <code className="font-mono text-sm">application/json</code>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Submitting your first order

Complete the following steps to submit your first order.

### To submit your first order

1. **Authenticate and get an access token**

Before making any API requests, you must obtain an access token using your client credentials.

Send a `POST` request to the `/authentication/v1/authentication/login` endpoint with the following request body:


```
{
  "clientId": "`clientId`",
  "clientSecret": "`clientSecret`",
  "userAccessType": "TOAST_MACHINE_CLIENT"
}
```

The response includes an access token to use in the `Authorization` header for subsequent requests:


```
{
  "token": {
    "tokenType": "Bearer",
    "scope": "orders:write,orders:read",
    "expiresIn": 86400,
    "accessToken": "eyJ0eXAiOiJKV1Q..."
  },
  "status": "SUCCESS"
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-authResponseScope" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The list of scopes assigned to your API client.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-authResponseAccessToken" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The authentication bearer token needed to place API calls.</p></div></td>
    </tr>
Store the `accessToken` value for use in the following steps.

For more information about authentication, see [Authentication](apiDevGuide-authentication).


2. **Retrieve the available dining options**

Every order requires a dining option. Send a `GET` request to the `/config/v2/diningOptions` endpoint to retrieve the dining options configured for the location.

The response returns an array of dining options:


```
[
  {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption",
    "name": "Dine-in",
    "curbside": false,
    "behavior": "DINE_IN"
  },
  {
    "guid": "7c6843f3-db7d-4096-bdd2-4eefd99b900f",
    "entityType": "DiningOption",
    "name": "Takeout",
    "curbside": false,
    "behavior": "TAKE_OUT"
  },
  {
    "guid": "b1b10604-a8f9-4a21-ae86-7db974ee9dbf",
    "entityType": "DiningOption",
    "name": "Delivery",
    "curbside": false,
    "behavior": "DELIVERY"
  }
]
```

Note the `guid` of the dining option you want to use. This example uses "Dine-in" with GUID `23fc2559-fc37-46ce-a963-cc5fdb88af0c`.

For more information, see [Retrieving the available dining options](apiDevGuide-apiOrderTypeDetails#apiOrdersGetDiningOptions).


3. **Retrieve menu groups**

Menu items belong to menu groups. Send a `GET` request to the `/config/v2/menuGroups` endpoint to retrieve the menu groups.

The response returns an array of menu groups with their GUIDs and names. Note the `guid` of the menu group that contains the item you want to order.


```
[
  {
    "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
    "entityType": "MenuGroup",
    "externalId": null,
    "name": "Hamburgers",
    "menu": {
      "guid": "a9b6e0d4-5c3f-4e2a-b1d8-7f9e6c5a4b3d",
      "entityType": "Menu"
    },
    "visibility": "ALL",
    "menuItems": [
      {
        "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
        "entityType": "MenuItem"
      }
    ]
  },
  {
    "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
    "entityType": "MenuGroup",
    "externalId": null,
    "name": "Smoothies",
    "menu": {
      "guid": "a9b6e0d4-5c3f-4e2a-b1d8-7f9e6c5a4b3d",
      "entityType": "Menu"
    },
    "visibility": "ALL",
    "menuItems": [
      {
        "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
        "entityType": "MenuItem"
      }
    ]
  }
]
```


4. **Retrieve menu items**

Send a `GET` request to the `/config/v2/menuItems` endpoint to retrieve menu items.

The response includes each menu item's `guid`, `name`, and `menuGroups` array:


```
[
  {
    "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
    "entityType": "MenuItem",
    "externalId": null,
    "name": "Good Burger",
    "sku": "BURG-001",
    "plu": null,
    "visibility": "ALL",
    "orderableOnline": "YES",
    "menuGroups": [
      {
        "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
        "entityType": "MenuGroup"
      }
    ],
    "optionGroups": [
      {
        "guid": "47d73134-03da-4fb5-b564-5358b3b37d34",
        "entityType": "MenuOptionGroup"
      }
    ]
  },
  {
    "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
    "entityType": "MenuItem",
    "externalId": null,
    "name": "Smoothie",
    "sku": "SMO-002",
    "plu": null,
    "visibility": "ALL",
    "orderableOnline": "YES",
    "menuGroups": [
      {
        "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
        "entityType": "MenuGroup"
      }
    ],
    "optionGroups": []
  }
]
```

Note the `guid` of the menu items you want to order and the corresponding menu group GUIDs in the `menuGroups` array.

Menu items can belong to multiple menu groups. If a menu item belongs to more than one menu group, the `menuGroups`array contains multiple entries. When you submit an order, you must specify which menu group you're ordering from by including the correct menu group GUID in the `itemGroup` field. This is important because different menu groups can have different modifier groups, pricing, and other properties. The orders API validates that the menu item belongs to the specified menu group.


5. **Build your order JSON**

Using the GUIDs you collected, build your order JSON. The following example shows a simple dine-in order with two menu items:


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
            "entityType": "MenuGroup"
          },
          "quantity": 1
        },
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
            "entityType": "MenuGroup"
          },
          "quantity": 2
        }
      ]
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderDiningOption" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">diningOption</code> object specifies the dining option for the order such as dine-in or takeout. Use the GUID of a valid dining option from step 2.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderChecks" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">checks</code> array contains one or more <code className="font-mono text-sm">Check</code> objects. Most orders have a single check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderSelections" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">selections</code> array contains the menu items being ordered.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderItemGuid" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the menu item. Retrieve this from the <a href="https://doc.toasttab.com/openapi/configuration/overview/" className="">configuration API</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderItemGroup" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the menu group that contains this item. The item must belong to this group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderQuantity" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The quantity of this item being ordered.</p></div></td>
    </tr>

6. **Get the order price (optional but recommended)**

Before submitting the order, you can validate the order and retrieve pricing information by sending the order to the `/orders/v2/prices` endpoint.

Send a `POST` request to the `/orders/v2/prices` endpoint. Include your order JSON as the message body.

The response returns the order with calculated prices, taxes, and totals. This step also validates your order structure and confirms that all referenced entities exist:


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "amount": 25.00,
      "taxAmount": 2.19,
      "totalAmount": 27.19,
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
            "entityType": "MenuGroup"
          },
          "quantity": 1,
          "preDiscountPrice": 12.00,
          "price": 12.00,
          "tax": 1.05
        },
        {
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "9ec9573d-efa7-465e-a272-cc3171729a6c",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "500feeaa-5624-4e05-aa80-17b7e6025835",
            "entityType": "MenuGroup"
          },
          "quantity": 2,
          "preDiscountPrice": 13.00,
          "price": 13.00,
          "tax": 1.14
        }
      ],
      "appliedTaxes": [],
      "appliedServiceCharges": []
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-pricesResponseAmount" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The subtotal of the check before taxes.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-pricesResponseTax" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total tax amount for the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-pricesResponseTotal" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The total amount due including taxes.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-pricesResponseItemPrice" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The calculated price for each menu item selection.</p></div></td>
    </tr>
For more information, see [Getting check prices](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).


7. **Submit the order**

Send a `POST` request to the `/orders/v2/orders` endpoint to submit your order. Include your order JSON as the message body.

A successful response (HTTP 200) returns the complete `Order` object with generated GUIDs, calculated prices, and status information:


```
{
  "guid": "89488287-f259-435b-a654-0bc391596af0",
  "entityType": "Order",
  "source": "API",
  "approvalStatus": "NEEDS_APPROVAL",
  "businessDate": 20250115,
  "createdDate": "2025-01-15T14:30:00.000+0000",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "guid": "6e1bb8e0-534d-437f-bbad-0f08045f463e",
      "entityType": "Check",
      "amount": 25.00,
      "taxAmount": 2.19,
      "totalAmount": 27.19,
      "selections": [
        {
          "guid": "f520f731-8164-41a8-b261-23b9df3bf861",
          "entityType": "MenuItemSelection",
          "item": {
            "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
            "entityType": "MenuItem"
          },
          "itemGroup": {
            "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
            "entityType": "MenuGroup"
          },
          "quantity": 1,
          "price": 12.00,
          "tax": 1.05
        }
      ],
      "paymentStatus": "OPEN"
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderResponseGuid" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform generates a unique GUID for the order. Use this GUID to retrieve or modify the order later.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderResponseSource" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The orders API sets the <code className="font-mono text-sm">source</code> value to <code className="font-mono text-sm">API</code> for orders you submit.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderResponseStatus" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">approvalStatus</code> indicates the order's position in the fulfillment process. Depending on location configuration, the order may require approval before the kitchen receives it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderResponseCheckGuid" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Each check receives a unique GUID. Use this to add items or payments to the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderResponseAmount" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">amount</code>, <code className="font-mono text-sm">taxAmount</code>, and <code className="font-mono text-sm">totalAmount</code> values show the calculated check totals.</p></div></td>
    </tr>


## Adding modifiers to menu items

Many menu items have associated modifiers, such as toppings or preparation options. To add modifiers to a menu item selection, include a `modifiers` array within the selection.

First, retrieve the modifier options for a menu item by sending a `GET` request to the `/config/v2/menuOptionGroups/<em>&#123;guid&#125;</em>`endpoint.

The following example shows a selection with a modifier:


```
{
  "entityType": "MenuItemSelection",
  "item": {
    "guid": "8a3e1737-50ea-4e3c-bcc5-9477a7820bf4",
    "entityType": "MenuItem"
  },
  "itemGroup": {
    "guid": "1c6187fa-37e7-4fc6-b42a-2ec5f0e3c36f",
    "entityType": "MenuGroup"
  },
  "quantity": 1,
  "modifiers": [
    {
      "entityType": "MenuItemSelection",
      "item": {
        "guid": "58e6629f-5a1e-42f8-b6c7-4351d628b92d",
        "entityType": "MenuItem"
      },
      "optionGroup": {
        "guid": "47d73134-03da-4fb5-b564-5358b3b37d34",
        "entityType": "MenuOptionGroup"
      },
      "quantity": 1
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderModifiers" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">modifiers</code> array contains modifier selections that apply to the parent menu item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderModifierItem" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the modifier item (for example, a topping or add-on option).</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-firstOrderOptionGroup" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the option group that contains the modifier. This is required for modifier selections.</p></div></td>
    </tr>
For more information, see [Applying modifiers to orders](apiDevGuide-apiSpecifyingModifiersAndInstructions#apiApplyingModifiers).

## Error handling

When submitting orders, you may encounter the following HTTP status codes:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Status Code</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Resolution</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">200</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Success</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The API created the order successfully. The response body contains the complete order details.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">400</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Bad Request</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The request contains invalid data. Check the error message for details. Common causes include invalid GUIDs, missing required fields, or items that do not belong to the specified menu group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">401</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unauthorized</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The access token is missing, invalid, or expired. Obtain a new access token and retry the request.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">403</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Forbidden</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The API client does not have access to the location or does not have the required scope (<code className="font-mono text-sm">orders.orders:write</code>).</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">404</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Not Found</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A referenced entity (such as a menu item or dining option) does not exist or belongs to a different location.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">413</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Payload Too Large</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of checks in the order exceeds the allowed limit.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">415</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unsupported Media Type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The request does not include the <code className="font-mono text-sm">Content-Type: application/json</code> header.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">500</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Internal Server Error</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An unexpected error occurred. Note the <code className="font-mono text-sm">requestId</code> from the error response and contact Toast support if the issue persists.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

### Common error messages

The following table describes common error messages and their resolutions:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Error Message</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Resolution</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Could not parse as Order object</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Your request body contains malformed JSON or invalid data types. Common causes include missing or extra commas, unclosed brackets or braces, unquoted strings, or numeric values that exceed allowed limits. Validate your JSON syntax before submitting the request.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item (<code className="font-mono text-sm">item GUID</code>) does not belong to the group (<code className="font-mono text-sm">item group GUID</code>)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu item you specified is not part of the referenced menu group. Verify the item's menu group by checking the <code className="font-mono text-sm">menuGroups</code> array in the menu items response. If the menu item belongs to multiple menu groups, ensure you're using the correct menu group GUID from the <code className="font-mono text-sm">menuGroups</code> array.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Referenced entity (type=MenuItem) must contain either a GUID or MultiLocationId</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A menu item in your request is missing its GUID. Ensure every <code className="font-mono text-sm">item</code> object contains a valid <code className="font-mono text-sm">guid</code> value.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Referenced entity (type=DiningOption) must contain a GUID</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">diningOption</code> object is missing its GUID. Retrieve valid dining option GUIDs from the configuration API.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Next steps

After successfully submitting your first order, you can explore additional capabilities of the orders API:

- **Add payments** - Add payment information to close the check. For more information, see [Adding payments to an existing check](apiDevGuide-apiAddingPaymentsToACheck).


- **Create different order types** - Learn about creating takeout, delivery, and curbside orders. For more information, see [Order details based on the order dining option](apiDevGuide-apiOrderTypeDetails).


- **Apply discounts** - Add discounts to items or checks. For more information, see [Working with order discounts](apiDevGuide-apiDiscountingOrders).


- **Schedule future orders** - Create orders to be fulfilled at a specific date and time. For more information, see [Scheduling future orders](apiDevGuide-orders_api_future_orders).


- **Retrieve order details** - Get information about existing orders. For more information, see [Getting detailed information about one order](apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder).


- **Void an order** - Cancel an order that was accidentally placed or is no longer needed. For more information, see [Void an order](apiDevGuide-apiVoidOrder).



For complete API reference documentation, see the [orders API reference](https://doc.toasttab.com/openapi/orders/overview/).

