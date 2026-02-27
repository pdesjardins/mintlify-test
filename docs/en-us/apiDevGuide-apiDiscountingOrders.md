---
title: "Working with order discounts"
id: apiDiscountingOrders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiOrderPrices.md
previousSectionTitle: "Order prices"
nextSectionFile: apiDevGuide-apiOrdersRevenueCenters.md
nextSectionTitle: "Providing revenue center information for an order"
externalReferences: [https://central.toasttab.com/s/article/BOGO-Buy-One-Get-One-Discounts, https://doc.toasttab.com/openapi/loyalty/operation/yourEndpointNamePost/]
excerpt: "A discount is a reduction to the price of a check or a menu item selection. You can include discounts when you create an order, and add discounts to an existing order."
procedures: 0
codeExamples: 0
---

A discount is a reduction to the price of a check or a menu item selection. You can include discounts when you create an order, and add discounts to an existing order.

To configure the available discounts at your restaurant, you use the Discounts screen of Toast Web. For more information about discounts in the Toast platform, see [Using the Discounts page](adminGuide-adminAvailableDiscounts).

## Types of discounts

Restaurants configure each discount to indicate whether it can be applied to a menu item selection or to a check. The discount specifies the eligibility requirements for the discount, and indicates how to determine the discount amount.

The Toast platform supports the following types of discounts:



****Fixed discount****
: **Can apply to:** Menu item or check.

A fixed discount removes either a specific percent or a specific currency amount from the menu item or check.

When a percent discount results in a fraction of a penny, the Toast platform applies half even rounding to the second decimal place.



****Open discount****
: **Can apply to:** Menu item or check.

An open discount allows the restaurant employee to specify a percentage or amount to remove from the menu item or check.

- An open amount discount allows the employee to specify a currency amount for the discount. For example, discount $5.00 from a check or item.


- An open percent discount allows the employee to specify a percentage for the discount. For example, discount 10% from a check or item.

When a percent discount results in a fraction of a penny, the Toast platform applies half even rounding to the second decimal place.



You can use the orders API to apply an open *amount* discount to a check or item.

You cannot use the orders API to apply an open *percent* discount to a check or item. Open percent discounts can only be applied using the Toast POS system. When you retrieve an order with the orders API, the API does return open percent discounts that are applied.



****Buy-one-get-one (BOGO)****
: **Can apply to:** Check.

A BOGO discount allows guests to receive items free when they purchase qualifying items.

For example, when a guest purchases a cup of coffee, they get a croissant free.

For more information about setting up BOGO discounts, see the article [BOGO (Buy One Get One) Discounts](https://central.toasttab.com/s/article/BOGO-Buy-One-Get-One-Discounts).



****Combo****
: **Can apply to:** Check.

A combo discount allows guests to receive a discounted price for purchasing a specific set of items.

For example, a guest gets a discounted price when they purchase a cup of coffee and a bagel at the same time.





## Retrieving available discounts

You can retrieve a list of discounts that are configured for the restaurant. You can also retrieve discounts that an order is eligible for.

### Getting the list of configured discounts for a restaurant

To get information about the discounts configured for a restaurant, send a `GET` request to the `/discounts`endpoint of the configuration API.

In the results, the information about each discount includes the GUID that you use to apply the discount to an order in the orders API.

The following example shows the JSON return data for a `GET` request to the `/discounts`endpoint.


```
[
  {
    "guid": "a96fd992-9d69-4a62-894f-b621c31127a5",
    "entityType": "Discount",
    "amount": 25,
    "selectionType": "CHECK",
    "nonExclusive": true,
    "percentage": null,
    "name": "$25 Off",
    "active": true,
    "itemPickingPriority": "FIRST",
    "type": "FIXED",
    "fixedTotal": null
  },
  {
    "guid": "f66bd37f-8814-4f3a-a8ec-536d359dc1b7",
    "entityType": "Discount",
    "amount": null,
    "selectionType": "ITEM",
    "nonExclusive": false,
    "percentage": null,
    "name": "Buy one, get one apple!",
    "active": true,
    "itemPickingPriority": "LEAST_EXPENSIVE",
    "type": "BOGO",
    "fixedTotal": null
  },
  {
    "guid": "baf12b76-511a-416d-871f-8d4532d425e4",
    "entityType": "Discount",
    "amount": null,
    "selectionType": "ITEM",
    "nonExclusive": false,
    "percentage": 100,
    "name": "Comp",
    "active": true,
    "itemPickingPriority": "FIRST",
    "type": "PERCENT",
    "fixedTotal": null
  },
  {
    "guid": "23b26475-7e0a-4c0b-a2dc-9b6fcbe49e15",
    "entityType": "Discount",
    "amount": null,
    "selectionType": "CHECK",
    "nonExclusive": false,
    "percentage": null,
    "name": "ComboWingsDrinks",
    "active": true,
    "itemPickingPriority": "FIRST",
    "type": "FIXED_TOTAL",
    "fixedTotal": 5
  }
]
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2299734545DE-34ED-4C72-91FC-F7D438E64472" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">/discounts</code> endpoint returns an array of <code className="font-mono text-sm">Discount</code> objects. You can use the <code className="font-mono text-sm">guid</code> value to apply the discount to an order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2301734545DE-34ED-4C72-91FC-F7D438E64472" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">selectionType</code> value indicates whether you can apply the discount to an item or to an entire check. This discount applies to an entire check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2303734545DE-34ED-4C72-91FC-F7D438E64472" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">nonExclusive</code> value indicates the <a href="adminGuide-adminDiscountExclusivity" className="">discount exclusivity</a> of this discount. If <code className="font-mono text-sm">true</code>, then the discount is nonexclusive and can be combined with discounts. If <code className="font-mono text-sm">false</code>, the discount is exclusive and cannot be combined with other discounts.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2305734545DE-34ED-4C72-91FC-F7D438E64472" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">type</code> value <code className="font-mono text-sm">FIXED</code> indicates that this discount reduces the check price by the fixed currency <code className="font-mono text-sm">amount</code> value.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2307734545DE-34ED-4C72-91FC-F7D438E64472" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Because it is a BOGO discount, the Toast platform applies the discount to items that match the item specification for the discount. In this case, it applies the discount to one of each set of two apples that are included as menu item selections in the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2310734545DE-34ED-4C72-91FC-F7D438E64472" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For BOGO discounts, the <code className="font-mono text-sm">itemPickingPriority</code> value indicates the setting of the <a href="adminGuide-adminDiscountsConfigureBogo#adminDiscountsBogoGetItemDiscount" className="">item picking priority option</a>. For example, a value of <code className="font-mono text-sm">LEAST_EXPENSIVE</code> means that the least expensive "get" item is discounted.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2312734545DE-34ED-4C72-91FC-F7D438E64472" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">type</code> value <code className="font-mono text-sm">BOGO</code> indicates that this discount matches item selections based on the criteria that you configure for the discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2314734545DE-34ED-4C72-91FC-F7D438E64472" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The type value <code className="font-mono text-sm">PERCENT</code> indicates that this discount reduces the price of an item by the <code className="font-mono text-sm">percentage</code> value.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2316734545DE-34ED-4C72-91FC-F7D438E64472" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">type</code> value <code className="font-mono text-sm">FIXED_TOTAL</code> indicates this is a combo discount that reduces the price of all the eligible items to a set currency amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2318734545DE-34ED-4C72-91FC-F7D438E64472" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">fixedTotal</code> value indicates the total price of items discounted by this combo discount. The <code className="font-mono text-sm">fixedTotal</code> value is <code className="font-mono text-sm">null</code> for discounts that are not combo discounts.</p></div></td>
    </tr>
### Getting the list of applicable discounts for an order

A `GET` request to the `/discounts` endpoint returns all of the configured discounts for a restaurant. The response does not consider whether a discount applies to an order.

To get the applicable discounts for an order, send a `POST` request with the `Order` object to the `/applicableDiscounts` endpoint of the orders API. You can optionally provide a promotional code. The promotional code limits the results to applicable discounts that are associated with that promotional code.

The response contains a list of applicable discounts. For each discount, the response indicates whether it is a check-level discount or an item-level discount. For item-level discounts, the response identifies the menu selection items that the discount can be applied to.

Here is an example of a response to a `POST` request to the `/applicableDiscounts` endpoint:


```
[
    {
        "discount": {
            "guid": "1086966b-1411-4d4b-b275-6b8643f5afb0",
            "entityType": "Discount"
        },
        "applicableChecks": [],
        "applicableSelections": [
            {
                "guid": "1f801d3f-4715-4ae7-b518-5df56b9910a3",
                "entityType": "SELECTION",
                "externalId": null
            }
        ]
    },
    {
        "discount": {
            "guid": "138c3818-371c-4de9-88b2-c839fa144e8c",
            "entityType": "Discount"
        },
        "applicableChecks": [
            {
                "guid": null,
                "entityType": "CHECK",
                "externalId": null
            }
        ],
        "applicableSelections": []
    }
]
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#availableDiscountGuidCo" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the applicable discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#availableDiscountsEmptyChecksCo" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Because this is an item-level discount, the <code className="font-mono text-sm">checks</code> value is empty.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#availableDiscountsItemGuidCo" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This is the GUID of a menu item selection that is eligible for the discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#availableDiscountsChecksCo" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For a check-level discount, the <code className="font-mono text-sm">applicableChecks</code> value is populated.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#availableDiscountsEmptySelectionsCo" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For a check-level discount, the <code className="font-mono text-sm">applicableSelections</code> value is empty.</p></div></td>
    </tr>
## Applying discounts to a new order

You can add a discount to either an individual menu item selection or to an entire check. Each discount is configured to indicate whether it can be applied to a check or to a menu item selection.

### AppliedDiscounts object

To add the discount, you add an `AppliedDiscounts` object to the `MenuItemSelection` object or to the `Check`object.

The `AppliedDiscounts` object contains an `AppliedDiscount` object for each discount to apply. The `AppliedDiscount` object specifies the discount GUID.


```
"appliedDiscounts": [
  {
    "discount": {
      "guid": "f66bd37f-8814-4f3a-a8ec-536d359dc1b7"
    }
  }
]
```

For an open amount discount, the `AppliedDiscount` object also contains a `discountAmount` value that specifies the amount of the discount.


```
"appliedDiscounts": [
  {
    "discount": {
      "guid": "462c68a3-40ce-41ab-89e2-e26aaa41696e"
    },
    "discountAmount": 2.0
  }
]
```

### Applying discounts to menu item selections

You can only apply one discount to a menu item selection. The discount must be an item-level discount.

The following example shows a discount applied to a menu item selection.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "customer": {
        "email": "fgauthier@example.com",
        "firstName": "Francis",
        "lastName": "Gauthier",
        "phone": "987-654-3210"
      },
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "4c842ed6-ae99-425a-a343-390ab0e081d3",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "28dc4d65-e84b-44f0-8b73-0a721d5a9b88"
          },
          "appliedDiscounts": [
            {
              "discount": {
                "guid": "a96fd992-9d69-4a62-894f-b621c31127a5"
              }
            }
          ],
          "quantity": 2,
          "modifiers": []
        }
      ]
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e348F363EEC9-2046-412B-BBF1-890075ECA926" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This <code className="font-mono text-sm">AppliedDiscounts</code> object applies to the <code className="font-mono text-sm">MenuItemSelection</code> object that contains it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e350F363EEC9-2046-412B-BBF1-890075ECA926" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">guid</code> value identifies a discount that is configured for your restaurant. For information about getting available discounts, see <a href="apiDevGuide-apiDiscountingOrders#apiOrdersDiscountsRetrieving" className="">Retrieving available discounts</a>.</p></div></td>
    </tr>
