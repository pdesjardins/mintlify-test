---
title: "Specifying modifiers and instructions for menu item selections"
id: apiSpecifyingModifiersAndInstructions
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiOrderTypeDetails.md
previousSectionTitle: "Order details based on the order dining option"
nextSectionFile: apiDevGuide-apiOrdersPackagingPreferences.md
nextSectionTitle: "Packaging preferences"
externalReferences: [https://doc.toasttab.com/openapi/menus/overview/]
excerpt: "You can specify custom details for the menu item selections in an order."
procedures: 0
codeExamples: 0
---

You can specify custom details for the menu item selections in an order.

For example, a guest might want *jalapeno peppers*on a sandwich, *extra* rice, or the *large* size of a drink. Or they might want to have the salad dressing provided on the side instead of on the salad.

## Applying modifiers and pre-modifiers

To specify the custom details for a menu item selection, you add modifiers and pre-modifiers.

A modifier is a type of menu item that is configured as an optional component of another menu item. For example, sugar might be a modifier for a coffee menu item. For items that use size pricing, size is a modifier group.

A pre-modifier applies a text string to a modifier. It is typically displayed before the modifier name on a Toast POS device display and in a modifier description. For example, `NO` and `EXTRA`might be pre-modifiers for the sugar modifier.

In the orders API, to include the modifiers and pre-modifiers for a menu item selection, you add a `modifiers` value to the menu item's `Selection` object.

### Structure of a modifiers entry

The `modifiers` value is an array of objects. Each object in `modifiers` defines the details of a modifier to add to the menu item selection.

Each modifier object contains:



**`optionGroup`**
: Contains the GUID of the modifier's parent modifier group.

For example, for a salad menu item, a parent modifier group might be the available salad dressings.



**`item`**
: Contains the GUID of the specific modifier.

For example, in the salad dressings modifier group, a modifier might be the balsamic vinaigrette dressing.



**`quantity`**
: The quantity for the modifier.

The quantity must match the quantity of the menu item selection. See [Requirements for modifier quantities](docs/en-us/apiDevGuide-apiSpecifyingModifiersAndInstructions#requirementsforModifierQuantities).



**`preModifier` (optional)**
: Contains the GUID of the pre-modifier, if one is applied.



**`modifiers` (optional)**
: An array of modifier objects that represent any nested modifiers for this modifier.

A nested modifier further refines the modifier. For example, a Steak menu item has a Sides modifier group. The Sides modifier group contains a Salad modifier. The Salad modifier contains a nested modifier group called Salad Dressing that has Ranch and Balsamic Vinaigrette modifiers.

Modifiers can be nested an arbitrary number of levels deep.





To get the GUID identifiers for modifier groups, modifiers, and pre-modifiers, use the menus API. For more information, see the [menus API reference documentation](https://doc.toasttab.com/openapi/menus/overview/).

The following example message body for an order shows a modifier and a pre-modifier for a menu item selection.


```
{
  "entityType": "Order",

    [contents omitted]

  "checks": [
    {
      [contents omitted]
      "selections": [
        {
          "itemGroup": {
            "guid": "4c842ed6-ae99-425a-a343-390ab0e081d3",
          },
          "item": {
            "guid": "28dc4d65-e84b-44f0-8b73-0a721d5a9b88"
          },
          "quantity": 1,
          "modifiers": [
            {
              "optionGroup": {
                "guid": "d0bf5394-adff-428d-8a6b-bcb848c8b16d"
              },
              "item": {
                "guid": "ed4d3bfc-ad0c-46e7-afdf-1fb48ff91edd"
              },
              "quantity": 1,
              "preModifier": {
                "guid": "6311f315-3df8-48ed-bbc3-bd924cb90d55"
              },
              "modifiers": []
            }
          ]
        }
      ]
    }
  ]
}

```



(1) The GUID of the menu group for this menu item selection. For example, this menu group might contain salads.

(2) The GUID of the menu item for this menu item selection. For example, this menu item might be a garden salad.

(3) The GUID of the modifier group for this item selection. For example, this modifier group might contain salad dressings.

(4) The GUID of the modifier for this item selection. For example, this modifier might be the balsamic vinaigrette dressing.

(5) To specify a pre-modifier for a modifier, add the preModifier value to the modifier.

(6) The GUID of the pre-modifier for this modifier. For example, the pre-modifier might be NO or EXTRA.

### Requirements for modifier quantities

The orders API requires that the quantity of a modifier is equal to the quantity of the menu item selection.

You specify the menu item selection quantity in the `quantity` value of the `Selection` object of the check. You specify the modifier quantity in the `quantity`value of the `Selection` object in the `modifiers`value.

For example, a menu item selection is for two cheeseburgers (`"quantity": 2`). If you add a bacon modifier to that menu item selection, the `quantity` for the bacon modifier also must be `2`.

If different instances of the same item require a different set of modifiers, then you must add those items to the check as separate `Selection` objects. For example, to order one cheeseburger with bacon, and one cheeseburger without bacon, you add two `Selection` objects to the check. Each `Selection`object is for a single cheeseburger (`"quantity": 1`). You then add a bacon modifier with `"quantity": 1` to one of those `Selection` objects.

The orders API rejects orders that have mismatching menu item selection and modifier quantities. For example, if a check contains a menu item selection with `"quantity": 1` and a modifier with `"quantity": 2`, the Toast platform rejects the order. If the menu item selection `quantity` is `3`, but the modifier `quantity` is only `2`, the Toast platform rejects the order.

#### Example of matching item and modifier quantities

The following excerpt from an `Order` object shows a menu item selection for five slices of Key Lime Pie. The Whipped Cream modifier is added to all of the slices.


```
{
  "entityType": "Order",
      [contents omitted]
"checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "guid": "f3c11a7a-91c6-4691-8a9f-c0b7a2c64266",
          "entityType": "MenuItemSelection",
          "displayName": "Key Lime Pie",
          "itemGroup": {
            "guid": "c9f51ce7-d8cb-4cdb-bbd5-42c9a5f4a9df",
            "entityType": "MenuGroup"
          },
          "item": {
            "guid": "944f6176-0b3d-432c-ab03-5665a5ab3c5c", 
            "entityType": "MenuItem"
          },
          "quantity": 5.0, 
          "modifiers": [ 
            { 
              "guid": "9d5616d0-f697-48bc-9f15-bcbca6bfb495",
              "entityType": "MenuItemSelection",
              "optionGroup": {
                "guid": "7d1bdd86-0c3e-48c5-936c-c28a6ff48345",
                "entityType": "MenuOptionGroup",
                "externalId": null
              },
              "displayName": "Whipped Cream",
              "item": {
                "guid": "b2755b69-2c99-4214-b74e-6b6a1467501f",
                "entityType": "MenuItem",
                "externalId": null
              },
              "quantity": 5.0 
            }
          ]
        }
      ]
    }
  ]
}
```



 GUID of the menu item. For example, the menu item Key Lime Pie.

 Quantity of the menu item. For example, five Key Lime Pies.

 Modifier, specified in the modifiers array. For example, Whipped Cream.

 Quantity of the modifier. For example, five Whipped Creams (one whipped cream per pie).

### Using nested modifier groups sourced from menu groups

You must include specific identifiers when a modifier meets the following conditions: 

- The modifier is nested (it exists inside a parent modifier's modifiers array).


- The parent modifier's modifier options are sourced from a reused menu group. For example, the modifier options for a side salad modifier might be sourced from a Salads menu group. For more information about reusing menu groups, see [Adding modifier groups and modifiers](docs/en-us/adminGuide-adminAddingModifierGroupsAndModifiers).



**Required fields for parent modifiers **The following list describes the fields to include in the parent modifier's `Selection` object in your orders API request. 

- `itemGroup`: The GUID of the reused menu group this parent menu item belongs to. This ensures the Toast platform correctly links the selection to its original menu configuration.


- `optionGroup`: The GUID of the parent modifier option group.


- `item`: The GUID of the specific parent modifier selection.


- `quantity`: The amount chosen for this modifier option.



**Required fields for nested modifiers **The following list describes the fields to include in the nested modifier's `Selection` object of your orders API request.

- `optionGroup`: The GUID of the nested modifier option group.


- `item`: The GUID of the specific nested modifier selection.


- `quantity`: The amount chosen for this modifier option.



#### Example nested modifier from a reused menu group

The example below shows the correct modifier structure for an orders API POST request.


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
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "8b4f2555-8482-406f-a1dd-82c5afd718a8",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "96edc6ab-3992-4665-a3d0-c5a9fffd81b7"
          },
          "quantity": 1,
          "modifiers": [
            {
              "optionGroup": {
                "guid": "a83a38b2-178a-4b31-b45f-e011f00faf6f" 
              },
              "itemGroup": {
                "guid": "8b4f2555-8482-406f-a1dd-82c5afd718a8",
                "entityType": "MenuGroup"
              },
              "item": {
                "guid": "70afec63-1919-4fe1-8c2d-3dfaa232c406"
              },
              "quantity": 1,
              "modifiers": [
                {
                  "optionGroup": {
                    "guid": "6c677a8a-a858-43fd-b7f0-a404310c0e12"
                  },
                  "item": {
                    "guid": "d6ecdcb2-3a9f-4dcf-8034-900e34306271"
                  },
                  "quantity": 1,
                  "modifiers": []
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}

```



(1) The GUID for the specific modifier group that controls the rules, choices, and pricing for the modifier being selected.

(2) The GUID for the menu group that contains the modifier item being selected. This identifies the group of options for example, Sauces, or Sides, that the modifier item belongs to.

(3) The GUID for the specific menu item selection that is chosen as the parent-level modifier. This identifies the modifier choice itself for example, Add Extra Cheese.

(4) The GUID for the specific menu item selection chosen as a nested modifier. This is used when a modifier item itself has additional, secondary options applied to it for example, specifying well done for a side steak's temperature modifier.

### Adding the same modifier multiple times to a menu item selection

You can add the same modifier to a menu item selection multiple times, as long as each instance of the modifier has the same quantity as the menu item selection. This tells the restaurant to add the modifier to the item more than once. For example, if a guest wants double the cheese on a pizza, you can add the cheese modifier twice.

The following JSON body example adds whipped cream twice to a slice of cherry pie in an order:


```
{
  "entityType": "Order",
   ...

"checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "guid": "0d167434-07a8-444e-adeb-864eacbfe35f",
          "entityType": "MenuItemSelection",
          "displayName": "Cherry Pie",
          "itemGroup": {
            "guid": "c9f51ce7-d8cb-4cdb-bbd5-42c9a5f4a9df",
            "entityType": "MenuGroup"
          },
          "item": {
            "guid": "78727790-fcaa-4acd-adcd-7e12d5e67823", 
            "entityType": "MenuItem"
          },
          "quantity": 1.0, 
          "modifiers": [ 
            { 
              "guid": "29122a58-8c1f-4325-be79-0134641dce02",
              "entityType": "MenuItemSelection",
              "optionGroup": {
                "guid": "e957363b-b398-46be-a4e9-0f9fdb8edaf3",
                "entityType": "MenuOptionGroup",
                "externalId": null
              },
              "displayName": "Whipped Cream",
              "item": {
                "guid": "b2755b69-2c99-4214-b74e-6b6a1467501f",
                "entityType": "MenuItem"
              },
              "quantity": 1.0 
            },
            { 
              "guid": "29122a58-8c1f-4325-be79-0134641dce02",
              "entityType": "MenuItemSelection",
              "optionGroup": {
                "guid": "e957363b-b398-46be-a4e9-0f9fdb8edaf3",
                "entityType": "MenuOptionGroup"
              },
              "displayName": "Whipped Cream",
              "item": {
                "guid": "b2755b69-2c99-4214-b74e-6b6a1467501f",
                "entityType": "MenuItem"
              },
              "quantity": 1.0
            }
          ]
        }
      ]
    }
  ]
}
```



 GUID of the menu item. For example, Cherry Pie.

 Quantity of the menu item. For example, one Cherry Pie.

 First modifier, specified in the modifiers array. For example, the first Whipped Cream.

 Quantity of the modifier. For example, one Whipped Cream.

 Another modifier with a quantity of one, specified in the modifiers array. For example, the second Whipped Cream.

### Including default modifiers

A menu item can be configured with default modifiers. For example, a turkey sandwich menu item by default has lettuce and tomato modifiers.

When you use a Toast POS device to place an order, the Toast platform automatically adds the default modifiers on the selected menu items.

When you use the orders API to order an item that has default modifiers, default modifiers are not added automatically. You must include all of the default modifiers in the `modifiers` value for the item. If you omit a default modifier when you use the orders API, the Toast platform removes that modifier from the item. This means that if a guest requests that you remove a default modifier, then to satisfy the request, you can omit that modifier from the order JSON.

For example, for a pineapple and jalapeno pizza menu item, the default modifiers are cheese, pineapple, and jalapenos. To use the orders API to order the pineapple and jalapeno pizza, you must include all of those default modifiers in the `modifiers` value for the item. If a guest requests the pizza without jalapenos, you include only the cheese and pineapple modifiers. The Toast platform then specifies that the pizza should not have jalapenos.

### Applying modifiers to menu item portions

You can configure portions for menu items. For example, a pizza menu item might be divided into portions named "half one" and "half two." You can then apply different modifiers to each portion. For information on menu portions, see [Portions overview](docs/en-us/adminGuide-adminPortionsOverview).

When you create an order in the orders API, to add portions and modifiers for those portions:

1. Add each portion as a modifier of a menu item selection.


2. For each portion modifier, set `selectionType` to `PORTION`.


3. Apply modifiers to each portion.



To retrieve the GUIDs for the portions, use the [menus API](https://doc.toasttab.com/openapi/menus/overview/).

The following example order JSON applies modifiers to portions of a menu item selection.


```
{
  "entityType": "Order",
  "diningOption": {
    [contents omitted]
  },
  "checks": [
    {
      "customer": {
          [contents omitted]
      },
      "selections": [
        {
          "itemGroup": {
            "guid": "9a861b29-58ee-4c1c-9e23-9cac3a1132d4",
          },
          "item": {
            "guid": "025006c3-acdc-4d09-be94-faffde4ce3b7"
          },
          "quantity": 1,
          "modifiers": [
            {
              "item": {
                "guid": "1e12608c-0875-4951-8570-cbc52e1180e6",
              },
              "quantity": 1,
              "selectionType": "PORTION",
              "modifiers": [
                {
                  "optionGroup": {
                    "guid": "669c7b5e-d0d8-49ef-af2d-f71ff3aa4ef3",
                  },
                  "item": {
                    "guid": "10e66af7-85aa-4865-9ad0-bcf9d95f44c4",
                  },
                  "quantity": 1
                }
              ]
            },
            {
              "item": {
                "guid": "5f1257ac-00a1-43d1-8ad5-c9649629f651",
              },
              "quantity": 1,
              "selectionType": "PORTION",
              "modifiers": [
                {
                  "optionGroup": {
                    "guid": "669c7b5e-d0d8-49ef-af2d-f71ff3aa4ef3",
                  "item": {
                    "guid": "4ca5f20e-2330-4a20-88dd-882dfdb8193f"
                  },
                  "quantity": 1
                  }
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```



(1) The GUID of the menu group for this item selection. For example, this menu group might be "pizzas."

(2) The GUID of the menu item for this item selection. For example, this menu item might be "cheese pizza."

(3) Apply portions to the menu item selection in the modifiers value for that item.

(4) The GUID of one of the portions configured for this menu item. For example, this portion might be "half1."

 Include a selectionType value and include the value PORTION.

(6) Apply modifiers to a portion in the modifiers value for that portion.

(8) The GUID of the modifier group for this item selection. For example, this modifier group might be "pizza toppings."

(7) The GUID of the modifier for this item selection. For example, this modifier might be "mushrooms."

(9) The GUID of another portion configured for this menu item. For example, this portion might be "half2."

 Include a selectionType value and include the value PORTION.

(11) Apply modifiers to a portion in the modifiers value for that portion.

## Special requests and instructions

When you create an order in the orders API, you can specify special requests and instructions for the menu item selections. For example, when they order a salad, a guest might request that salad dressing is packaged on the side, instead of mixed in.

Special requests appear with the item name in the order description in the Toast platform and printed order tickets. Restaurant employees can see the requests when they prepare the items for an order.

### How to add a special request to a menu item selection

To add a special request to a menu item selection, in the `modifiers` object, add an object with the request message.

In the object for the special request:

- Set the `selectionType` value to `SPECIAL_REQUEST`.


- In the `displayName` value, provide the request message. You can enter up to 1000 characters.





> **Important**
> 
> To display special requests on your restaurant's KDS, add them to the `modifiers` object. Special requests added to objects other than `modifiers` will not show on the KDS.


### Example of adding a special request to a menu item selection

The following example JSON message body for a `POST` request to the orders API includes a special request for a menu item selection.


```
{
  "entityType": "Order",
      [contents omitted]
  },
  "checks": [
    {
      "selections": [
        {
            [contents omitted]
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
          },
          "modifiers": [
            {
              "selectionType": "SPECIAL_REQUEST"
              "displayName": "Put the salad dressing on the side, not mixed in.",
            }
          ]
        }
      ]
    [contents omitted]
  ]
}
```



(1) Include special requests in the array of modifiers for a menu item selection.

(2) Set the selectionType value to SPECIAL_REQUEST.

(3) In the displayName value, enter the request message.

