---
title: "Order prices"
id: apiOrderPrices
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiOrdersPackagingPreferences.md
previousSectionTitle: "Packaging preferences"
nextSectionFile: apiDevGuide-apiDiscountingOrders.md
nextSectionTitle: "Working with order discounts"
externalReferences: [https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/AppliedServiceCharge/]
excerpt: "Order price information includes menu item prices, service charges, and taxes."
procedures: 0
codeExamples: 0
---

Order price information includes menu item prices, service charges, and taxes.

## Getting check prices before you submit an order

Before you can `POST` an order to the `/orders`endpoint, you must first obtain the order price information for the order. For an overview of the order creation process, including the step to obtain the order prices, see [Order creation process for the orders API](apiDevGuide-apiCreatingOrders#apiOrdersCreationProcess).

To get the price information, you send a `POST` request to the `/prices` endpoint of the orders API. The request contains an `Order` object with the information about the order.

The `/prices` endpoint is the only reliable and supported way to determine the payment amount for a check. If you `POST` an order with a payment amount that does not match the results from the `/prices` endpoint, then restaurant employees must manually handle the underpayment or overpayment during order fulfillment.

### Example Order object for a request to the /prices endpoint

The following example shows a JSON `Order` object to `POST` to the `/prices` endpoint. The order contains one check with a single menu item.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c"
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53"
          },
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
          },
          "quantity": 1,
          "modifiers": []
        }
      ]
    }
  ]
}
```



    <tr>
      <td>[(1)](#co-d1e193C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The GUID of the dining option for the order. For example, the dining option for an order might be dine in, takeout, or delivery.<br/>For some dining options, you might need to include additional information. For example, for takeout orders, you provide information about the guest who will pick up an order.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e195C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The GUID of the menu group for the menu item selected for this check. For example, a menu group might be "appetizers" or "drinks."</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e197C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The GUID of the menu item selected for this check. For example, a menu item might be "spinach dip" or "lemonade."</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e199C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The quantity of the menu item selection. For example, to order three lemonades, a check includes a "lemonade" menu item selection with a quantity of three.</td>
    </tr>
### Response data from the /prices endpoint

The response from the `/prices` endpoint fills in the amounts, including prices and taxes, for the menu item selections and checks. For a description of the amount fields in the `Order`object, see [Order amounts](apiDevGuide-apiOrdersOrderObjectSummary#apiOrderObjectAmounts).

The following example shows the response data returned by the `/prices` endpoint of the orders API.


```
{
  "guid": null,
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": null,
  "server": null,
  "deliveryInfo": null,
  "serviceArea": null,
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "API",
  "voidDate": null,
  "openedDate": "2017-05-09T16:24:09.881+0000",
  "duration": null,
  "businessDate": 20170509,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": null,
      "entityType": "Check",
      "externalId": null,
      "displayNumber": null,
      "amount": 8.99,
      "tabName": null,
      "taxExempt": false,
      "payments": [],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2017-05-09T16:24:09.883+0000",
      "totalAmount": 9.55,
      "selections": [
        {
          "guid": null,
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "preDiscountPrice": 8.99,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Crab Cakes",
          "appliedDiscounts": [],
          "tax": 0.56,
          "modifiers": [],
          "seatNumber": -1,
          "voidDate": null,
          "fulfillmentStatus": "NEW",
          "salesCategory": null,
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": null,
          "preModifier": null,
          "price": 8.99,
          "modifiedDate": null,
          "voided": false,
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.56,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": null,
      "closedDate": null,
      "deletedDate": null,
      "modifiedDate": null,
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.56,
      "appliedServiceCharges": [],
      "paymentStatus": "OPEN",
      "customer": null
    }
  ],
  "deleted": false,
  "paidDate": null,
  "closedDate": null,
  "deletedDate": null,
  "restaurantService": null,
  "modifiedDate": null,
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": null,
  "table": null
}
```



    <tr>
      <td>[(1)](#co-d1e217C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The price of the check after discounts, not including tax.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e219C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The price of the check after discounts, including tax.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e221C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The price of the menu item selection, before discounts.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e223C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The tax amount applied to the menu item selection.</td>
    </tr>
    <tr>
      <td>[(5)](#co-d1e225C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The menu item selection, including discounts, quantity adjustments, and modifiers.</td>
    </tr>
    <tr>
      <td>[(6)](#co-d1e228C93B886C-2601-45C3-B008-CB13B0107A92)</td>
      <td>The tax amount applied to the menu item selection.</td>
    </tr>
## Including open price menu items in an order

You can create orders that include open price menu items. When you create the order, you specify the price of the menu item.

### About open price menu items

*Open price* menu items allow restaurant employees or your integration client software to set the price of a configured menu item. For example, the price of a seafood menu item might vary each day based on the current market price. Instead of changing the price in the menu each day, the item is configured as an open price menu item, and the price is specified when the order is placed. You can `POST` orders with open price menu items with the orders API.

Open price menu items are different from *open*menu items, which allow restaurant employees to set both the name AND the price of the item. You cannot `POST` orders with open menu items with the orders API.

To verify that a menu item is an open price menu item, check the `pricingStrategy` value of the `MenuItem` object in the menus API response data. If the `pricingStrategy` value is `OPEN_PRICE`, then the menu item is an open price menu item.

The following example `MenuItem` object is for an open price menu item:


```
...
"menuItems": [
  {
    "entityIdentifier": "0/2/0/e19e5a1c-2b52-42ad-935e-568cd2a333dc",
    "name": "Soda",
    "guid": "e19e5a1c-2b52-42ad-935e-568cd2a333dc",
    "masterId": 200000000070407140,
    "description": "",
    "image": null,
    "visibility": [
      "POS",
      "KIOSK",
      "TOAST_ONLINE_ORDERING"
    ],
    "price": null,
    "pricingStrategy": "OPEN_PRICE",
    "pricingRules": null,
...
```

### How to set the price of an open price item

To set the price for an open price item, in the `Selection` object for the open price item, set the `openPriceAmount` value to the currency amount of the item price. `openPriceAmount` is the price of a single item before any quantity, taxes, discounts, and modifier adjustments are applied. For example, a restaurant configures a seafood special as an open price item. `openPriceAmount` is always the price of one seafood special, even if a guest orders more than one seafood special.

If you do not provide an `openPriceAmount` value for an open price menu item, the orders API sets the price to 0.00.

Include the open price items in the request body that you send to the `/prices` endpoint to [get the check prices](apiDevGuide-apiOrderPrices#apiGettingCheckPrices). For open price items, the call to the `/prices` endpoint returns the calculated tax for the item. The orders API calculates the tax based on the value of `openPriceAmount`.

### Example Order object with an open price item

The following example shows a JSON `Order` object that contains a check with a single open price menu item.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c"
  },
  "checks": [
    {
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "4c842ed6-ae99-425a-a343-390ab0e081d3"
          },
          "item": {
            "guid": "e19e5a1c-2b52-42ad-935e-568cd2a333dc"
          },
          "quantity": 1,
          "openPriceAmount": 4.50,
          "modifiers": []
        }
      ]
    }
  ]
}
```



    <tr>
      <td>[(1)](#co-d1e18994C2B4C02-01BB-46CE-B543-1A815822BD0D)</td>
      <td>The GUID of the menu group for the selected open price menu item.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e19014C2B4C02-01BB-46CE-B543-1A815822BD0D)</td>
      <td>The GUID of the selected open price menu item.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e19034C2B4C02-01BB-46CE-B543-1A815822BD0D)</td>
      <td>The quantity for the menu item selection.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e19054C2B4C02-01BB-46CE-B543-1A815822BD0D)</td>
      <td>A currency amount that sets the price for the open price menu item. The amount reflects the price before the quantity, taxes, discounts, and modifier adjustments are applied.</td>
    </tr>
