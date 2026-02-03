---
title: "Using PricingRules and PricingStrategy to calculate prices"
id: apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiUnderstandingGuidsEntityIdentifiersAndMultilocationIds_V2.md
previousSectionTitle: "Understanding GUIDs, referenceIds, and multiLocationIds"
nextSectionFile: apiDevGuide-apiUsingTaxInfoAndModifierOptionTaxInfoToCalculateTaxesForMenuItemsAndModOptions.md
nextSectionTitle: "Using taxInfo and modifierOptionTaxInfo to calculate taxes for menu items and modifier options"
excerpt: "There are situations where additional context is needed before a price can be determined. For example, the price of a menu item that uses time-specific pricing depends on the time the menu item is..."
keywords: ["pricingrules", "pricingstrategy", "calculate", "prices", "pricingStrategy", "pricingRules"]
procedures: 0
codeExamples: 0
---

There are situations where additional context is needed before a price can be determined. For example, the price of a menu item that uses time-specific pricing depends on the time the menu item is ordered. For these situations, the menus API provides two values, `pricingStrategy` and `pricingRules`, that contain the information you need to calculate the menu item or modifier option's price. These values appear for every menu item, modifier group, and modifier option in the fully resolved JSON. Their contents change depending on how a menu item or modifier option's price has been configured.

You use the `pricingStrategy` and `pricingRules` values to calculate prices for:

- Menu items that use either the [Time Specific Price](adminTimeSpecificPrice.html) or [Size Price](adminSizePrice.html) pricing strategy.


- Modifier options that inherit their prices from a parent modifier group that uses the [Size Price](adminSizePrice.html), [Sequence Price](adminSequencePrice.html), or [Size/Sequence Price](adminSizeSequencePrice.html)pricing strategy.


- Modifier options that get their prices from modifier option [item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference) that use the [Time Specific Price](adminTimeSpecificPrice.html) or [Size Price](adminSizePrice.html) pricing strategy.



The `pricingStrategy` value tells you which pricing strategy is in effect so that you can properly interpret the contents of the `pricingRules` value and calculate the correct price. Because they appear in multiple locations in the menu JSON, it is important to use the correct `pricingStrategy` and `pricingRules` values when calculating prices. The following sections describe which `pricingStrategy` and `pricingRules` values to use and how to interpret them.

#### Calculating prices for menu items

The following sections describe how to calculate time-specific and size prices for a menu item. When calculating the price for a menu item, you use the `pricingStrategy` and `pricingRules` values for that menu item.



> **Note**
> 
> For menu items that use the Base Price or Menu Specific Price pricing strategy, no calculations are required. You retrieve the price from the menu item's `price` value. For menu items that use the Open Price pricing strategy, the expectation is that the price is provided at the time the item is ordered. See [Using menus API data to submit properly formed orders](apiUsingMenusApiDataToSubmitProperlyFormedOrders_V2.html)for more information.


##### Menu item with a time-specific price

When a menu item is priced using the Time Specific Price pricing strategy, its `pricingStrategy` value is `TIME_SPECIFIC_PRICE` and its `pricingRules`value contains the information you need to calculate the price of the item at any given time. Inside the `pricingRules`value, you see the `timeSpecificPricingRules` value which contains an array of time-specific prices for the menu item.

In this use case, the `pricingRules` value also contains the `sizeSpecificPricingGuid` and `sizeSequencePricingRules` values, however, the `sizeSpecificPricingGuid` is null and the `sizeSequencePricingRules` array is empty because the menu item uses a time-specific price, not a size price.