### Applying discounts to an entire check

You can apply more than one check-level discount to a check.

Check-level and BOGO discounts have an [Allow with other discounts](adminGuide-adminDiscountExclusivity)setting. This setting determines whether the discount can be applied at the same time as other check-level and BOGO discounts.

- If Allow with other discounts is enabled, then the discount can be combined with other check-level or BOGO discounts. This includes check-level or BOGO discounts that have Allow with other discounts disabled.


- If Allow with other discounts is disabled, then the discount cannot be combined with other check-level or BOGO discounts that also have Allow with other discounts disabled.



For example, a BOGO discount allows guests to receive a free cup of coffee when they purchase a breakfast sandwich. Another check-level discount offers 10% off of the entire check. If either of those discounts has Allow with other discounts enabled, then a guest could get both the free cup of coffee and the 10% discount off their breakfast sandwich and any other items on their order.

The following example shows a discount applied to a check.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "customer": {
        "email": "fgauthier@example.com",
        "firstName": "Francis",
        "lastName": "Gauthier",
        "phone": "987-654-3210"
      },
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "4c842ed6-ae99-425a-a343-390ab0e081d3",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "28dc4d65-e84b-44f0-8b73-0a721d5a9b88"
          },
          "quantity": 2,
          "modifiers": []
        }
      ],
      "appliedDiscounts": [
        {
          "discount": {
            "guid": "f66bd37f-8814-4f3a-a8ec-536d359dc1b7"
          } 
        }
      ]
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e379F363EEC9-2046-412B-BBF1-890075ECA926" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedDiscounts</code> value in the <code className="font-mono text-sm">Check</code> object contains <code className="font-mono text-sm">AppliedDiscount</code> objects for each discount that you apply to the check. Specify the GUID for each discount. For information about getting the GUID for a discount, see <a href="apiDevGuide-apiDiscountingOrders#apiOrdersDiscountsRetrieving" className="">Retrieving available discounts</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e381F363EEC9-2046-412B-BBF1-890075ECA926" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">guid</code> value identifies a discount that is configured for your restaurant. For information about getting GUIDs for discounts, see <a href="apiDevGuide-apiDiscountingOrders#apiOrdersDiscountsRetrieving" className="">Retrieving available discounts</a>.</p></div></td>
    </tr>