### Open price values in orders API responses

Only include the `openPriceAmount` when you add an open price menu item to an order. `openPriceAmount` is not returned in orders API responses.

The orders API uses the `openPriceAmount` value to populate the `receiptLinePrice` value for the menu item selection.

## Service charges for checks

You can apply general upcharges, or service charges, to checks when you create an order in the orders API. Some examples of service charges are a delivery fee for delivery orders, or a gratuity service charge based on the amount of the check.

Before you can apply a service charge, restaurants must configure the service charge in Toast Web. You then use the service charge GUID to add the service charge to the check. To retrieve the service charge GUID, you can use the configuration API.

For more information about service charges and how restaurants configure them, see [Service charge overview](adminGuide-adminServiceChargeOverview) in the *Toast Platform Guide*.

### Getting the available service charges

To get the available service charges, send a `GET`request to the `serviceCharges` endpoint of the configuration API. For more information about retrieving available service charges, see [Get service charges](https://doc.toasttab.com/openapi/configuration/operation/serviceChargesGet/) in the *Toast API reference*.

The response provides detailed information about each service charge, including:



**`guid`**
: The GUID that the Toast platform generated for the service charge.

You use the GUID to add the service charge to a check.



**`amountType`**
: The amount type for the service charge. `amountType` is one of the following:

- `PERCENT` - The service charge is a specified fixed percentage of the check. For example, the service charge is always 10% of the check.


- `FIXED` - The service charge is a specified fixed amount. For example, the service charge is always $5.00.


- `OPEN` - The service charge does not have a specified amount. You provide the amount when you add the service charge to the check.





**`criteria`**
: The eligibility criteria for the service charge. For orders placed using a Toast POS device, the criteria determines when to automatically apply a service charge.

For orders from the orders API, service charges are not added automatically. However, the orders API does use the criteria to validate the added service charges. For example, if you add a delivery service charge to a takeout order, the orders API returns an error.

The criteria includes whether to apply the service charge based on:

- The dining behavior. Service charges can be assigned to specific dining behaviors, including `delivery`, `takeout`, and `dineIn`. When a dining behavior is specified for a service charge, the order's dining behavior must match the service charge's dining behavior. Service charges can also have no dining behavior assigned. When no dining behavior is assigned to a service charge, orders with any dining behavior can be submitted using this service charge.


- For delivery orders, the delivery distance.


- The pre-discount amount of the check. Service charges might apply to orders that are either larger or smaller than a specified amount.







### How to apply service charges to a check

To apply service charges to a check, include the `appliedServiceCharges` value in the `Check` object. Include a `serviceCharge` value for each service charge that applies to the check.

The orders API does not automatically add any service charges. You must add all of the applicable service charges. If the order does not meet the service charge criteria, the orders API rejects the order.

In each `serviceCharge` value:

- Set `guid` to the Toast platform GUID of the service charge.


- For an open service charge, include a `chargeAmount`value to set the amount of the service charge.

Do not provide a `chargeAmount` for `FIXED` or `PERCENT` service charges. The orders API ignores `chargeAmount` values for `FIXED` or `PERCENT` service charges.



### Example appliedServiceCharges value

The following example shows an `appliedServiceCharges`value that applies an open service charge to a check.


```
"appliedServiceCharges": [
  {
   "serviceCharge": {
     "guid": "0a81611c-b424-4586-9539-f33286c0211a"
   },
   "chargeAmount": 3.45
  }
]
```



    <tr>
      <td>[(1)](#apiServiceChargeAmount)</td>
      <td>You include `chargeAmount` for `OPEN`service charges. Do not include `chargeAmount` for `FIXED` or `PERCENT` service charges.</td>
    </tr>
### Identifying service charge types

The `AppliedServiceCharge` object includes a `serviceChargeCategory` field that identifies the type of service charge. This value is response-only and helps you filter or categorize service charges in your reporting integrations.

The `serviceChargeCategory` field can have the following values:



**`SERVICE_CHARGE`**
: The default type for a service charge. This includes standard service charges such as delivery fees, gratuity, and other general upcharges.



**`CREDIT_CARD_SURCHARGE`**
: A fee assessed only on payment transactions that use a credit card. The `paymentGuid` field on the `AppliedServiceCharge` object contains the GUID of the payment this surcharge is linked to.



**`FUNDRAISING_CAMPAIGN`**
: A service charge associated with fundraising. When guests make donations through the Toast fundraising feature, the donation amount appears as a service charge with this category.

When building sales reports or calculating service charge totals, you may want to exclude service charges where `serviceChargeCategory` is `FUNDRAISING_CAMPAIGN` from your calculations. For more information about filtering fundraising transactions, see [Building a sales report](devCookbook-apiIntegrationChecklistAccounting).



**`CASH_ROUNDING`**
: A service charge for cash rounding.





If the `serviceChargeCategory` value is missing or `null`, treat the service charge as a regular `SERVICE_CHARGE` and include it in your calculations.

For complete API reference information about the `AppliedServiceCharge` object and the `serviceChargeCategory` value, see [AppliedServiceCharge](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/AppliedServiceCharge/)in the Toast API reference.

## Working with taxes

When calculating taxes, the orders API uses rounding rules to round the tax amounts to valid denomination values.

Menu items, checks, and service charges are also configured to indicate whether they are taxable.

### Tax rounding

When it calculates taxes and check prices, the orders API uses the following rounding rules to produce valid denomination values.

- The orders API rounds all currency amounts to two decimal places.


- When the orders API applies a percent tax rate, it uses the rounding algorithm that is configured for that percent tax rate.

For example, depending on the configured rounding option, the orders API rounds a tax amount of $1.235 down to $1.23 or up to $1.24. For more information, see [Rounding options](adminGuide-adminPercentTaxRates#roundingOptions) in the *Toast Platform Guide*.


- To calculate a check price, the orders API first rounds the item prices, including the tax amounts. It then sums the rounded item prices.





> **Important**
> 
> This description of the orders API rounding method does not guarantee that orders API client software can accurately calculate check prices. The price of a check includes several factors in addition to the item prices and rounded tax amounts.
> The `/prices` endpoint is the only reliable and supported way to determine the payment amount for a check. See [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).
> If you `POST` an order with a payment amount that does not match the results from the `/prices`endpoint, then restaurant employees must manually handle the underpayment or overpayment during order fulfillment.


### Tax exemptions for menu items, checks, and service charges

The following settings control whether items, checks, and service charges are taxable:



****nontaxable flag for menu items****
: The nontaxable flag is a configuration setting that applies to menu items. It is not present in the API.

Indicates that an item is never taxable. For example, in some states or provinces, the sales tax does not apply to confectionery purchases.



****`taxExempt` property for checks****
: The `taxExempt` property of a check is present in the API.

Indicates whether that particular check, rather than the items or service charges on it, is exempt from taxation.

For example, an order placed by a non-profit or government entity might be exempt from taxes.



****`taxable` property for service charges****
: The `taxable` property of an `AppliedServiceCharge` is present in the API.

Indicates whether a service charge is taxable.

For example, tax rates can apply to delivery charges.





