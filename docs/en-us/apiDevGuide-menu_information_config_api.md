---
title: "Getting menu information from the configuration API"
id: menu-information-config-api
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiMenusApiTroubleshooting_V2.md
previousSectionTitle: "Menus API troubleshooting"
nextSectionFile: apiDevGuide-portalApiGettingStockOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 5. Stock"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/]
excerpt: "This section explains how to use the Toast configuration API to get menu information for a restaurant."
keywords: [/menuGroups,/menuGroups/{guid},/menuItems,/menuOptionGroups,/menuOptionGroups/{guid},/preModifiers,/preModifiers/{guid},/preModifierGroups,/preModifierGroups/{guid},Menu]
procedures: 0
codeExamples: 2
---

### Getting menu information from the configuration API



> **Important**
> 
> The menus API has replaced the configuration API as the preferred mechanism for retrieving menu data for a restaurant. It is described in the [Menus API overview](apiGettingMenuInformationFromTheMenusAPI.html) section. This section remains for customers who have not yet transitioned to using the menus API for menu data retrieval.


This section explains how to use the Toast configuration API to get menu information for a restaurant.

The menu resources available from the configuration API provide JSON representations of the menu components for your restaurant. The JSON information includes the Toast GUIDs for menu components. You can use these GUIDs to submit pricing queries to the orders API.

**Menu Resources in the Configuration API**

- `/menus`


- `/menus/\{guid\}`


- `/menuGroups`


- `/menuGroups/\{guid\}`


- `/menuItems`


- `/menuOptionGroups`


- `/menuOptionGroups/\{guid\}`


- `/preModifiers`


- `/preModifiers/\{guid\}`


- `/preModifierGroups`


- `/preModifierGroups/\{guid\}`