## Applying promotional codes

Discounts can be configured with a promotional code, also known as a promo code. For orders placed from the Toast POS, to apply the discount, the employee must enter the promotional code or scan a barcode.

When you use the orders API to create orders, you can include promotional codes with the discounts. To apply a promotional code:

- Include an `AppliedDiscounts` value containing an `AppliedDiscount` object in the `Check` or `MenuItemSelection` object.


- In that `AppliedDiscount` object, provide an `appliedPromoCode` value.



The Toast platform does not verify that the `appliedPromoCode` value matches a promotional code that is configured for the discount.

The following example shows promotional codes applied to check and menu item selection discounts in an order:


```
{
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c"
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
          },
          "quantity": 1,
          "modifiers": [],
          "appliedDiscounts": [
          {
            "discount": {
              "guid": "590d2298-471d-4adb-8b83-24103157df6c"
            },
          "appliedPromoCode": "MYSPECIALOFFER"
        }
      ]
        }
      ],
      "appliedDiscounts": [
        {
          "discount": {
            "guid": "69d98978-6363-40bf-96eb-1e0d97dcea3d"
          },
          "appliedPromoCode": "MYEXTRASPECIALOFFER"
        }
      ]
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1506DCFD6CC3-6D50-4CF5-BF62-DC7AF967B651" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of a menu item selection discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1508DCFD6CC3-6D50-4CF5-BF62-DC7AF967B651" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedPromoCode</code> value identifies a promotion that is associated with the menu item selection discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1510DCFD6CC3-6D50-4CF5-BF62-DC7AF967B651" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of a check discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e1512DCFD6CC3-6D50-4CF5-BF62-DC7AF967B651" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedPromoCode</code> value identifies a promotion that is associated with the check discount.</p></div></td>
    </tr>
## Applying discounts to an existing order

You can add discounts to a check or menu item selection in an existing order.

The check `paymentStatus` must be `OPEN`.

### Required information to add the discount

Before you can add a discount to a check or a menu item selection, you need the following information:

- The GUID of the order.


- The GUID of the check.


- If you are adding a discount to a menu item selection, the GUID of the menu item selection.



You also create an array of `AppliedDiscount` objects for the discounts you are adding. You can optionally provide promotional codes for the discounts.

For example:


```
[
  {
    "discount": {
      "guid": "a96fd992-9d69-4a62-894f-b621c31127a5"
    }
  },
  {
    "discount": {
      "guid": "30430bb7-0e55-4aae-b783-ee62cda3ca7d"
    },
    "appliedPromoCode": "MYEXTRASPECIALOFFER"
  }
]
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e166052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You can include multiple discounts in the JSON array.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e168052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform identifier of one of the discounts that is being added to a check or menu item selection.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e170052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier of another discount that is being added.</p></div></td>
    </tr>
### POSTing the discounts to the check or menu item selection

When you add discounts to an existing order, you send a `POST` message to the `/appliedDiscounts` endpoint for the check or the menu item selection.

The REST API request path parameters must include the following Toast platform GUIDs:

- The GUID of the order.


- The GUID of the check.


- If applicable, the GUID of the menu item selection.



Use the following endpoints to add discounts to an existing order:



****Check-level discounts****
: To add check-level discounts, send the `POST`message to:

`/orders/<em>&#123;orderGuid&#125;</em>/checks/<em>&#123;checkGuid&#125;</em>/appliedDiscounts`



****Item-level discounts****
: To add an item-level discount, send the `POST`message to:

`/orders/<em>&#123;orderGuid&#125;</em>/checks/<em>&#123;checkGuid&#125;</em>/selections/<em>&#123;selectionGuid&#125;</em>/appliedDiscounts`





The body of the message is the JSON array of `AppliedDiscount` objects.

### Example responses for added discounts

When you add a discount to an existing order, the response contains an `Order` object that shows the added discounts.

Here is an example of a response to a request to add discounts to a check:


