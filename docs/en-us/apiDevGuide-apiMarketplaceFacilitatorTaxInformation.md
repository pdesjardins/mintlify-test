---
title: "Marketplace facilitator tax information"
id: apiMarketplaceFacilitatorTaxInformation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiOrdersNetSalesCalculation.md
previousSectionTitle: "Calculating net sales using the orders API"
nextSectionFile: apiDevGuide-apiOrdersFindingAnOrderGuid.md
nextSectionTitle: "Finding an order or check GUID"
excerpt: "For orders submitted by a marketplace facilitator, the prices and tax amounts are either populated by the Toast platform, or provided by the marketplace facilitator."
procedures: 0
codeExamples: 0
---

For orders submitted by a marketplace facilitator, the prices and tax amounts are either populated by the Toast platform, or provided by the marketplace facilitator.

## About marketplace facilitators

For Toast platform restaurants, a marketplace facilitator is a business that:

- Takes guest orders, processes guest payments, and then directly submits those orders to a Toast platform restaurant for fulfillment.


- Is required by a taxing authority to pay tax amounts for the orders they process.



For example, a restaurant ordering service such as Grubhub™, Uber Eats™, or Doordash® accepts orders for a large number of restaurants. The service might take guest orders and payments and then submit the order to the Toast platform for fulfillment at a Toast platform restaurant. The ordering service receives the guest payment and then remits the applicable tax amounts.

For Toast Takeout and Toast Local orders, Toast acts as the marketplace facilitator and remits tax amounts on behalf of the restaurant. In these cases, Toast pays the tax amounts for the orders.

For more information about marketplace facilitator orders in the Toast platform, see [Marketplace facilitator tax payments](adminGuide-adminMarketplaceFacilitatorTaxPayments).

## Indicating the source of prices and tax amounts

The orders API return data indicates whether the prices and tax amounts were populated by the Toast platform, or specified by the marketplace facilitator. It also indicates whether the marketplace facilitator collected and remitted the taxes on behalf of the restaurant.

In the `appliedTaxes` object, the `type` value indicates whether the value came from the Toast platform or was calculated by the marketplace facilitator:

- If `type` is `EXTERNAL`, then the prices and tax amounts were provided by the marketplace facilitator. The prices should match the current menu prices for the restaurant. The tax amounts are usually calculated by a tax partner.


- If `type` is any value other than `EXTERNAL`, then the prices and tax amounts were calculated by the Toast platform.



The `facilitatorCollectAndRemitTax` value indicates whether the marketplace facilitator remitted the tax on behalf of the restaurant. If set to `true`, then the marketplace facilitator remitted the tax.

### Reviewing marketplace facilitator tax calculations

To review the tax calculation for a marketplace facilitator, refer to the `AppliedTaxRate` object. This object contains the following details:

- `entityType`: The type of object.


- `name`: The name of the tax rate. For marketplace facilitator taxes, this field is always Toast Marketplace Facilitator Taxes.


- `rate`: The tax rate. This value can be a fixed amount, percentage or `null`.


- `taxAmount`: The tax amount applied.


- `type`: The tax rate type. Possible tax types for marketplace facilitators are: 

- FIXED: The tax rate is a fixed amount that is calculated by a third-party provider.


- EXTERNAL: The tax is for a marketplace facilitator order, and the marketplace facilitator organization, such as a third-party ordering platform, calculated the tax amount.




- `displayName`:The name of the tax rate as it appears on guest receipts.


- `jurisdiction`: The area the tax rate applies to, such as a state or province, for reporting purposes.


- `facilitatorCollectAndRemitTax`: Indicates whether the marketplace facilitator remitted the tax amount on behalf of the restaurant. If set to `true`, the marketplace facilitator remitted the tax. If set to `false` or `null`, the marketplace facilitator did not remit the tax.



### Calculating total marketplace facilitator tax paid

To calculate the total marketplace facilitator tax amount that was remitted on behalf of a restaurant for an order, sum the `taxAmount` values from all `AppliedTaxRate`objects where `facilitatorCollectAndRemitTax` is `true`.

You need to check all `AppliedTaxRate` objects in the order, which can be found in:

- The `appliedTaxes` array on each `MenuItemSelection` object in each check.


- The `appliedTaxes` array on each `AppliedServiceCharge` object, if service charges are present.



For example, to calculate the total marketplace facilitator tax paid for an order:

1. Iterate through all checks in the order.


2. For each check, iterate through all menu item selections and service charges.


3. For each `AppliedTaxRate` object where `facilitatorCollectAndRemitTax` is `true`, add the `taxAmount` value to your total.





> **Note**
> 
> For some Toast Takeout and Toast Local orders, Toast remits the tax amounts on behalf of the restaurant. In these cases, the `facilitatorCollectAndRemitTax` value will be `true` for taxes that Toast remitted.


The following example shows how to identify marketplace facilitator taxes that were remitted:


```
{
  "checks": [
    {
      "selections": [
        {
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "name": "State Tax",
              "taxAmount": 0.31,
              "facilitatorCollectAndRemitTax": true
            },
            {
              "entityType": "AppliedTaxRate",
              "name": "Local Tax",
              "taxAmount": 0.15,
              "facilitatorCollectAndRemitTax": true
            }
          ]
        }
      ]
    }
  ]
}
```

In this example, the total marketplace facilitator tax paid would be `0.46` (the sum of `taxAmount` values where `facilitatorCollectAndRemitTax` is `true`). 

## Example return data with Toast platform prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the Toast platform calculated and populated the prices and tax amounts.


```
{
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",

     [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "26aa5680-3233-4d3b-9504-051a622ae76d",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "rate": 0.0625,
              "name": "State Tax",
              "taxAmount": 0.31,
              "type": "PERCENT",
              "facilitatorCollectAndRemitTax": true
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },

          [contents omitted]

          "receiptLinePrice": 5,
          "tax": 0.31,

          [contents omitted]

        }
      ],

      [contents omitted]

      "taxAmount": 0.31,

      [contents omitted]

   }
  ],

  [contents omitted]

}
```



(1) Any value other thanEXTERNALindicates that the marketplace facilitator used the prices and tax amounts calculated by the Toast platform for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

## Example return data with specified prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the marketplace facilitator specifies the prices and tax amounts.

The prices should correspond to the prices from the restaurant menu. The tax amounts are usually calculated by a tax partner.

The marketplace facilitator submits those prices and tax amounts to the Toast platform.


```
{
  "guid": "cdef26f4-68bd-42a1-a1e0-be43c4fb52f0",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",
 
      [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "688cdc21-ab92-427e-9837-c981cc2d55c5",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "a19eaf97-c0b9-47bf-9af2-ed833c3e4051",
                "entityType": "TaxRate"
              },
              "rate": null,
              "name": "Marketplace Facilitator Taxes Paid",
              "taxAmount": 0.1,
              "type": "EXTERNAL",
              "facilitatorCollectAndRemitTax": true
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },
 
          [contents omitted]

          "receiptLinePrice": 20,

          [contents omitted]

        }
      ],

     [contents omitted]

      "taxAmount": 0.1,

     [contents omitted]

    }
  ],

  [contents omitted]

}
```



(1) The value EXTERNAL indicates that the marketplace facilitator specified the prices and tax amounts for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

