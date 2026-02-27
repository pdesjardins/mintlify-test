---
title: "Marketplace facilitator orders"
id: apiMarketplaceFacilitatorOrders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiUpdatingDeliveryInfoForAnOrder.md
previousSectionTitle: "Updating delivery information for an order"
nextSectionFile: apiDevGuide-apiOrdersDeferredMenuItems.md
nextSectionTitle: "Deferring menu items"
externalReferences: [https://doc.toasttab.com/openapi/menus/operation/menusGet/]
excerpt: "If your organization is designated a marketplace facilitator by a taxation authority, then when you use the orders API to create orders, you can either:"
procedures: 0
codeExamples: 0
---

If your organization is designated a marketplace facilitator by a taxation authority, then when you use the orders API to create orders, you can either:

- Allow the Toast platform to calculate and populate the item prices and tax amounts based on the restaurant configuration.


- Submit the item prices and tax amounts. You typically use this option if you have a tax partner that calculates the tax for you.

The prices that you provide should match the menu prices from the restaurant configuration.



In both cases, you also indicate whether you collect and remit taxes on behalf of the Toast restaurant. Restaurant employees use Toast platform analytics and reports to get information about the tax amounts that a marketplace facilitator paid on their behalf.

For more information about marketplace facilitator orders in the Toast platform, see [Marketplace facilitator tax payments](adminGuide-adminMarketplaceFacilitatorTaxPayments).

## Overview of the order creation process for a marketplace facilitator order

A marketplace facilitator uses the following process to create an order and remit tax payments.

1. As a marketplace facilitator, your organization receives a guest order to be fulfilled at a Toast restaurant location.


2. You use the orders API to get accurate price and tax amount information for the order. For more information, see [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).


3. You receive payment for the order from the restaurant guest.


4. You transmit the order information to the Toast platform for fulfillment at the restaurant location.

When you create a Toast platform order as a marketplace facilitator, you can either:

- Allow the Toast platform to calculate and populate the prices and tax amounts. For more information, see [Allowing the Toast platform to calculate the prices and tax amounts](apiDevGuide-apiMarketplaceFacilitatorOrders#apiUsingToastPlatformPricesMarketplaceFacilitatorOrders).


- Provide the prices and tax amounts for the items in the order. For more information, see [Specifying prices and tax amounts](apiDevGuide-apiMarketplaceFacilitatorOrders#apiSpecifyingPricesMarketplaceFacilitatorOrders).



You also indicate whether you remit tax amounts on behalf of the restaurant. The `MarketplaceFacilitatorTaxInfo` object provides information about whether you remit taxes.

If you specify the order prices and tax amounts, then `MarketplaceFacilitatorTaxInfo` also includes the order tax amounts.


5. If you do remit taxes, then you remit the tax amounts to taxing authorities on behalf of the restaurant.


6. You deliver order payment to the restaurant location.



## Allowing the Toast platform to calculate the prices and tax amounts

When you create a marketplace facilitator order, you can have the Toast platform calculate and populate the prices and tax amounts when the order is created.

For marketplace facilitator orders where the Toast platform calculates the prices and tax amounts, you include a `MarketplaceFacilitatorTaxInfo` object that contains a single value, `facilitatorCollectAndRemitTaxOrder`.

- If you remit taxes on behalf of the restaurant, set `facilitatorCollectAndRemitTaxOrder` to `true`.


- If you do not remit taxes on behalf of the restaurant, set `facilitatorCollectAndRemitTaxOrder` to `false`.



The presence of the `facilitatorCollectAndRemitTaxOrder`value indicates that the Toast platform populates the prices and tax amounts. Do not provide an `externalPriceAmount` value for any of the menu item selections.

The `Order` object in the following example creates a marketplace facilitator order that where the Toast platform populates the price and tax amounts. In this example, the marketplace facilitator does not remit the taxes.

**Example 2.7. Marketplace facilitator order where the Toast platform populates the prices and tax amounts**


```
{
  "entityType": "Order",

    [contents omitted]

  "marketplaceFacilitatorTaxInfo": {
    "facilitatorCollectAndRemitTaxOrder": false
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],

    [contents omitted]

    }
  ]
}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e183ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Contains information about the taxes that a marketplace facilitator organization remits on behalf of a Toast restaurant.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e185ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Indicates whether the marketplace facilitator organization will pay the tax amounts for an order on behalf of the restaurant that fulfills the order. In this example, the marketplace facilitator will not pay the tax amounts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e187ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If you include the <code className="font-mono text-sm">facilitatorCollectAndRemitTaxOrder</code> value, do not specify <code className="font-mono text-sm">externalPriceAmount</code> for menu item selections in the order.</p></div></td>
    </tr>
  
## Specifying prices and tax amounts

When you create a marketplace facilitator order, you can provide the prices and tax amounts for the order. You typically select this option when you have a tax partner that calculates the tax amounts for you.

When you choose this option, make sure that the prices that you provide are consistent with the restaurant menu prices. You can get the prices for the current order (see [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices)), or get the prices from the menu configuration (see [Get menus](https://doc.toasttab.com/openapi/menus/operation/menusGet/)).

Service charges and discounts are not supported when your integration provides prices and tax amounts for the order. Including an `appliedServiceCharges` or `appliedDiscounts` object in your order submission will cause the order to fail and return an error. For more information about service charges, see [Service charges for checks](apiDevGuide-apiOrderPrices#apiServiceCharges). For more information about discounts, see [Working with order discounts](apiDevGuide-apiDiscountingOrders).

In a marketplace facilitator order that specifies prices and tax amounts:

- For each menu item selection, provide the item price as the value of `externalPriceAmount`.

For menu items that use size pricing, specify the item price as the value of `externalPriceAmount` for the size-price modifier. For the parent item, set `externalPriceAmount` to `0.00`. For more information, see [Specifying size prices in marketplace facilitator orders](apiDevGuide-apiMarketplaceFacilitatorOrders#apiSpecifyingPricesMarketplaceFacilitatorOrdersSizePrice).


- In the `MarketplaceFacilitatorTaxInfo` object for the order, include a `taxes` array of `AppliedTaxRate` objects.

You provide an `AppliedTaxRate` object for each type of tax that applies to the order. In each `AppliedTaxRate`object:

- Set `name` to the name of the tax. This value is not used outside of the Toast API. It can be any value that is useful for you.


- Set `taxAmount` to the total amount for the tax across all of the checks and menu item selections.


- Use the `facilitatorCollectAndRemitTax` value to indicate whether you will remit the amount for that tax.

If you will remit the tax amount, set `facilitatorCollectAndRemitTax` to `true`.

If you will not remit the tax amount, set `facilitatorCollectAndRemitTax` to `false`.





The `Order` object in the following example creates a marketplace facilitator order that provides the prices and tax amounts for the order. The marketplace facilitator remits the tax amount for one of the taxes, but does not remit the tax amount for the other tax.

**Example 2.8. Marketplace facilitator order that specifies prices and tax amounts**


```
{
  "entityType": "Order",

    [contents omitted]

  "marketplaceFacilitatorTaxInfo": {
    "taxes": [
      {
        "name": "SomeTax",
        "taxAmount": 3.21,
        "facilitatorCollectAndRemitTax": true
      },
      {
        "name": "SomeOtherTax",
        "taxAmount": 2.34,
        "facilitatorCollectAndRemitTax": false
      }
    ]
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "externalPriceAmount": 123.45,
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],

    [contents omitted]

    }
  ]
}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e245ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Contains information about the taxes that a marketplace facilitator organization remits on behalf of a Toast restaurant.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e247ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include the <code className="font-mono text-sm">taxes</code> value if you specify prices and tax amounts for a marketplace facilitator order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e249ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specifies the total tax amount for this tax type across all of the checks and menu item selections in the order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e251ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The value <code className="font-mono text-sm">true</code> indicates that the marketplace facilitator organization will pay this tax amount for the order on behalf of the restaurant that fulfills the order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e253ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The value <code className="font-mono text-sm">false</code> indicates that the marketplace facilitator organization will not pay this tax amount for the order on behalf of the restaurant that fulfills the order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e256ED70EBFB-66D2-4C17-9A10-C756EEEBD261" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specifies the price for this menu item selection. To specify prices and tax amounts for a marketplace facilitator order, include the <code className="font-mono text-sm">externalPriceAmount</code> value for each menu item selection. The specified price should correspond to the price that is configured in the restaurant menu.</p></div></td>
    </tr>
  
## Specifying size prices in marketplace facilitator orders

Marketplace facilitator orders can include menu items that use size pricing. For information about menu items with size pricing, see [Menu item with a size price](apiDevGuide-apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2#apiMenuItemWithASizePrice_V2).

When you create a marketplace facilitator order and specify prices, you include an `externalPriceAmount` for all of the menu item selections. For size-priced items:

- Set the `externalPriceAmount` for the parent item to `0.0`.


- Include the actual price of the item in the `externalPriceAmount` value of the size modifier.



The `Order` object in the following example creates a marketplace facilitator order with a menu item selection that uses size pricing.

**Example 2.9. Marketplace facilitator order that specifies a size-based price for a menu item selection**


```
{
  "entityType": "Order",

    [contents omitted]

  "marketplaceFacilitatorTaxInfo": {
    "taxes": [
      {
        "name": "SomeTax",
        "taxAmount": 0.10,
        "facilitatorCollectAndRemitTax": true
      }
    ]
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "externalPriceAmount": 0,
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802"
          },
          "quantity": 1,
          "modifiers": [
            {
              "externalPriceAmount": 10.00,
              "entityType": "MenuItemSelection",
              "optionGroup": {
                "guid": "f315fe4c-a74d-49c1-b117-fe4494bb456e"
              },
              "item": {
                "entityType": "MenuItem",
                "guid": "4382f595-8f01-4d97-b3ec-8fe91da963a1"
              },
              "quantity": 1
            }
          ]
        }
      ],

    [contents omitted]

    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e390FF8D1928-D00D-4A66-8C03-09C0F1A6A166" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">When you specify tax amounts for an order, you also specify the prices for items in the order. For more information, see <a href="apiDevGuide-apiMarketplaceFacilitatorOrders#apiSpecifyingPricesMarketplaceFacilitatorOrders" className="">Specifying prices and tax amounts</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e392FF8D1928-D00D-4A66-8C03-09C0F1A6A166" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For items that use size prices, set <code className="font-mono text-sm">externalPriceAmount</code> for the parent item to <code className="font-mono text-sm">0.00</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e394FF8D1928-D00D-4A66-8C03-09C0F1A6A166" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the size-priced parent item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#selectedSizePriceMarker" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the selected size modifier for the size-priced item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e396FF8D1928-D00D-4A66-8C03-09C0F1A6A166" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the Size modifier group that is used for size pricing.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e398FF8D1928-D00D-4A66-8C03-09C0F1A6A166" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the selected modifier for the item that uses size pricing. Represents a value such as Small, Medium, or Large.</p></div></td>
    </tr>
  