```
{
  "guid": "52b90296-359c-4015-a42b-044276a9c0b3",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "guid": "b79bbce8-cc4f-42f5-b42d-1f644888db34",
      "entityType": "Check",

      [contents omitted]

      "appliedDiscounts": [
        {
          "guid": "43130ce2-24e4-4532-b77d-f1cee4690743",
          "entityType": "AppliedCustomDiscount",
          "externalId": null,
          "approver": null,
          "processingState": null,
          "loyaltyDetails": null,
          "name": "MyCheckDiscount",
          "comboItems": [],
          "discountAmount": 11.1,
          "discount": {
            "guid": "c0c17bfb-db88-4322-ae58-df5059325a1a",
            "entityType": "Discount"
          },
          "nonTaxDiscountAmount": 11.1,
          "triggers": [],
          "appliedPromoCode": null
        }
      ],

      [contents omitted]

    }
  ],

  [contents omitted]

}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e196052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the order you added a discount in.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e198052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the check you added a discount to.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e200052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the discount you added.</p></div></td>
    </tr>
Here is an example of a response to a request to add a discount to a menu item selection:


```
{
  "guid": "52b90296-359c-4015-a42b-044276a9c0b3",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "guid": "b79bbce8-cc4f-42f5-b42d-1f644888db34",
      "entityType": "Check",

      [contents omitted]

      "selections": [
        {
          "guid": "ee3d2c4a-2d67-4c4e-8aa0-b8496fb00110",
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedDiscounts": [
            {
              "guid": "9d0a2fb6-c962-4ccd-89b6-c96865a7b2f3",
              "entityType": "AppliedCustomDiscount",
              "externalId": null,
              "approver": null,
              "processingState": null,
              "loyaltyDetails": null,
              "name": "MyItemDiscount",
              "comboItems": [],
              "discountAmount": 11.1,
              "discount": {
                "guid": "896304bc-6151-4e13-a407-89a4792fa2ba",
                "entityType": "Discount"
              },
              "nonTaxDiscountAmount": 11.1,
              "triggers": [
                {
                  "selection": {
                    "guid": "33182827-db63-4119-84a3-230e3e7eb809",
                    "entityType": "MenuItemSelection",
                    "externalId": null
                  },
                  "quantity": 1
                }
              ],
              "appliedPromoCode": null
            }
          ],

          [contents omitted]

        }
      ],

      [contents omitted]

    }
  ],

  [contents omitted]

}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e233052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the order you added a discount in.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e235052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the check you added a discount in.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e237052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the menu item selection you added a discount to.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e239052FCDED-8EB9-4BFA-9C41-EBF50ED0E8CE" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast platform GUID of the discount you added.</p></div></td>
    </tr>
## Verifying eligibility for discounts

When you use the orders API to add discounts to an order, the orders API verifies that the discounts are applicable based on the discount eligibility requirements, which can include:

- When the order is placed. A discount might only be available during a specified date range, on specific days of the week, or during specific times.


- A minimum or maximum check price.


- Required item selections.


- For check-level and BOGO discounts, whether multiple discounts can be combined.



For more information about discount eligibility and combining discounts, see the [discounts information](adminGuide-platformDiscountsOverview) in the *Toast Platform Guide*.

### Determining whether a menu item allows discounts

In the menus API, the `isDiscountable` field for a menu item determines whether any discount can be applied to that item.

If `isDiscountable` is `false`, then the item cannot have any discounts applied to it.

The orders API does not apply discounts to non-discountable items. If you add a discount to a non-discountable item, the `discountAmount` is set to 0 in the response.

### Determining eligibility based on order date

A discount might only be available during a specific date range. For an order created using the orders API, the eligibility is based on the order creation time.

### Verifying eligibility for BOGO discounts

A BOGO discount is based on "buy" items and "get" items. When an order contains the qualifying "buy" items, the guest receives the qualifying "get" items. For example, when a guest buys a bagel, they get a free cup of coffee. Or when a guest buys two cups of soup, they get a third cup of soup for free.

A BOGO discount can also be configured to apply to any items. For example, when a guest purchases any two items, they get a third item for free.

When a BOGO discount is applied to a check, the Toast platform attempts to match the menu item selections in the check to the applied discount. It checks for both the "buy" items and the "get" items.

If the Toast platform cannot match a qualifying "buy" or "get" item for the discount, the orders API returns an HTTP 400 error to indicate that the order is not formed correctly.

For the item matching for BOGO discounts, note the following:



****Toast platform selects the first matching item****
: The Toast platform matches a BOGO discount to the menu item selections in the order that they occur in the `Selections` object for the check.

For example, you apply a BOGO discount that offers free coffee with a purchased bagel. The Toast platform applies the discount when it finds the first bagel menu item selection. It discounts the price of the first coffee menu item selection.

If it is important to apply a BOGO discount to specific menu item selections, make sure that they are in the correct sequence.



****Cannot use an already discounted item****
: The Toast platform does not select an item that already has a discount applied to it as either the "buy" or "get" item.

For example, you apply a BOGO discount that offers free coffee with a purchased bagel. The order contains both a bagel and a coffee. However, you also applied to the coffee a discount for 50% off. Because of the existing discount on the coffee, it cannot be the "get" item for the BOGO discount.





### Verifying eligibility for combo discounts

A combo discount applies to multiple menu item selections in an order. A combo discount can be configured to apply to more than one item of the same type or to a combination of different items. For example, a combo discount might be:

- Two small cheese pizzas for a fixed amount


- One coffee and one bagel for a fixed amount



When you apply a combo discount to a check, the Toast platform selects matching menu selection items that qualify the check for the discount.

If the Toast platform cannot match a qualifying item for the discount, the orders API returns an HTTP 400 error to indicate that the order is not formed correctly.

When it identifies items to match the combo discount, the Toast platform does not select an item that already has a discount applied to it.

For example, you apply a combo discount that offers two small cheese pizzas for a fixed amount. The order contains two cheese pizzas. However, you also applied a 50% off discount to one of those pizzas. The discounted pizza cannot count toward the combo discount.

## How BOGO and combo discounts are applied in returned order data

When the Toast platform applies a BOGO or combo discount, it updates the menu item selections to reflect the discount.

To do this, the Toast platform might split the original menu item selections.

For example, an order includes two menu item selections - one for three bagels, and the other for a cup of coffee. The applied combo discount offers a bagel and coffee for a reduced price. The returned order object splits the bagel menu selection item. The bagel that the discount applies to is listed separately from the other two bagels.

### Applying BOGO discounts

A BOGO discount is applied to the "get" items for the discount. In the returned `Order` object, the discount is removed from the check and added to the "get" items.

For example, for a BOGO discount that offers a free cup of coffee with every bagel, the bagel is the "buy" item and the coffee is the "get" item. In the returned `Order` object, the discount is applied to the coffee.

The "get" items are in a separate `MenuItemSelection`object. The `appliedDiscounts` value for the "get" items includes information about the BOGO discount. In the `AppliedDiscounts` object, the `triggers` value identifies the menu item selections that fulfill the "buy" requirements.