In a Toast `Menu`, each `MenuGroup` has a list of `MenuItem`s in its `items` value. Each `MenuItem` may also have one or more `MenuOptionGroup`s in its `optionGroup`s value, which in turn contains further `MenuItem`s that are modifiers for the primary item. See more information about the data objects that represent menu components in [MenuItems, MenuGroups, MenuOptionGroups, and Menus](apiDevGuide-menu_information_config_api.html#menu-component-data-objects).

The following example shows the JSON representations of a menu, composed from configuration API return data. You can get the JSON representations of each component from the menu resources of the configuration API. See information about composing a menu from menu resource return data in [Working with the Toast menu hierarchy](apiDevGuide-menu_information_config_api.html#api-working-with-menu-hierarchy).

**Example 4.12. JSON Menu Composed from Configuration API Return Data**

```
[
  \{
    "entityType":"Menu",
    "name":"Lunch Menu",
    "guid":"a2a0b78a-a480-4adb-bbac-b32a7e0c2a12",
    "groups":[
      \{
        "entityType":"MenuGroup",
        "name":"A Twist-On-Fries",
        "guid":"578c5e48-7d99-438f-be61-f4f972569ce6",
        "subgroups":[],
        "items":[
          \{
            "entityType":"MenuItem",
            "name":"'Award Winning' Curly-Q Fries",
            "guid":"f21f2250-6f97-4a31-8a78-3283a5be0af4",
            "optionGroups":[
              \{
                "entityType":"MenuOptionGroup",
                "name":"Size",
                "guid":"f63f8bd3-9764-4b1b-b3c9-40c8c104b42b",
                "items":[
                  \{
                    "entityType":"MenuItem",
                    "name":"Half Basket",
                    "guid":"3c043245-3b4f-4e87-a6c9-6eeeb073518a",
                    "optionGroups":[]
                  },
                  \{
                    "entityType":"MenuItem",
                    "name":"Full Basket",
                    "guid":"68343381-290b-4410-9b8a-c8d63d9c9e1a",
                    "optionGroups":[]
                  \}
                ]
              \}
            ]
          \}
        ]
      \}
    ]
  \}
]
```

  
The following example shows a curl command that places an order for `'Award Winning' Curly-Q Fries` with `Full
      Basket` modifier with the **curl** command and order JSON shown in the following example.

**Example 4.13. Submitting an Order Selection with a Modifier**

```
curl -X POST \
-H "Content-Type: application/json" \
-H "Toast-Restaurant-External-ID: 93d6a5ce-395f-42ca-aa9d-d12a66a3b781" \
-H "Authorization: Bearer eyJhbGciOiJSUzI1NiJ9.eyJhdWQiOlsidG9hc3QiXSwic2
NvcGUiOlsiY2FyZHMiLCJjY3Byb2Nlc3NpbmciLCJkZXZpY2VzIiwic3ZjbWdtdCIsInVzZXJ
tZ210Il0sImV4cCI6MTQ2NDI4ODAwNCwianRpIjoiZWU0ODMyNzYtZmNmZC00ZmM5LThhZjAt
YTE5YzVhNzBmNzg5IiwiY2xpZW50X2lkIjoidG9hc3R3ZWIifQ.WzS6hcLrfXtcsmwXq2u0Ou
CmXBZoBRY0wVk__gNpg8TnV94zEnpB77BkBlVPqKk8YM9_ZOC1MDt4atZVAM_ImiEbtugTF9z
6YPROhhtDYx37BaDNrViUggvhY5PplZND_nSNSgA8nu6CARBIoTcfoWzSg0jj1yR8mUk2edFc
TzU" \
-d '\{
    "entityType": "Order",
    "diningOption": \{
      "guid": "a8512bcf-fde7-446e-ac31-7c342d4aaaff",
      "entityType": "DiningOption"
    },
    "checks": [
      \{
        "entityType": "Check",
        "selections": [
          \{
            "entityType": "MenuItemSelection",
            "itemGroup": \{
              "guid": "578c5e48-7d99-438f-be61-f4f972569ce6",
              "entityType": "MenuGroup"
            },
            "item": \{
              "guid": "f21f2250-6f97-4a31-8a78-3283a5be0af4",
              "entityType": "MenuItem"
            },
            "quantity": 1,
            "modifiers": [\{
                "entityType": "MenuItemSelection",
                "optionGroup": \{
                  "guid": "f63f8bd3-9764-4b1b-b3c9-40c8c104b42b",
                  "entityType": "MenuOptionGroup"
                },
                "item": \{
                  "guid": "68343381-290b-4410-9b8a-c8d63d9c9e1a",
                  "entityType": "MenuItem"
                \},
                "quantity": 1,
                "modifiers": []
              \}
            ]
          \}
        ]
      \}
    ]
  \}' "https://`[toast-api-hostname]`/orders/v2/orders"
```

  
#### MenuItems, MenuGroups, MenuOptionGroups, and Menus

The Toast POS represents menus using the following data objects:

- A `MenuItem` represents a single base product or product option. A final line item will correspond to a base `MenuItem` and any number of optional `MenuItems` made available by `MenuOptionGroups` associated with the base `MenuItem`. These `MenuOptionGroups` can be attached to the `MenuItem` itself or inherited from a `MenuGroup` of which the `MenuItem` is a member.


- A `MenuOptionGroup` is a collection of optional `MenuItems` that modify an associated base `MenuItem`. For instance, a "Burger" `MenuItem` might have a `MenuOptionGroup`called "Condiments" containing "Pickle", "Cheese", and "Tomato" `MenuItem`s. If there's only one burger on the `Menu`, the "Condiments" group will probably be attached directly to the "Burger" `MenuItem`. If the `Menu` contains a whole `MenuGroup` of various burgers, all of which can be ordered with pickles, cheese, or tomato, the `MenuOptionGroup` might instead be attached to the `MenuGroup`, and inherited by all the `MenuItems` in it.


- A `MenuGroup` is a named logical grouping of `MenuItems` and `MenuGroups`. A `MenuOptionGroup` attached to a `MenuGroup`provides the options in that `MenuOptionGroup` to all `MenuItems` in the `MenuGroup`, and to any of its child `MenuGroups` that have the `inheritOptionGroups` flag set to true.


- A `Menu` is the top-level representation of a group of products. A given restaurant might, for instance, have a "Lunch" `Menu` and a "Dinner" `Menu`. `Menu`s contain any number of `MenuGroup`s, and cannot contain `MenuItem`s directly.



Toast also offers pre-modifiers, which can supply additional information about a modifier, and pre-modifier groups. For more information, see the [reference documentation for the configuration API](https://doc.toasttab.com/openapi/configuration/overview/).

#### Working with the Toast menu hierarchy

Toast menus have the following attributes:

- Inheritance: Each MenuGroup can define MenuOptionGroups to apply to its containing MenuGroups and MenuItems. The final optionGroups in a MenuItem are determined by the inheritOptionGroups boolean property. If the value is true, the MenuItem takes optionGroups from its containing MenuGroup (which in turn may take it from its containing MenuGroup depending on its inheritOptionGroups property).


- Arbitrary Depth: A MenuItem can reference a MenuOptionGroup that in turn contains MenuItems that refer to MenuOptionGroups, and so forth. MenuGroups regularly contain other MenuGroups, though we encourage restaurants not to nest deeper than two levels.


- Multiple Parentage: Most Toast menu entities can be referenced by more than one container. MenuItems can be referenced by multiple MenuGroups, and a MenuGroup can be included in multiple Menus and MenuGroups. Position in the tree matters: The same MenuItem might inherit options from one MenuGroup in one subtree, and different options from another MenuGroup in another subtree.



##### Raw menu JSON versus resolved menu JSON

There are two different logical representations of a menu. The configuration API currently operates on a raw menu structure in which `MenuOptionGroup`s appear at any level as described above, and inheritance flags are present and necessary to determine which options are available for which items.

In a resolved menu structure, inheritance information has been consulted, `MenuOptionGroup`s have been propagated down to each item to which they apply, and inheritance flags are withheld. This is a more usable structure, and will eventually be supported by our APIs. For now, best practice for partners is to derive this resolved structure from the raw configuration API results. If Toast provides you with a JSON `Menu` export for testing purposes, it will be in this format.

The following example demonstrates a simple raw menu structure. If you need a JSON export of a restaurant menu for testing, contact Toast integration support. Note that these exports will include pricing information, which is not yet available through the API. Actual API responses will also include an additional `externalId` field, which is omitted here. For more information, see [External identifiers](portalToastIdentifiers.html#apiExternalIdentifiers).

```
[
  \{
    "entityType":"Menu",
    "name":"Lunch Menu",
    "guid":"a2a0b78a-a480-4adb-bbac-b32a7e0c2a12",
    "groups":[
      \{
        "entityType":"MenuGroup",
        "name":"A Twist On Fries",
        "guid":"578c5e48-7d99-438f-be61-f4f972569ce6",
        "subgroups":[],
        "optionGroups": [
          \{
            "entityType":"MenuOptionGroup",
            "name":"Size",
            "guid":"f63f8bd3-9764-4b1b-b3c9-40c8c104b42b",
            "items":[
              \{
                "entityType":"MenuItem",
                "name":"Half Basket",
                "guid":"3c043245-3b4f-4e87-a6c9-6eeeb073518a",
                "optionGroups":[]
              },
              \{
                "entityType":"MenuItem",
                "name":"Full Basket",
                "guid":"68343381-290b-4410-9b8a-c8d63d9c9e1a",
                "optionGroups":[]
              }
            ]
          }
        ]
        "items":[
          \{
            "entityType":"MenuItem",
            "name":"'Award Winning' Curly-Q Fries",
            "guid":"f21f2250-6f97-4a31-8a78-3283a5be0af4",
            "optionGroups":[],
            "inheritOptionGroups":true
          \}
        ]
      \}
    ]
  \}
]
```

##### Constructing the menu

A restaurant's complete menu can be reconstructed via API calls.

In the above example, calling

```
GET /menus/a2a0b78a-a480-4adb-bbac-b32a7e0c2a12
```

returns

```
\{
  "entityType":"Menu",
  "name":"Lunch Menu",
  "guid":"a2a0b78a-a480-4adb-bbac-b32a7e0c2a12",
  "groups":[
    \{
      "guid":"578c5e48-7d99-438f-be61-f4f972569ce6",
      "entityType": "MenuGroup"
    \}
  ]
\}
```

Which gives you a list of `MenuGroup` GUIDs. For each one, you can the call

```
GET /menuGroups/578c5e48-7d99-438f-be61-f4f972569ce6
```

which returns

```
\{
  "entityType":"MenuGroup",
  "name":"A Twist On Fries",
  "guid":"578c5e48-7d99-438f-be61-f4f972569ce6",
  "subgroups":[],
  "optionGroups": [
    \{
      "entityType":"MenuOptionGroup",
      "guid":"f63f8bd3-9764-4b1b-b3c9-40c8c104b42b"
    }
  "items":[
    \{
      "entityType":"MenuItem",
      "guid":"f21f2250-6f97-4a31-8a78-3283a5be0af4"
    \}
  ]
\}
```

giving you lists of the `MenuItem` GUIDs, `MenuOptionGroup` GUIDs, and `MenuGroup` GUIDs (none in this case) in each of those `MenuGroup`s. For each such GUID, make the appropriate call:

```
GET /menuOptionGroups/f63f8bd3-9764-4b1b-b3c9-40c8c104b42b

\{
  "entityType":"MenuOptionGroup",
  "name":"Size",
  "guid":"f63f8bd3-9764-4b1b-b3c9-40c8c104b42b",
  "items":[
    \{
      "entityType":"MenuItem",
      "guid":"3c043245-3b4f-4e87-a6c9-6eeeb073518a"
    },
    \{
      "entityType":"MenuItem",
      "guid":"68343381-290b-4410-9b8a-c8d63d9c9e1a"
    \}
  ]
\}
```

In this case we can see that there are two options in the "Size" `MenuOptionGroup`. These options themselves can of course be retrieved as above with `GET``/menuItems/<em>\<guid\></em>`.

Going back up to the "A Twist On Fries" group, make the calls for the listed `MenuItem`s:

```
GET /menuItems/f21f2250-6f97-4a31-8a78-3283a5be0af4
```

This returns

```
\{
  "entityType":"MenuItem",
  "name":"'Award Winning' Curly-Q Fries",
  "guid":"f21f2250-6f97-4a31-8a78-3283a5be0af4",
  "modifierGroups":[],
  "inheritOptionGroups":true
\}
```

We've now retrieved all the relevant information, but there is one more step. Checking the inheritOptionGroups flag on each MenuItem, we can see that "'Award Winning' Curly-Q Fries" inherits MenuOptionGroups from its parent, "A Twist On Fries". This means that the "Size" options apply to it. To derive a resolved Menu structure from this information, remove the "optionGroups" attribute from "A Twist On Fries" and copy it into each MenuItem that inherits it (in this case just "'Award Winning' Curly-Q Fries"). Then remove the iniheritGroups flag from all menuItems. The final resolved Menu structure is

```
[
  \{
    "entityType":"Menu",
    "name":"Lunch Menu",
    "guid":"a2a0b78a-a480-4adb-bbac-b32a7e0c2a12",
    "groups":[
      \{
        "entityType":"MenuGroup",
        "name":"A Twist On Fries",
        "guid":"578c5e48-7d99-438f-be61-f4f972569ce6",
        "subgroups":[],
        "items":[
          \{
            "entityType":"MenuItem",
            "name":"'Award Winning' Curly-Q Fries",
            "guid":"f21f2250-6f97-4a31-8a78-3283a5be0af4",
            "optionGroups": [
              \{
                "entityType":"MenuOptionGroup",
                "name":"Size",
                "guid":"f63f8bd3-9764-4b1b-b3c9-40c8c104b42b",
                "items":[
                  \{
                    "entityType":"MenuItem",
                    "name":"Half Basket",
                    "guid":"3c043245-3b4f-4e87-a6c9-6eeeb073518a",
                    "optionGroups":[]
                  },
                  \{
                    "entityType":"MenuItem",
                    "name":"Full Basket",
                    "guid":"68343381-290b-4410-9b8a-c8d63d9c9e1a",
                    "optionGroups":[]
                  \}
                ]
              \}
            ]
          \}
        ]
      \}
    ]
  \}
]
```