**Example 4.2. Sample JSON for a menu item that uses the Time Specific Price pricing strategy**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "6f54db28-557b-4070-b3da-58a52fa4a4fb",
              ...
              "price": null,
              "pricingStrategy": "TIME_SPECIFIC_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [
                  \{
                    "timeSpecificPrice": 8.0,
                    "basePrice": 10.0,
                    "schedule": [
                      \{
                        "days": [
                          "MONDAY",
                          "TUESDAY",
                          "WEDNESDAY",
                          "THURSDAY",
                          "FRIDAY"
                        ],
                        "timeRanges": [
                          \{
                            "start": "12:00",
                            "end": "14:00"
                          }
                        ]
                      }
                    ]
                  },
                  \{
                    "timeSpecificPrice": 9.0,
                    "basePrice": 10.0,
                    "schedule": [
                      \{
                        "days": [
                          "SATURDAY",
                          "SUNDAY"
                        ],
                        "timeRanges": [
                          \{
                            "start": "12:00",
                            "end": "15:00"
                          }
                        ]
                      }
                    ]
                  }
                ],
                "sizeSpecificPricingGuid": null,
                "sizeSequencePricingRules": []
              },
              ...
            },
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    ...
  },
  "modifierOptionReferences": \{
    ...
  \}
\}
```



(1) The price of the Cheese Pizza menu item during the time period defined by the schedule value ($8).

(2) The base price of the Cheese Pizza menu item ($10), used for time periods when a time-specific price has not been defined.

(3) The schedule for this time specific price, which defines the days and times the price applies.

(4) The days this time-specific price applies (Monday through Friday).

(5) The times this time-specific price applies (noon to 2pm), in the restaurant's local time.

(6) The configuration for another time-specific price for Saturday and Sunday.

  
##### Menu item with a size price

When a menu item is priced using the Size Price pricing strategy, its `pricingStrategy` value is `SIZE_PRICE` and its `pricingRules` value contains the information you need to calculate the prices for different sizes of the item. Inside the `pricingRules`value, you see the `sizeSpecificPricingGuid` value, which is populated with the `GUID` of the Size modifier group that contains the sizes and prices for this menu item.

The Toast platform automatically creates a Size modifier group when you choose the Size Price pricing strategy for a menu item. The system stores the sizes and prices you specify in this modifier group, using separate modifier options, one for each size. You use the `sizeSpecificPricingGuid` value to locate the correct Size modifier group to use when pricing a menu item that uses size pricing. In the JSON fragment below, you can see that Cheese Pizza menu item uses the `SIZE_PRICE` pricing strategy and the Size modifier group where the sizes and prices for the Cheese Pizza menu item are defined has a `GUID` ending in `31b0`. The Size modifier group has two modifier options that define two sizes for the Cheese Pizza menu item, Small and Large, which cost $8 and $10, respectively.

In this use case, the `timeSpecificPricingRules`array contained in the `pricingRules` value is empty because the menu item uses a size price, not a time-specific price. Also, the `sizeSequencePricingRules` array is empty because because this array is used for modifier option pricing, not menu item pricing.

**Example 4.3. Sample JSON for a menu item that uses the Size Price pricing strategy**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                6,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    ...
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
    ...
  },
  "modifierOptionReferences": \{
    ...
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \}
    ...
  \}
\}
```



(1) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(2) A reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(3) References to other, non-size related, modifier groups that modify the Cheese Pizza menu item.

(4) The Size modifier group for the Cheese Pizza menu item.

(5) References to the modifier options in the Size modifier group where the individual sizes and prices are defined.

(6) The Small modifier option, which defines the price of the Small size of the Cheese Pizza menu item.

(7) The price ($8) of the Small size of the Cheese Pizza menu item. This price is inherited from the Small modifier option's underlying item reference.

(8) The pricingStrategy for the Small modifier option, inherited from the underlying item reference.

(9) The pricingRules for the Small modifier option, inherited from the underlying item reference.

(10) The Large modifier option, which defines the price of the Large size of the Cheese Pizza menu item.

  
#### Calculating prices for modifier options that inherit a price from a modifier group

Modifier options that are priced at the group level, using the [Size Price](adminSizePrice.html), [Sequence Price](adminSequencePrice.html), or [Size/Sequence Price](adminSizeSequencePrice.html) pricing strategy, require additional price calculation. You can determine if a modifier option is priced this way by inspecting the modifier option's `price` and `pricingStrategy` values. If the `pricingStrategy` value is `GROUP_PRICE`, then the modifier option has been priced at the group level. If the modifier option's `price` value is `null`, it means that the group price is one that cannot be resolved down to the modifier option level and it requires additional calculation. This indicates that the modifier group uses the Size Price, Sequence Price, or Size/Sequence Price pricing strategy because those are the group-level pricing strategies that require additional calculation.

