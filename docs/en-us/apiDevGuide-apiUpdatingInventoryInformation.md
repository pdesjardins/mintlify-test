---
title: "Updating stock"
id: apiUpdatingInventoryInformation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUpdatingInventoryInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating stock information"
previousSectionFile: apiDevGuide-apiUpdatingInventoryInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating stock information"
nextSectionFile: apiDevGuide-portalApiGettingRestaurantInfoOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 6. Restaurant info"
externalReferences: [https://doc.toasttab.com/openapi/stock/overview/]
excerpt: "You can use the stock API to update stock inventory information for menu items and modifiers (via their underlying menu item references)."
keywords: ["PUT", "MenuItemInventory", "multiLocationId", "IN_STOCK", "OUT_OF_STOCK", "QUANTITY", "itemGuidValidity", "VALID", "INVALID"]
procedures: 0
codeExamples: 3
---

You can use the [stock
  API](https://doc.toasttab.com/openapi/stock/overview/) to update stock inventory information for menu items and
  modifiers (via their underlying menu item references).



> **Note**
> 
> For information on getting inventory information, see [Getting stock using the stock webhook](apiDevGuide-apiUsingTheStockWebhook) and [Getting stock information using the stock API](apiDevGuide-apiUsingTheStockApi).


To update inventory information for menu items, submit a
  `PUT` request to the stock API's `/inventory/update`
  endpoint. The message body of the `PUT` request must contain an
  array of objects that provide information about the menu items to
  update.

The following example **curl** command sends a
  `PUT` request to the `/inventory/update`
  endpoint.

**Example 5.8. Update menu item inventory information**

```
curl -X PUT \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: e4c1f40d-3247-4b8b-9891-52f445930fa3" \
-H "Content-Type: application/json" \
-d @my-item-inventory-data.json \
https://`[toast-api-hostname]`/stock/v1/inventory/update
```



(1) Use the Toast-Restaurant-External-ID
        request parameter to specify the GUID of the restaurant you want to
        update inventory for. The GUID must be for an individual restaurant
        location, not the GUID for a restaurant group or management
        group.

(2) Specify the data type of the message body in the
        Content-Type header field. The value must be
        application/json.

(3) Include the array of menu items to update in the message body of
        the PUT request. This example
        curl command sends message body data from the
        contents of the my-item-inventory-data.json file.

  
For each menu item to update, include a `MenuItemInventory`
  object in the message body with the following values:

- An identifier for the menu item. This may be either the menu
      item's `multiLocationId` or its `guid`.

If you use a `multiLocationId`, then the Toast platform
      will use that ID along with the restaurant GUID in the request header to
      resolve which menu item version is affected by the update.

See [Toast identifiers](apiDevGuide-portalToastIdentifiers) for more information on these two
      identifier types.


- The status for the menu item, which must be one of the
      following:

- `IN_STOCK`


- `OUT_OF_STOCK`


- `QUANTITY`




- For menu items with a stock status of `QUANTITY`, you
      must also provide a `quantity` value. This number should be
      greater than 0 (such as 0.5, 7.0, or 10.75). Note that if you provide 0
      as the `quantity` for a menu item that has a
      `QUANTITY` stock status, the stock API will accept this value
      but it will set the menu item's stock status to
      `OUT_OF_STOCK`.

*Do not* include a `quantity` value
      for menu items with a status of `IN_STOCK` or
      `OUT_OF_STOCK`.



The following example shows a JSON message body data that provides
  information about the menu items to update.

**Example 5.9. JSON message body content to update menu items**

```
[
    {
        "multiLocationId": "100000000171238879",
        "status": "IN_STOCK"
    },
    {
        "multiLocationId": "100000000171239701",
        "status": "QUANTITY",
        "quantity": 5.0
    },
    {
        "guid": "88521da5-198e-435b-a5ba-a09983525cf9",
        "status": "OUT_OF_STOCK"
    },
]
```



(1) This object uses a multiLocationId to identify the
        menu item to update and sets the menu item's stock status to
        IN_STOCK.

(2) This object uses a multiLocationId to identify the
        menu item to update. It sets the menu item's stock status to
        QUANTITY and specifies in the quantity value
        that there are five units of the menu item in stock.

(3) This object uses a guid to identify the menu item
        to update and sets the menu item's stock status to
        OUT_OF_STOCK.

  
The response for an update request includes a [`MenuItemInventory`
  object](apiDevGuide-apiUsingTheStockApi#portalMenuItemInventoryObject) with the inventory information for each menu item identifier
  you submitted in the request. The stock API sets the
  `itemGuidValidity` value of each `MenuItemInventory`
  object to indicate whether it found a matching menu item and made the
  update. `VALID` indicates a matching item was found and its stock
  status was updated. `INVALID` indicates no matching item was
  found and no action was taken for that identifier. If a menu item's status
  is `INVALID`, your integration should update the list of menu
  items it associates with the restaurant location.



> **Note**
> 
> You can use the [menus API](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI) to
    retrieve a fully resolved set of menus for each restaurant location,
    including identifiers for all of the location's menu items.


The following example shows the JSON response data for a PUT request
  to the `/inventory/update` endpoint.

**Example 5.10. Inventory update response**

```
[
    {
        "guid": "7d850cd0-c014-46f0-bfa6-b1f920c03743", 
        "itemGuidValidity": "VALID",
        "status": "IN_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171238879",
        "versionId": "7d850cd0-c014-46f0-bfa6-b1f920c03743"
    },
    {
        "guid": "79977142-e076-4727-9b69-9176726b1603",
        "itemGuidValidity": "VALID",
        "status": "QUANTITY",
        "quantity": 5.0,
        "multiLocationId": "100000000171239701",
        "versionId": "79977142-e076-4727-9b69-9176726b1603"
    },
    {
        "guid": "88521da5-198e-435b-a5ba-a09983525cf9",
        "itemGuidValidity": "VALID",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171241912",
        "versionId": "88521da5-198e-435b-a5ba-a09983525cf9"
    },
    {
        "guid": "78271a25-cce4-4317-be6e-67be12722d20",
        "itemGuidValidity": "INVALID",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "null",
        "versionId": "78271a25-cce4-4317-be6e-67be12722d20"
    },
    {
        "guid": "null",
        "itemGuidValidity": "INVALID",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "400000000861576949",
        "versionId": "null"
    }
]
```



(1) Return data for a menu item whose status was set to
        IN_STOCK.

(2) Return data for a menu item whose status was set to
        QUANTITY and whose quantity was set to
        5.0.

(3) Return data for a menu item whose status was set to
        OUT_OF_STOCK.

(4) Return data for a menu item guid that does not have
        a matching menu item in the restaurant location's menu configuration.
        Your integration should update the list of menu items it associates
        with the restaurant location to remove this menu item.

(5) Return data for a menu item multiLocationId that
        does not have a matching menu item in the restaurant location's menu
        configuration. Your integration should update the list of menu items
        it associates with the restaurant location to remove this menu
        item.

  
Note that, if your integration also uses the [stock webhook](apiDevGuide-apiStockWebhook),
  your webhook endpoint receives a message indicating that an inventory update
  has occurred whenever updates are made using the stock API.