For example, the following order contains a single menu item selection for three cups of soup. The applied BOGO discount offers a free cup of soup for every cup purchased.


```
{  
   "entityType":"Order",

   [contents omitted]

   },
   "checks":[  
      {  
         "entityType":"Check",
         "selections":[  
           {
             "entityType": "MenuItemSelection",
             "itemGroup": {
               "guid": "e0da05d4-db71-44ed-805b-95284d22df73",
               "entityType": "MenuGroup"
             },
             "item": {
               "entityType": "MenuItem",
               "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
             },
             "quantity": 3,
             "modifiers": []
           }
         ],
         "appliedDiscounts": [
           {
             "discount": {
                "guid": "7e345df5-9b3c-4e5a-9fbe-6183c56d2f88"
             }
           }
        ]
      }
   ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23132AAD0504-D23B-47FA-B191-CCDA17A4B028" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the menu item selection for the check. To trigger the orders API to apply the discount, the specific menu items must match the configuration of the BOGO discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23152AAD0504-D23B-47FA-B191-CCDA17A4B028" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of menu items in the check. To trigger the orders API to apply the discount, the number of menu items must match the configuration of the BOGO discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23172AAD0504-D23B-47FA-B191-CCDA17A4B028" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID for a BOGO discount that is configured for your restaurant. You apply BOGO discounts in the <code className="font-mono text-sm">appliedDiscounts</code> value for the <code className="font-mono text-sm">Check</code> object.</p></div></td>
    </tr>
In the returned order information, there are two `MenuItemSelection` objects.

- One `MenuItemSelection` object is for two cups of soup, which includes the "buy" item for the BOGO discount.


- The other `MenuItemSelection` object is for one cup of soup, which is the "get" item for the BOGO discount. This object includes the applied discount. The `triggers` object points to the other `MenuItemSelection` object.



The following example shows the return data for an order that includes a BOGO discount. In this example, the BOGO discount is *buy* one cup of soup and *get* one cup of soup free. The check in the order includes three cups of soup.


```
{
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",

      [contents omitted]

      "appliedDiscounts": [],
      "selections": [
        {
          "guid": "e0da05d4-db71-44ed-805b-95284d22df73",
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup"
          },
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem"
          },
          "quantity": 2,
          "preDiscountPrice": 17.98,
          "displayName": "Soup",
          "appliedDiscounts": [],
          "price": 17.98,

          [contents omitted]

        },
        {
          "guid": "2950ded4-f21a-428d-a847-698bcb260c03",
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup"
          },
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem"
          },
          "quantity": 1,
          "preDiscountPrice": 8.99,
          "displayName": "Soup",
          "appliedDiscounts": [
            {
              "guid": "7ec5c2e8-b6ae-4d30-8084-fecf3dd611f3",
              "entityType": "AppliedCustomDiscount",
              "approver": null,
              "processingState": null,
              "loyaltyDetails": null,
              "name": "Enjoy more soup.",
              "comboItems": [],
              "discountAmount": 8.99,
              "discount": {
                "guid": "7e345df5-9b3c-4e5a-9fbe-6183c56d2f88",
                "entityType": "Discount"
              },
              "triggers": [
                {
                  "selection": {
                    "guid": "e0da05d4-db71-44ed-805b-95284d22df73",
                    "entityType": "MenuItemSelection"
                  },
                  "quantity": 1
                }
              ],
              "appliedPromoCode": null
            }
          ],
          "price": 0,

          [contents omitted]

        }
      ],

      [contents omitted]

    }
  ],

  [contents omitted]

}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2359FB6A5D14-9F96-466C-8541-5687523E637B" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The BOGO discount is not applied to the <code className="font-mono text-sm">Check</code> in this <code className="font-mono text-sm">Order</code>. The BOGO discount is applied to the "get" menu item selections.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2361FB6A5D14-9F96-466C-8541-5687523E637B" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID that the Toast POS system assigns to a menu item selection in a check. You can use this GUID to determine which <code className="font-mono text-sm">MenuItemSelection</code> triggered a discount.</p> <p className="text-base leading-relaxed">In this example, the first <code className="font-mono text-sm">MenuItemSelection</code> object includes the items that triggered the BOGO discount. The items that trigger a BOGO discount are the "buy" items.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2363FB6A5D14-9F96-466C-8541-5687523E637B" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the specific menu item. This matches the menu item configured as the "buy" item for the BOGO discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2365FB6A5D14-9F96-466C-8541-5687523E637B" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The quantity of the menu items in this <code className="font-mono text-sm">MenuItemSelection</code> object. This object includes the "buy" item for the BOGO discount.</p> <p className="text-base leading-relaxed">The number of items in the input data for this order was three. This example response data splits the original <code className="font-mono text-sm">MenuItemSelection</code> into two groups. The <code className="font-mono text-sm">quantity</code> of <code className="font-mono text-sm">2</code> in this <code className="font-mono text-sm">MenuItemSelection</code> object includes the "buy" item and another item that is not affected by the BOGO discount at all.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2367FB6A5D14-9F96-466C-8541-5687523E637B" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">No discounts are applied to the <code className="font-mono text-sm">MenuItemSelection</code> for the "buy" item in the BOGO discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2370FB6A5D14-9F96-466C-8541-5687523E637B" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID that the Toast platform assigns to a menu item selection in a check. You can use this GUID to determine which <code className="font-mono text-sm">MenuItemSelection</code> triggered a discount.</p> <p className="text-base leading-relaxed">In this example, the second <code className="font-mono text-sm">MenuItemSelection</code> object includes the items that the BOGO discount applies to. The items that are reduced in price by a BOGO discount are the "get" items.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2372FB6A5D14-9F96-466C-8541-5687523E637B" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the specific menu item. This matches the menu item configured as the "get" item for the BOGO discount. In this example, the specific menu item for the "buy" and "get" items are the same item, a cup of soup.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2374FB6A5D14-9F96-466C-8541-5687523E637B" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The quantity of the menu items in this <code className="font-mono text-sm">MenuItemSelection</code> object. This object includes the "get" item for the BOGO discount.</p> <p className="text-base leading-relaxed">The number of items in the input data for this order was three. This example response data splits the original <code className="font-mono text-sm">MenuItemSelection</code> into two groups. The <code className="font-mono text-sm">quantity</code> of <code className="font-mono text-sm">1</code> in this <code className="font-mono text-sm">MenuItemSelection</code> object includes the "get" item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2376FB6A5D14-9F96-466C-8541-5687523E637B" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the "get" item before the BOGO discount is applied.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2378FB6A5D14-9F96-466C-8541-5687523E637B" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The BOGO discount is applied to the <code className="font-mono text-sm">MenuItemSelection</code> that includes the "get" item for the discount. The <code className="font-mono text-sm">AppliedCustomDiscount</code> object includes information about the BOGO discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2380FB6A5D14-9F96-466C-8541-5687523E637B" className="">(11)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">In this example, the BOGO discount applies a 100% price reduction to the "get" item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2383FB6A5D14-9F96-466C-8541-5687523E637B" className="">(12)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">triggers</code> value indicates which <code className="font-mono text-sm">MenuItemSelection</code> object in the check qualified the current menu item for the discount. The <code className="font-mono text-sm">guid</code> value matches the GUID that the Toast platform assigned to the <code className="font-mono text-sm">MenuItemSelection</code> that triggered the discount. In this example, see <a href="apiDevGuide-apiDiscountingOrders#co-d1e2361FB6A5D14-9F96-466C-8541-5687523E637B" className="">the matching GUID</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2385FB6A5D14-9F96-466C-8541-5687523E637B" className="">(13)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">In this example, the BOGO discount applies to one "get" item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2387FB6A5D14-9F96-466C-8541-5687523E637B" className="">(14)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the "get" item is reduced by the BOGO discount. In this example, the BOGO discount reduces the price of the "get" item by 100%.</p></div></td>
    </tr>