##### Modifier option that inherits a size price from a modifier group

When calculating [size pricing](adminSizePrice.html) for a modifier option, the Toast platform determines which size of a menu item has been ordered and then it locates the coordinating size and price for the modifier option. For example, toppings on a small pizza are $1 while toppings on a large pizza are $2. This scenario requires that both the menu item and the modifier group are configured to use the Size Price pricing strategy.

In the example below, the Cheese Pizza menu item's `pricingStrategy` is `SIZE_PRICE` and it has two sizes defined, Small and Large, priced at $8 and $10 respectively (for information on size pricing for a menu item, see [Menu item with a size price](apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2.html#apiMenuItemWithASizePrice_V2)). The Toppings modifier group's `pricingStrategy` is also `SIZE_PRICE`and its sizes and prices are defined in its own `pricingRules` value.

**Example 4.4. Sample JSON for modifier options that inherit Size pricing from a parent modifier group**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                3,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    ...
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
    "3": \{
      "referenceId": 3,
      "name": "Toppings",
      "guid": "58b79986-f88f-411d-ba18-14b1e2441e9d",
      ...
      "pricingStrategy": "SIZE_PRICE",
      "pricingRules": \{
        "timeSpecificPricingRules": [],
        "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
        "sizeSequencePricingRules": [
          \{
            "sizeName": "Small",    (12)
            "sizeGuid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
            "sequencePrices": [
              \{
                "sequence": 1,
                "price": 2.0
              }
            ]
          },
          \{
            "sizeName": "Large",
            "sizeGuid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
            "sequencePrices": [
              \{
                "sequence": 1,
                "price": 4.0
              \}
            ]
          \}
        ]
      \},
      ...
      "modifierOptionReferences": [
        10,
        11
      ],
      ...
    },
    ...
  },
  "modifierOptionReferences": \{
    ...
    "10": \{
      "referenceId": 10,
      "name": "Mushrooms",
      "guid": "fa24fee9-76c4-40ba-ae3c-7dfccafdd8d3",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "11": \{
      "referenceId": 11,
      "name": "Onions",
      "guid": "afee6be7-8280-4c69-a170-9fdf4c76bf7b",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \},
    ...
  \}
\}
```



(1) Indicates that the pricing strategy for the Cheese Pizza menu item is SIZE_PRICE.

(2) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(3) Reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(4) Reference to the Toppings modifier group.

(5) The Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(6) Prices are defined on the Small and Large modifier options themselves, so the pricingStrategy for the Size modifier group is NONE and pricingRules is null.

(7) Reference to the Small modifier option for the Cheese Pizza menu item.

(8) Reference to the Large modifier option for the Cheese Pizza menu item.

(9) The Toppings modifier group.

(10) Indicates that the pricing strategy for the Toppings modifier group is SIZE_PRICE.

(11) The GUID of the Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(12) An object that defines the price of toppings added to a Small cheese pizza.

(13) The GUID of the modifier option that defines the matching Small size of the Cheese Pizza menu item.

(14) The sequence value is always 1 for the SIZE_PRICE pricing strategy because there is only one price for each size of the modifier option. (Other pricing strategies use the sequence value to assign a price to a modifier option based on the sequence in which it was ordered.)

(15) The price for a Small size of a topping ($2).

(16) An object that defines the price of toppings added to a Large cheese pizza.

(17) The GUID of the modifier option that defines the matching Large size of the Cheese Pizza menu item.

(18) The price for a Large size of a topping ($4).

(19) Reference to the Mushrooms modifier option.

(20) Reference to the Onions modifier option.

(21) GROUP_PRICE indicates that the Mushrooms modifier option inherits its price from its parent modifier group.

(22) The modifier option that defines the price of a Small cheese pizza.

(23) The price of a Small cheese pizza ($8).

(24) The modifier option that defines the price of a Large cheese pizza.

(25) The price of a Large cheese pizza ($10).

  
##### Modifier option that inherits a sequence price from a modifier group

When using [sequence pricing](adminSequencePrice.html), the cost of a modifier option depends on the order in which it is added to a menu item. For example, on a pizza menu item, the first topping is free, the second topping costs $1.00, the third topping costs $1.50, and all additional toppings cost $2.00. As modifier options are added to or removed from the menu item, the cost of the menu item is updated to reflect those choices.

Unlike the Size Price and Size/Sequence Price pricing strategies, the Sequence Price pricing strategy has no interaction with the pricing strategy of the menu item that a modifier option is applied to. In the example below, the Cheese Pizza menu item has two sizes, Small ($8) and Large ($10). The first topping added to either size costs $1, the second topping costs $2, and all additional toppings cost $2.50. So, a small Cheese Pizza with two toppings costs $11 while a large Cheese Pizza with two toppings costs $13.

**Example 4.5. Sample JSON for modifier options that inherit Sequence pricing from a parent modifier group**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                4,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    ...
    "4": \{
      "referenceId": 4,
      "name": "Toppings",
      "guid": "2fb9889a-e3e9-4039-9bbd-99defb7f04b1",
      ...
      "pricingStrategy": "SEQUENCE_PRICE",
      "pricingRules": \{
        "timeSpecificPricingRules": [],
        "sizeSpecificPricingGuid": null,
        "sizeSequencePricingRules": [
          \{
            "sizeName": null,
            "sizeGuid": null,
            "sequencePrices": [
              \{
                "sequence": 1,
                "price": 1.0
              },
              \{
                "sequence": 2,
                "price": 2.0
              },
              \{
                "sequence": 3,
                "price": 2.5
              \}
            ]
          \}
        ]
      \},
      ...
      "modifierOptionReferences": [
        14,
        15
      ],
      ...
    },
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
  },
  "modifierOptionReferences": \{
    ...
    "14": \{
      "referenceId": 14,
      "name": "Pepperoni",
      "guid": "11adaad3-c391-42e8-a234-350a16e5a68d",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "15": \{
      "referenceId": 15,
      "name": "Sausage",
      "guid": "bd3a44ed-8362-49b8-8f6e-c899480137ff",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    ...
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \}
  \}
\}
```



