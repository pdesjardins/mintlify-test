---
title: "Using multi-location IDs in orders"
id: apiUsingMultiLocationIdsInOrders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiVoidOrder.md
previousSectionTitle: "Void an order"
nextSectionFile: apiDevGuide-apiOrderTypeDetails.md
nextSectionTitle: "Order details based on the order dining option"
excerpt: "When you use the orders API to post an order, you must identify the menu groups, menu items, modifier groups, and modifiers that are included in the order."
keywords: [multilocationId,multiLocationId]
procedures: 0
codeExamples: 0
---

### Using multi-location IDs in orders

When you use the orders API to post an order, you must identify the menu groups, menu items, modifier groups, and modifiers that are included in the order.

To do this, you can provide either:

- The unique `guid`assigned to each menu entity. You can see examples of that in [Order details based on the order dining option](apiOrderTypeDetails.html)and [Specifying modifiers and instructions for menu item selections](apiSpecifyingModifiersAndInstructions.html).


- The `multilocationId`for each menu entity. This is the recommended option, especially for restaurants that use the multi-location management module (previously known as the " enterprise module").



For information about `guid`and `multilocationId`values and using them in API requests, see [Toast identifiers](portalToastIdentifiers.html).

Note that for each menu entity, you must submit either a `guid`OR a `multiLocationId`. You cannot submit both identifiers. When you submit both types of identifier for a menu entity, the order submission fails.

You can submit `guid`values for some menu entities and `multiLocationId`values for others. You cannot submit both a `guid`and a `multiLocationId`for the *same menu entity*.

#### Example orders API request with multilocationIds

The following example shows a request to the `/orders`endpoint that uses `multiLocationId`values.

```
{ [(1)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e1951635951163-co)
    "diningOption": {
        "guid": "03e8796d-6eeb-460c-83fe-376766003059",
    },
    "checks": [
        {
            "selections": [
                {
                    "itemGroup": { [(2)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e1971635951163-co)
                        "multiLocationId": "500000008202847047",
                    },
                    "item": { [(3)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e1991635951163-co)
                        "multiLocationId": "500000008202871058"
                    },
                    "quantity": 1,
                    "modifiers": [
                        {
                            "optionGroup": { [(4)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2011635951163-co)
                                "multiLocationId": "500000000111604139"
                            },
                            "item": { [(5)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2031635951163-co)
                                "multiLocationId": "500000000106492270"
                            },
                            "quantity": 1
                        },
                        {
                            "optionGroup": {
                                "multiLocationId": "500000000106491932"
                            },
                            "item": {
                                "multiLocationId": "500000000099996428"
                            },
                            "quantity": 1
                        }
                    ]
                }
            ],
            "customer": { [(6)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2061635951163-co)
                "entityType": "Customer",
                "firstName": "Jack",
                "lastName": "Jones",
                "phone": "333-555-5555",
                "email": "jack@example.com"
            }
        }
    ]
}
```



(1) The Orderobject that defines the order being submitted.

(2) The parent menu group for a menu item to submit in this order. For example, Salads.

(3) The menu item included in this order. For example, Dinner Salad.

(4) A modifier group for the Dinner Salad menu item. For example, Salad Dressing.

(5) A modifier for the Dinner Salad menu item. For example, Balsamic Vinaigrette.

(6) The guest who is placing the order.

#### Example Order object with both identifiers in an orders API response

Responses to requests sent to the `/orders/{GUID}`and `/ordersBulk`endpoints contain both the `multiLocationId`and `guid`for all `item`, `itemGroup`, and `optionGroup`objects in an order.

The following example response shows how both identifiers are provided for each menu entity.

```
{
  "guid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  "entityType": "Order",

  *[contents omitted]*

  "checks": [
    {
      "guid": "e4c1f40d-3247-4b8b-9891-52f445930fa3",
      "entityType": "Check",

      *[contents omitted]*

      "selections": [
        {
          "guid": "2f91e217-ec31-4659-a7ba-dc66d76a1b5b",
          "entityType": "MenuItemSelection",

          *[contents omitted]*

          "displayName": "Dinner Salad",
          "modifiers": [
            {
              "guid": "7d850cd0-c014-46f0-bfa6-b1f920c03743",
              "entityType": "MenuItemSelection",

              *[contents omitted]*

              "optionGroup": {
                "guid": "8a2f952d-4dca-4eb0-b867-445f3a674bad",
                "entityType": "MenuOptionGroup",
                "externalId": null,
                "multiLocationId": "100000000171239701" [(1)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2731635951163-co)
              },
              "displayName": "Balsamic Vinaigrette",

              *[contents omitted]*

              "item": {
                "guid": "e5ccef2d-dc70-4c2d-bddd-d8448dee2e61",
                "entityType": "MenuItem",
                "externalId": null,
                "multiLocationId": "100000000171239909" [(2)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2791635951163-co)
              },
              
              *[contents omitted]*

            },
          ],
          
          *[contents omitted]*

          "itemGroup": {
            "guid": "c922e206-8512-4d99-a79d-32532eae239f",
            "entityType": "MenuGroup",
            "externalId": null,
            "multiLocationId": "100000000171239911" [(3)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2871635951163-co)
          },
          "item": {
            "guid": "50508a61-b561-4a5b-8bbb-7838c045dfab",
            "entityType": "MenuItem",
            "externalId": null,
            "multiLocationId": "100000000437569098" [(4)](apiDevGuide-apiUsingMultiLocationIdsInOrders.html#d1e2891635951163-co)
          },
          
          *[contents omitted]*

        },
      ],

      *[contents omitted]*

    },
  ],
  
  [contents omitted]

}
```



(1) The multiLocationIdfor the modifier group. For example, Salad Dressing.

(2) The multiLocationIdfor the modifier. For example, Balsamic Vinaigrette.

(3) The multiLocationIdfor the menu group. For example, Salads.

(4) The multiLocationIdfor the menu item. For example, Dinner Salad.