### Applying a combo discount

When the Toast platform applies a combo discount, it adds a `comboItems` object to the `AppliedDiscounts`object. The `comboItems` object identifies the menu item selections that are part of the discount.

For example, the following order contains a single menu item selection for three cups of soup. The applied combo discount offers two cups of soup for a reduced price.


```
{  
   "entityType":"Order",

   [contents omitted]

   },
   "checks":[  
      {  
         "entityType":"Check",
         "selections":[  
           {
             "entityType": "MenuItemSelection",
             "itemGroup": {
               "guid": "e0da05d4-db71-44ed-805b-95284d22df73",
               "entityType": "MenuGroup"
             },
             "item": {
               "entityType": "MenuItem",
               "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
             },
             "quantity": 3,
             "modifiers": []
           }
         ],
         "appliedDiscounts": [
           {
             "discount": {
                "guid": "7e345df5-9b3c-4e5a-9fbe-6183c56d2f88"
             }
           }
        ]
      }
   ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2684531BD268-895B-4950-9F99-86F6459D75C7" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the menu item selection for the check. The specific menu items must match the configuration of the combo discount to trigger the orders API to apply that discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2686531BD268-895B-4950-9F99-86F6459D75C7" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of menu items in the check. The number of menu items must match the configuration of the combo discount to trigger the orders API to apply that discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2688531BD268-895B-4950-9F99-86F6459D75C7" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID for a combo discount that is configured for your restaurant. You apply combo discounts in the <code className="font-mono text-sm">appliedDiscounts</code> value for the check object.</p></div></td>
    </tr>
In the returned order information, there are two `MenuItemSelection` objects.

- One `MenuItemSelection` object is for two cups of soup. These are the two cups of soup that have the combo discount applied.


- The other `MenuItemSelection` object is for the third cup of soup, which is not discounted.



In the `AppliedDiscounts` object for the check, the `comboItems` object points to the `MenuItemSelection` object for the two cups of soup.


```
{
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",

      [contents omitted]

      "appliedDiscounts": [
        {
          "guid": "3b97af77-bb9f-4f83-87e1-471a1dd984cd",
          "entityType": "MultiItemAppliedDiscount",
          "approver": null,
          "processingState": null,
          "loyaltyDetails": null,
          "name": "Eat more soup.",
          "comboItems": [
            {
              "guid": "b059bf10-2d4b-4aba-808a-46d0ecfa1b71",
              "entityType": "MenuItemSelection"
            }
          ],
          "discountAmount": 2.98,
          "discount": {
            "guid": "b1fba60e-f119-45ce-81ed-1e030c8e8705",
            "entityType": "Discount"
          },
          "triggers": [
            {
              "selection": {
                "guid": "13c704da-d8bd-4a72-8df3-d340efb1e0d3",
                "entityType": "MenuItemSelection"
              },
              "quantity": 2
            }
          ],
          "appliedPromoCode": null
        }
      ],
      "totalAmount": 25.67,
      "selections": [
        {
          "guid": "13c704da-d8bd-4a72-8df3-d340efb1e0d3",
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup"
          },
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem"
          },
          "quantity": 1,
          "preDiscountPrice": 8.99,
          "appliedDiscounts": [],

          [contents omitted]

          "price": 8.99
        },
        {
          "guid": "b059bf10-2d4b-4aba-808a-46d0ecfa1b71",
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 2,
          "preDiscountPrice": 17.98,
          "appliedDiscounts": [],
          
          [contents omitted]
          
          "price": 15
        }
      ]

      [contents omitted]

    }
  ]