(1) Indicates that the pricing strategy for the Cheese Pizza menu item is SIZE_PRICE.

(2) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(3) Reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(4) Reference to the Toppings modifier group.

(5) The Toppings modifier group.

(6) Indicates that the pricing strategy for the Toppings modifier group is SEQUENCE_PRICE.

(7) The price of the first topping added to the Cheese Pizza menu item ($1).

(8) The price of the second topping added to the Cheese Pizza menu item ($2).

(9) The price of the third topping added to the Cheese Pizza menu item ($2.50). Because this is the last price in the sequence, it is also the price of any toppings added beyond the third.

(10) Reference to the Pepperoni modifier option.

(11) Reference to the Sausage modifier option.

(12) The Size modifier group that defines sizes for the Cheese Pizza menu item.

(13) Reference to the Small modifier option.

(14) Reference to the Large modifier option.

(15) GROUP_PRICE indicates that the Pepperoni modifier option inherits its price from its parent modifier group.

(16) A Small cheese pizza costs $8.

(17) A Large cheese pizza costs $10.

  
##### Modifier option that inherits a size/sequence price from a modifier group

With [size/sequence pricing](adminSizeSequencePrice.html), the cost of a modifier option depends on the size of the menu item it is applied to and the order in which it is applied to the menu item. For example, the first topping on a small pizza is $0.50 and additional toppings are $1 while the first topping on a large pizza is $1.50 and additional toppings are $2.50. To configure size/sequence pricing, the menu item must use the Size Price pricing strategy and the modifier group must use the Size/Sequence Price pricing strategy.

