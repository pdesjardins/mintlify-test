---
title: "Adding items to an existing check"
id: apiAddingItemsToACheck
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-calculatingOrderWaitTime.md
previousSectionTitle: "Calculating order wait time"
nextSectionFile: apiDevGuide-apiAddingPaymentsToACheck.md
nextSectionTitle: "Adding payments to an existing check"
externalReferences: [https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407]
excerpt: "You can use the orders API to add items to an existing check."
procedures: 0
codeExamples: 0
---



> **Important**
> 
> To use the `/orders` endpoint to add items to an existing check, you need access to the `orders.items:write` scope. For more information about API client scopes, and how to get access to them, see [Scopes](apiScopes.html).


You can use the orders API to add items to an existing check.

You cannot add items to a check in a restricted order. A closed order becomes restricted automatically after a specific period of time. For more information, see [Working with restricted orders](adminViewingRestrictedOrders.html).

The added items ignore meal pacing.

### How to add the items to the check

To add items to an existing check, you send a `POST`request to the `/orders/<em>\{orderGuid\}</em>/checks/<em>\{checkGuid\}</em>/selections`endpoint. To identify the items to add, you provide a JSON array of `Selection` objects.

**Procedure 2.5. To add items to an existing check**

1. Find the Toast platform GUIDs of the order and the check that you are adding items to. For more information on locating these GUIDs, see [Finding an order or check guid](apiOrdersFindingAnOrderGuid.html).


2. Create a JSON array of `Selection` objects that contain information about the items you are adding, including modifiers. For an example, see [Example request message body to add an item to an existing check](apiAddingItemsToACheck.html#apiExampleSelectionObjectsForAddingItemstoaCheck).



> **Note**
> 
> The `externalId` values for the `Order`, `Check`, and `Selection` objects must be unique. If you submit an order containing an `externalId`that already exists for another `Order`, `Check`, or `Selection`, the request will fail.



3. Send a `POST` request to the `/orders/<em>\{orderGuid\}</em>/checks/<em>\{checkGuid\}</em>/selections`endpoint of the Orders API. 

In the `POST` request path parameters, include the Toast platform GUIDs of the order and the check. 

In the request message body, include the array of `Selection` objects.


4. Examine the response that you receive from the Orders API. Verify that your request processed successfully with a 200 HTTP code response. For an example, see [Example response after adding items to an existing check](apiAddingItemsToACheck.html#apiExampleResponseDataWhenAddingItemstoaCheck).



### Example request message body to add an item to an existing check

The following example shows an array that contains a `Selection` object to ad a menu item to an existing check.

```
[
  \{
    "entityType": "MenuItemSelection",
    "itemGroup": \{
      "guid": "205c4612-d04d-43ec-86fd-7d0827a2eeed"
    },
    "item": \{
      "guid": "c58b958e-85a0-485a-bb5c-3b588e056aff"
    \}
    "quantity": 2,
    "modifiers": [
      
      [content omitted]

    ]
  \}
]
```



(1) You can include multiple menu item selections in the JSON array. This example contains a single item.

(2) The Toast platform GUID of the menu group for the menu item to add to the check. For more information, see Menus API overview.

(3) The Toast platform GUID of the menu item to add to the check.

(4) The quantity of the menu item to add to the check.

(5) If applicable, the modifiers for the added item. For more information about adding modifiers, see Applying modifiers and pre-modifiers.

### Example response after adding items to an existing check

The following example shows the response for a `POST` request to the `/orders/<em>\{orderGuid\}</em>/checks/<em>\{checkGuid\}</em>/selections`endpoint of the orders API.

```
\{
  "guid": "da257b12-4766-471c-9580-837d2b29eb92", 
  "entityType": "Order",

  [content omitted]

  "checks": [
    \{
      "guid": "6e1bb8e0-534d-437f-bbad-0f08045f463e",
      "entityType": "Check",
      
      [content omitted]
      
      "selections": [
        \{
          "guid": "f520f731-8164-41a8-b261-23b9df3bf861",
          "entityType": "MenuItemSelection",
                    
          [content omitted]

        },
        \{
          "guid": "a963dd45-e0bf-456b-a148-e955310d2643",
          "entityType": "MenuItemSelection",
          
          [content omitted]      

        \}
      ],
    
      [content omitted]
    
    \}
  ], 

  [content omitted]

\}
```



(1) The Toast platform GUID of the order that contains the check that you added menu items to.

(2) The Toast platform GUID of the check that you added menu items to.

(3) The Toast platform GUID of a menu item selection from the original check.

(4) The Toast platform system GUID of the menu item selection that was added to the existing check.

### How added items are sent to the kitchen

When you add menu item selections to an existing check, the effect in the kitchen depends on the following factors:



****Order approval****
: Does the original order require approval?

If the original order requires approval, is the order approved?

Orders that are created using the orders API never require approval. As long as an auto-firing device is configured, orders from the orders API are automatically fired to the kitchen. For more information about auto-firing devices, see [Setting up Order Auto-Firing](https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407).

For other orders, the restaurant can be configured to automatically send orders to the kitchen without approval, to require approval for all orders, or to require approval based on the order amount.



****Order scheduling****
: Is the original order a scheduled order or an as soon as possible (ASAP) order?

For scheduled orders, is the order `promisedDate`still in the future?





#### Handling for orders that do not require approval

If the original order did not require approval, the added menu item selections are handled as follows:



****Scheduled orders****
: If `promisedDate` for the order is still in the future, then the items are fired at the same time as the rest of the order.

If the order is already fired, then the added items are fired ASAP on a new ticket.



****ASAP orders****
: If the order is not yet fired, then the items are fired at the same time as the rest of the order.

If the order is already fired, then the added items are fired ASAP on a new ticket.





#### Handling for orders that do require approval

If the original order required approval, then added menu item selections are handled as follows:



****Scheduled orders****
: If the original order is not approved, and `promisedDate` for the order is still in the future, then the items are added to the order. They are fired at the same time as the rest of the order.

If the original order is approved, but `promisedDate` is still in the future, then the items are added to the order. The new items do not require approval. They are fired at the same time as the rest of the order.

If the original order is approved and has fired, then the new items are fired ASAP on a new ticket.



****ASAP orders****
: If the original order is not approved, then the new items are added to the order. They are fired at the same time as the rest of the order.

If the order is approved and has fired, then the items are fired ASAP on a new ticket.