[contents omitted]

}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2717531BD268-895B-4950-9F99-86F6459D75C7" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You apply a combo discount in the <code className="font-mono text-sm">appliedDiscounts</code> value of the <code className="font-mono text-sm">Check</code> object in an order. The response data for a check with a combo discount includes the discount information in the <code className="font-mono text-sm">appliedDiscounts</code> value for the <code className="font-mono text-sm">Check</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2719531BD268-895B-4950-9F99-86F6459D75C7" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the <code className="font-mono text-sm">MenuItemSelection</code> that the combo discount is applied to.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2721531BD268-895B-4950-9F99-86F6459D75C7" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the combo discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2723531BD268-895B-4950-9F99-86F6459D75C7" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the <code className="font-mono text-sm">MenuItemSelection</code> that contains the menu items that qualify for the combo discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2725531BD268-895B-4950-9F99-86F6459D75C7" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The number of menu items that qualify for the combo discount. For example, the combo discount in this example applies to two cups of soup.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2728531BD268-895B-4950-9F99-86F6459D75C7" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID that the Toast platform assigned to a menu item selection in a check. You can use this GUID to determine which <code className="font-mono text-sm">MenuItemSelection</code> triggered a discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2730531BD268-895B-4950-9F99-86F6459D75C7" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the specific menu item for this selection.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2732531BD268-895B-4950-9F99-86F6459D75C7" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The quantity of the menu items in this <code className="font-mono text-sm">MenuItemSelection</code> object.</p> <p className="text-base leading-relaxed">The number of items in the input data for this order was three. This example response data splits the original <code className="font-mono text-sm">MenuItemSelection</code> into two groups. The <code className="font-mono text-sm">quantity</code> of <code className="font-mono text-sm">1</code> in this <code className="font-mono text-sm">MenuItemSelection</code> object is not included in the combo discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2734531BD268-895B-4950-9F99-86F6459D75C7" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The orders API reports combo discount information in the <code className="font-mono text-sm">appliedDiscounts</code> value for the <code className="font-mono text-sm">Check</code>. The <code className="font-mono text-sm">appliedDiscounts</code> value for the menu item selection is empty.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2736531BD268-895B-4950-9F99-86F6459D75C7" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the specific menu item for this selection. This matches the menu item configured in the combo discount. In this example, the specific menu item is a cup of soup.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2738531BD268-895B-4950-9F99-86F6459D75C7" className="">(11)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The quantity of the menu items in this <code className="font-mono text-sm">MenuItemSelection</code> object.</p> <p className="text-base leading-relaxed">The number of items in the input data for this order was three. This example response data splits the original <code className="font-mono text-sm">MenuItemSelection</code> into two groups. The <code className="font-mono text-sm">quantity</code> of <code className="font-mono text-sm">2</code> in this <code className="font-mono text-sm">MenuItemSelection</code> object includes the two cups of soup that are configured in the example combo discount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2741531BD268-895B-4950-9F99-86F6459D75C7" className="">(12)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the two menu items before the combo discount is applied.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2743531BD268-895B-4950-9F99-86F6459D75C7" className="">(13)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The orders API reports combo discount information in the <code className="font-mono text-sm">appliedDiscounts</code> value for the <code className="font-mono text-sm">Check</code>. The <code className="font-mono text-sm">appliedDiscounts</code> value for the menu item is empty.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e2745531BD268-895B-4950-9F99-86F6459D75C7" className="">(14)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the two menu items after the combo discount is applied.</p></div></td>
    </tr>
## Working with loyalty programs

A loyalty program rewards guests for patronizing a restaurant. A loyalty program might offer a reward based on a number of visits or a total dollar amount. Loyalty programs might also offer discounts.

From the Toast orders API, you can perform the following tasks related to loyalty programs that are integrated with Toast:

- Apply a check to the guest's loyalty program account. For example, if a guest receives a free entree after 10 visits, then you want to make sure that their loyalty account is credited for each visit.


- Apply a loyalty program discount to a check or a menu item selection. For example, loyalty program members always get 10% off of their check.



For more information about loyalty programs, see [Loyalty program integration overview](apiDevGuide-apiLoyaltyProgramIntegrationOverview).

### How the Toast platform interacts with loyalty programs

To perform loyalty account operations, the Toast platform communicates with a third-party loyalty program service provider. The loyalty program service provider maintains information about customers' qualifying purchases and determines the loyalty program discounts that a customer can apply to checks.

The Toast platform supports integration with a specific set of third-party loyalty program services. When you associate a customer's loyalty program account with an order or a discount, you specify the program service provider from the list of supported providers.

The Toast platform does not maintain configuration information about loyalty programs and loyalty program discounts. The Toast platform relies on the loyalty program service provider to perform the following tasks:

- Verify the loyalty program account.


- Determine whether a check is eligible to be applied to a customer's account.


- Validate eligibility for a loyalty program discount.



### Applying checks to a loyalty program account

To apply a check to a loyalty program account, include an `AppliedLoyaltyInfo` object in the `Check` object. The `AppliedLoyaltyInfo` object includes the following information:

- `loyaltyIdentifier` - The identifier of the loyalty program account. For example, the customer's loyalty card number.


- `vendor` - The identifier of the loyalty program service provider. The `vendor` value is usually `INTEGRATION`.



The following example shows a check being applied to a loyalty program account.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "4f4d2103-2e0f-45d7-ae4c-8a9c16648fd1",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "customer": {
        "email": "fgauthier@example.com",
        "firstName": "Francis",
        "lastName": "Gauthier",
        "phone": "987-654-3210"
      },
      "appliedLoyaltyInfo": {
        "loyaltyIdentifier": "6000101001599474",
        "vendor": "`MYLOYALTYPROVIDER`"
      },
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "eeebddd6-6556-4c81-bd2b-1d1a1a716a83",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "79df2dfb-340d-405f-a0f9-55b882606ce5"
          },
          "quantity": 3,
          "modifiers": []
        }
      ]
    }
  ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e29207557168-3DB0-4F1C-BC76-F4C42119A6B2" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedLoyaltyInfo</code> value holds an <code className="font-mono text-sm">AppliedLoyaltyInfo</code> object that associates a check with a specific loyalty account.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e29407557168-3DB0-4F1C-BC76-F4C42119A6B2" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">loyaltyIdentifier</code> value is the unique identifier of the loyalty account that is recognized by the loyalty program service provider. For example, this might be the loyalty card number for a program member.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e29907557168-3DB0-4F1C-BC76-F4C42119A6B2" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">vendor</code> value specifies the loyalty program service provider. The value is one of the enumerated service provider names that are supported by the Toast POS system. The value is usually <code className="font-mono text-sm">INTEGRATION</code>.</p></div></td>
    </tr>
### Applying loyalty program discounts to an order

To apply loyalty program discounts to an order:

1. Include an `appliedLoyaltyInfo` value in the `Check` object that the discount applies to.

In the `AppliedLoyaltyInfo` object, provide the following information:

- `loyaltyIdentifier` - The identification string for the loyalty program account.


- `vendor` - The Toast API enumeration value for the loyalty program service provider. The `vendor`value is usually `INTEGRATION`.




2. Include an `appliedDiscounts` value in the `Check` object for a check-level discount, or in a `MenuItemSelection` object for an item-level discount.