In the example below, the Cheese Pizza menu item's `pricingStrategy` is `SIZE_PRICE` and it has two sizes defined, Small and Large, priced at $8 and $10 respectively (for information on size pricing for a menu item, see [Menu item with a size price](apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2.html#apiMenuItemWithASizePrice_V2)). The Toppings modifier group's `pricingStrategy` is `SIZE_SEQUENCE_PRICE` and it defines that the first topping on a small Cheese Pizza costs $1 while the second topping costs $2. Likewise, the first topping on a large Cheese Pizza costs $3 and the second topping costs $4.

**Example 4.6. Sample JSON for modifier options that inherit Size/Sequence pricing from a parent modifier group**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                5,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    ...
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
    "5": \{
      "referenceId": 5,
      "name": "Toppings",
      "guid": "e65dd350-5628-45fd-993d-8cf9c4f15a76",
      ...
      "pricingStrategy": "SIZE_SEQUENCE_PRICE",
      "pricingRules": \{
        "timeSpecificPricingRules": [],
        "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
        "sizeSequencePricingRules": [
          \{
            "sizeName": "Small",
            "sizeGuid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
            "sequencePrices": [
              \{
                "sequence": 1,
                "price": 1.0
              },
              \{
                "sequence": 2,
                "price": 2.0
              }
            ]
          },
          \{
            "sizeName": "Large",
            "sizeGuid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
            "sequencePrices": [
              \{
                "sequence": 1,
                "price": 3.0
              },
              \{
                "sequence": 2,
                "price": 4.0
              \}
            ]
          \}
        ]
      \},
      ...
      "modifierOptionReferences": [
        16,
        17
      ],
      ...
    },
    ...
  },
  "modifierOptionReferences": \{
    ...
    "16": \{
      "referenceId": 16,
      "name": "Olives",
      "guid": "8d45403d-5393-4c19-9d11-1dd963df8a26",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "17": \{
      "referenceId": 17,
      "name": "Peppers",
      "guid": "d4977c91-08d3-4060-a7bd-13e19a83e794",
      ...
      "price": null,
      "pricingStrategy": "GROUP_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \}
  \}
\}
```



(1) Indicates that the pricing strategy for the Cheese Pizza menu item is SIZE_PRICE.

(2) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(3) Reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(4) Reference to the Toppings modifier group.

(5) The Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(6) Prices are defined on the Small and Large modifier options themselves, so the pricingStrategy for the Size modifier group is NONE and pricingRules is null.

(7) Reference to the Small modifier option for the Cheese Pizza menu item.

(8) Reference to the Large modifier option for the Cheese Pizza menu item.

(9) The Toppings modifier group.

(10) Indicates that the pricing strategy for the Toppings modifier group is SIZE_SEQUENCE_PRICE.

(11) The GUID of the Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(12) An object that defines the price of toppings added to a Small cheese pizza.

(13) The GUID of the modifier option that defines the matching Small size of the Cheese Pizza menu item.

(14) The price of the first topping added to a Small cheese pizza ($1).

(15) The price of the second topping added to a Small cheese pizza ($2). Because this is the last price in the sequence, it is also the price of any toppings added beyond the second.

(16) Reference to the Olives modifier option.

(17) Reference to the Peppers modifier option.

(18) GROUP_PRICE indicates that the Olives modifier option inherits its price from its parent modifier group.

(19) The modifier option that defines the price of a Small cheese pizza.

(20) The price of a Small cheese pizza ($8).

  
#### Calculating prices for modifier options that use their item reference price

This section describes the `pricingRules` and `pricingStrategy` values when you have configured a modifier option so that it uses the price of its underlying [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference) and that item reference uses the Time Specific Price or Size Price pricing strategy.

##### Modifier option that uses a time specific price from its item reference

The example below shows a modifier group, Toppings, whose modifier options are individually priced. One of the modifier options in the Toppings group, Goat Cheese, uses the `TIME_SPECIFIC_PRICE` pricing strategy. When the Goat Cheese modifier option is ordered between noon and 2pm, it costs $1. During the rest of the day, it costs $2.

**Example 4.7. Sample JSON for a modifier option that inherits a Time Specific Price from its item reference**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                6,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    "6": \{
      "referenceId": 6,
      "name": "Toppings",
      "guid": "a1778e92-7ce9-4b1e-867d-c1effd7478b8",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        18,
        ...
      ],
      ...
    },
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
  },
  "modifierOptionReferences": \{
    "18": \{
      "referenceId": 18,
      "name": "Goat Cheese",
      "guid": "0ca19f15-184c-4b69-8049-cd50bf96c39e",
      ...
      "price": null,
      "pricingStrategy": "TIME_SPECIFIC_PRICE",
      "pricingRules": \{
        "timeSpecificPricingRules": [
          \{
            "timeSpecificPrice": 1.0,
            "basePrice": 2.0,
            "schedule": [
              \{
                "days": [
                  "MONDAY",
                  "TUESDAY",
                  "WEDNESDAY",
                  "THURSDAY",
                  "FRIDAY",
                  "SATURDAY",
                  "SUNDAY"
                ],
                "timeRanges": [
                  \{
                    "start": "12:00",
                    "end": "14:00"
                  }
                ]
              }
            ]
          }
        ],
        "sizeSpecificPricingGuid": null,
        "sizeSequencePricingRules": []
      },
      ...
    },
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \}
  \}
\}
```



(1) Indicates that the pricing strategy for the Cheese Pizza menu item is SIZE_PRICE.

(2) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(3) Reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(4) Reference to the Toppings modifier group.

(5) The Toppings modifier group.

(6) A price is defined on the Goat Cheese modifier option itself, so the pricingStrategy for the Toppings modifier group is NONE and pricingRules is null.

(7) Reference to the Goat Cheese modifier option.

(8) The Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(9) Prices are defined on the Small and Large modifier options themselves, so the pricingStrategy for the Size modifier group is NONE and pricingRules is null.

(10) Reference to the Small modifier option for the Cheese Pizza menu item.

(11) Reference to the Large modifier option for the Cheese Pizza menu item.

(12) Indicates that the pricing strategy for the Goat Cheese modifier option is TIME_SPECIFIC_PRICE.

(13) The price of the Goat Cheese modifier option during the time period defined by the schedule value ($1).

(14) The base price of the Goat Cheese modifier option ($2), used for time periods when a time-specific price has not been defined.

(15) The schedule for this time-specific price, which defines the days and times the price applies.

(16) The days this time-specific price applies (Monday through Sunday).

(17) The times this time-specific price applies (noon to 2pm), in the restaurant's local time.

(18) The modifier option that defines the price of a Small cheese pizza.

(19) The price of a Small cheese pizza ($8).

  
##### Modifier option that uses a size price from its item reference

The example below shows a modifier group, Toppings, whose modifier options are individually priced. One of the modifier options in the Toppings group, Tomatoes, uses the `SIZE_PRICE` pricing strategy. Two sizes and prices are defined for Tomatoes, Small for $1.50 and Large for $3.50.

**Example 4.8. Sample JSON for a modifier option that inherits a Size Price from its item reference**

```
\{
  "restaurantGuid": "2071fb81-988b-4d75-b8dc-c5c17cff9706",
  ...
  "menus": [
    \{
      "name": "Dinner",
      "guid": "ddd681de-3c12-4d45-b8b1-a5b2ea898210",
      ...
      "menuGroups": [
        \{
          "name": "Pizza",
          "guid": "dc868006-919a-4950-a4cc-3a03f9770fd7",
          ...
          "menuItems": [
            \{
              "name": "Cheese Pizza",
              "guid": "95c5d500-8d92-46f2-bec4-fb2a42a46621",
              ...
              "price": null,
              "pricingStrategy": "SIZE_PRICE",
              "pricingRules": \{
                "timeSpecificPricingRules": [],
                "sizeSpecificPricingGuid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
                "sizeSequencePricingRules": []
              \},
              ...
              "modifierGroupReferences": [
                2,
                6,
                ...
              ],
              ...
            }
          ]
        }
      ]
    }
  ],
  "modifierGroupReferences": \{
    "7": \{
      "referenceId": 7,
      "name": "Size",
      "guid": "1517b7a4-612f-4447-ab93-46b989f01b6b",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        20,
        21
      ],
      ...
    },
    "6": \{
      "referenceId": 6,
      "name": "Toppings",
      "guid": "a1778e92-7ce9-4b1e-867d-c1effd7478b8",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        19,
        ...
      ],
      ...
    },
    "2": \{
      "referenceId": 2,
      "name": "Size",
      "guid": "23c02762-9d6a-4d3f-a298-71c989bf31b0",
      ...
      "pricingStrategy": "NONE",
      "pricingRules": null,
      ...
      "modifierOptionReferences": [
        12,
        13
      ],
      ...
    },
  "modifierOptionReferences": \{
    "19": \{
      "referenceId": 19,
      "name": "Tomatoes",
      "guid": "b53cb945-d790-4386-88b5-c29b4f72141f",
      ...
      "price": null,
      "pricingStrategy": "SIZE_PRICE",
      "pricingRules": \{
        "timeSpecificPricingRules": [],
        "sizeSpecificPricingGuid": "1517b7a4-612f-4447-ab93-46b989f01b6b",
        "sizeSequencePricingRules": []
      \},
      ...
      "modifierGroupReferences": [
        7
      ]
    },
    "20": \{
      "referenceId": 20,
      "name": "Small",
      "guid": "e5c9883b-5c15-4771-9efa-0a63b9124484",
      ...
      "price": 1.5,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "21": \{
      "referenceId": 21,
      "name": "Large",
      "guid": "269cbff6-2e90-4ef8-8a83-ea5a76fb7199",
      ...
      "price": 3.5,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "12": \{
      "referenceId": 12,
      "name": "Small",
      "guid": "352244f2-a952-4a3a-a3ae-7775fa221ce7",
      ...
      "price": 8.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    },
    "13": \{
      "referenceId": 13,
      "name": "Large",
      "guid": "4ff89bca-b448-4892-bc4c-62c37a28ac44",
      ...
      "price": 10.0,
      "pricingStrategy": "BASE_PRICE",
      "pricingRules": null,
      ...
      "modifierGroupReferences": []
    \}
  \}
\}
```



(1) Indicates that the pricing strategy for the Cheese Pizza menu item is SIZE_PRICE.

(2) The GUID of the Size modifier group that defines the sizes and prices for Cheese Pizza menu item. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 2.

(3) Reference to the Size modifier group in the modifierGroupReferences map. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(4) Reference to the Toppings modifier group.

(5) The Size modifier group that defines sizes and prices for the Tomatoes modifier option.

(6) Reference to the Small modifier option for the Tomatoes modifier option.

(7) Reference to the Large modifier option for the Tomatoes modifier option.

(8) Prices are defined on the modifier options themselves, so the pricingStrategy is NONE and pricingRules is null.

(9) Reference to the Tomatoes modifier option.

(10) The Size modifier group that defines sizes and prices for the Cheese Pizza menu item.

(11) Reference to the Small modifier option for the Cheese Pizza menu item.

(12) Reference to the Large modifier option for the Cheese Pizza menu item.

(13) The Tomatoes modifier option.

(14) Indicates that the pricing strategy for the Tomatoes modifier option is SIZE_PRICE.

(15) The GUID of the Size modifier group that defines sizes and prices for the Tomatoes modifier option. Note that this is the same modifier group that is referenced in the modifierGroupReferences map using the ID 7.

(16) Reference to the Size modifier group that defines sizes and prices for the Tomatoes modifier option. This is the same modifier group whose GUID is specified in the sizeSpecificPricingGuid value.

(17) The modifier option that defines the price of the Tomatoes modifier option when it is applied to a Small cheese pizza.

(18) The modifier option that defines the price of the Tomatoes modifier option when it is applied to a Large cheese pizza.

(19) The modifier option that defines the price of a Small cheese pizza.

(20) The modifier option that defines the price of a Large cheese pizza.

  