In the `AppliedDiscounts` object, include the `loyaltyDetails` value.

In the `LoyaltyDetails` object, provide the following information:

- `vendor` - The Toast API enumeration value for the loyalty program service provider. The `vendor`value is usually `INTEGRATION`. If vendor is `INTEGRATION`, then you do not provide a discount GUID or amount.


- `referenceId` - The identification string for the loyalty program discount. The loyalty program service provider recognizes this value and matches it to the specific discount.





The following example shows the JSON message body to `POST` an order with a check-level loyalty program discount.


```
{  
   "entityType":"Order",
   "diningOption":{  
      "guid":"4f4d2103-2e0f-45d7-ae4c-8a9c16648fd1",
      "entityType":"DiningOption"
   },
   "checks":[  
      {  
         "entityType":"Check",
         "customer":{
            "email":"fgauthier@example.com",
            "firstName":"Francis",
            "lastName":"Gauthier",
            "phone":"987-654-3210"
         },
         "appliedLoyaltyInfo": {
            "loyaltyIdentifier": "6000101001599474",
            "vendor": "INTEGRATION"
         },
         "selections":[  
            {  
               "entityType":"MenuItemSelection",
               "itemGroup":{  
                  "guid":"eeebddd6-6556-4c81-bd2b-1d1a1a716a83",
                  "entityType":"MenuGroup"
               },
               "item":{  
                  "entityType":"MenuItem",
                  "guid":"79df2dfb-340d-405f-a0f9-55b882606ce5"
               },
               "quantity":3,
               "modifiers": []
            }
         ],
         "appliedDiscounts": [
           {
             "loyaltyDetails": {
               "vendor": "INTEGRATION",
               "referenceId": "4"
             }
           }
         ]
      }
   ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e266B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedLoyaltyInfo</code> value holds an <code className="font-mono text-sm">AppliedLoyaltyInfo</code> object that associates a check with a specific loyalty account.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e268B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">loyaltyIdentifier</code> value is the unique identifier of the loyalty account that is recognized by the loyalty program service provider. For example, this might be the loyalty card number for a program member.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e270B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">vendor</code> value specifies the loyalty program service provider. The value is one of the enumerated service provider names that the Toast POS system supports. The value is usually <code className="font-mono text-sm">INTEGRATION</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e272B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedDiscounts</code> value holds an <code className="font-mono text-sm">AppliedDiscount</code> object that specifies the loyalty program discount or discounts to apply to the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e274B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">vendor</code> value specifies the loyalty program service provider. The value is one of the enumerated service provider names that the Toast platform supports. The value is usually <code className="font-mono text-sm">INTEGRATION</code>. If <code className="font-mono text-sm">vendor</code> is <code className="font-mono text-sm">INTEGRATION</code>, then you do not provide a discount GUID or amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e277B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">referenceId</code> value is the unique identifier that is recognized by the loyalty program service provider. The loyalty program service provider matches this value to its own discount records.</p></div></td>
    </tr>
This example shows the JSON message body to `POST` an order with an item-level loyalty program discount.


```
{  
   "entityType":"Order",
   "diningOption":{  
      "guid":"4f4d2103-2e0f-45d7-ae4c-8a9c16648fd1",
      "entityType":"DiningOption"
   },
   "checks":[  
      {  
         "entityType":"Check",
         "customer":{
            "email":"fgauthier@example.com",
            "firstName":"Francis",
            "lastName":"Gauthier",
            "phone":"987-654-3210"
         },
         "appliedLoyaltyInfo": {
            "loyaltyIdentifier": "6000101001599474",
            "vendor": "INTEGRATION"
         },
         "selections":[  
            {  
               "entityType":"MenuItemSelection",
               "itemGroup":{  
                  "guid":"eeebddd6-6556-4c81-bd2b-1d1a1a716a83",
                  "entityType":"MenuGroup"
               },
               "item":{  
                  "entityType":"MenuItem",
                  "guid":"79df2dfb-340d-405f-a0f9-55b882606ce5"
               },
               "quantity":3,
               "appliedDiscounts": [
                 {
                   "loyaltyDetails": {
                   "vendor": "INTEGRATION",
                   "referenceId": "4"
                   }
                 }
               ],
               "modifiers": []
            }
         ]
      }
   ]
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e290B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedLoyaltyInfo</code> value holds an <code className="font-mono text-sm">AppliedLoyaltyInfo</code> object that associates a check with a specific loyalty account.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e292B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">loyaltyIdentifier</code> value is the unique identifier of the loyalty account that is recognized by the loyalty program service provider. For example, this may be the loyalty card number for a program member.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e294B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">vendor</code> value specifies the loyalty program service provider. The value is one of the enumerated service provider names that the Toast platform supports. The value is usually <code className="font-mono text-sm">INTEGRATION</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e296B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">appliedDiscounts</code> value holds an <code className="font-mono text-sm">AppliedDiscount</code> object that specifies the loyalty program discount or discounts being applied to the item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e298B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">vendor</code> value specifies the loyalty program service provider. The value is one of the enumerated service provider names that the Toast platform supports. The value is usually <code className="font-mono text-sm">INTEGRATION</code>. If vendor is <code className="font-mono text-sm">INTEGRATION</code>, then you do not provide a discount GUID or discount amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e301B5FD597B-A42F-4C83-8CA0-E173E36FE922" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">referenceId</code> value is the unique identifier that is recognized by the loyalty program service provider. The loyalty program service provider matches this value to its own discount records.</p></div></td>
    </tr>
### Validating loyalty program account and discount eligibility

When you `POST` the order, the Toast POS sends the following information to the program service provider:

- The identifier of the loyalty program account.


- For discounts, the reference identifiers of the applied discounts.


- Details about the check and menu selection items.



The program service provider uses this information to verify that the loyalty account exists. It checks whether the order can be applied to the loyalty account, and whether the checks or menu item selections are eligible for the specified loyalty discounts.

The program service provider returns the results of the validation. The response includes whether the request was accepted. For discounts, the response indicates the discount amount.

For details on the response information for loyalty transactions, see [Provide information on a loyalty transaction](https://doc.toasttab.com/openapi/loyalty/operation/yourEndpointNamePost/) in the *API Reference*.

