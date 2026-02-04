---
title: "Getting stock information using the stock API"
id: apiUsingTheStockApi
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingStockInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting stock information"
previousSectionFile: apiDevGuide-apiUsingTheStockWebhook.md
previousSectionTitle: "Getting stock using the stock webhook"
nextSectionFile: apiDevGuide-apiUpdatingInventoryInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating stock information"
externalReferences: [https://doc.toasttab.com/openapi/stock/overview/]
excerpt: "You can use the stock API to retrieve stock inventory information for menu items and modifiers (via their underlying menu item references)."
keywords: ["OUT_OF_STOCK", "QUANTITY", "IN_STOCK", "MenuItemInventory", "multiLocationId", "itemGuidValidity", "VALID", "INVALID", "versionId"]
procedures: 0
codeExamples: 0
---

You can use the [stock API](https://doc.toasttab.com/openapi/stock/overview/) to retrieve stock inventory information for menu items and modifiers (via their underlying menu item references).

The stock API has the following endpoints for retrieving inventory information:

- `/inventory` retrieves inventory information for all menu items in a restaurant that have an stock status of `OUT_OF_STOCK` or `QUANTITY`. This endpoint ignores menu items that have a stock status of `IN_STOCK`because these items are not considered at risk of going out of stock.

An optional `status` query parameter lets you retrieve inventory information for menu items that have a specified stock status of either `OUT_OF_STOCK` or `QUANTITY`.


- `/inventory/search` retrieves inventory information for the menu items in a list that you provide in the request body. The returned information for each menu item in the list will have a stock status of `OUT_OF_STOCK`, `QUANTITY`, or `IN_STOCK`.



The inventory information for each menu item is returned in a `MenuItemInventory`object, which has the following properties:

- `guid`: The unique GUID assigned to the menu item by the Toast platform.


- `status`: The stock status of the menu item. This value is one of the following:

- `OUT_OF_STOCK`: The menu item is not in stock in the restaurant.


- `QUANTITY`: The menu item is in limited supply (1 or more items left).


- `IN_STOCK`: The menu item is in stock in the restaurant. Note that no quantity is associated with the menu item but it is considered available and not at risk of going out of stock.




- `quantity`: The amount of stock remaining for the menu item.

- For menu items with a stock status of `QUANTITY`, the `quantity` value is a number that is greater than 0 (such as 0.5, 7.0, or 10.75).


- For menu items with a stock status of `IN_STOCK` or `OUT_OF_STOCK`, the `quantity` value is `null`.

The `null` value for `IN_STOCK`items indicates that there is no specific quantity associated with the item but it is assumed to be available.




- `multiLocationId`: A consistent identifier that applies to all versions of a menu item that is shared across locations.

Toast support recommends that requests sent to Toast APIs use a combination of a restaurant location's GUID and the `multiLocationId` to identify a menu item (instead of the menu item's `guid` value). Integration clients can extract the `multiLocationId` from menus API or stock API responses and use it in subsequent requests to Toast APIs. See [Toast identifiers](portalToastIdentifiers.html)for more information.


- `itemGuidValidity`: Indicates whether a menu item identifier that you included in your request is valid or not.

No identifiers are submitted for requests to the `/inventory` endpoint, so `itemGuidValidity`is always `VALID` in responses from this endpoint.

For requests to the `[/inventory/search](apiUsingTheStockApi.html#apiInventorySearch)` and `[/inventory/update](apiUpdatingInventoryInformation.html)`endpoints, the stock API sets the `itemGuidValidity`value to `VALID` if it finds a match for the menu item. If the stock API does not find a match, either because the menu item does not exist at the location or because it has been archived, it sets `itemGuidValidity` to `INVALID` for that menu item. If a menu item is invalid, your integration should update the list of menu items it associates with the restaurant location to remove that menu item.

For an invalid menu item, the stock API sets the following placeholders for the other JSON values:

- The `status` value is set to `OUT_OF_STOCK`.


- The `quantity` value is set to `null`.


- If the request included a `guid` as the identifier for the menu item, that unmatched `guid`is retained in the `guid` value but the `multiLocationId` value is set to `null`because the stock API is unable to resolve it.


- If the request included a `multiLocationId` as the identifier for the menu item, that unmatched `multiLocationId` is retained in the `multiLocationId` value but the `guid` is set to `null` because the stock API is unable to resolve it.





> **Note**
> 
> You can use the [menus API](apiGettingMenuInformationFromTheMenusAPI.html) to retrieve a fully resolved set of menus for each restaurant location, including identifiers for all of the location's menu items.



- `versionId`: This value is reserved for future use.



The following sections provide more information about retrieving inventory information for menu items.



> **Note**
> 
> For more information on how to change a menu item's inventory information using the stock API's `/inventory/update`endpoint, see [Updating stock](apiUpdatingInventoryInformation.html). For more information on how to change a menu item's inventory status using Toast Web, see [Menu item inventory overview](adminMenuItemInventoryOverview.html).


## Getting all stock information for a location

Send a `GET` request to the `/inventory` endpoint of the stock API to get inventory information for the menu items of a restaurant. The request returns a JSON array of `MenuItemInventory` objects containing information on the stock status and quantity of the menu items.

Information is returned only for menu items that have an inventory status of `QUANTITY` or `OUT_OF_STOCK`.

Inventory information is not returned for menu items that have an `IN_STOCK` status, because these items are not considered at risk for going out of stock.

The following example **curl** command sends a `GET` request to the `/inventory`endpoint.

**Example 5.1. Get all menu item inventory for a location**

```
curl -X GET \
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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
https://`[toast-api-hostname]`/stock/v1/inventory
```



(1) Use the Toast-Restaurant-External-ID request parameter to specify the GUID of the restaurant from which to retrieve menu item inventories. The GUID must be for an individual restaurant, not the GUID for a restaurant group or management group.

  
The following example shows the JSON response data for a GET request to the `/inventory` endpoint.

**Example 5.2. Get all inventory return data**

```
[
    \{
        "guid": "79977142-e076-4727-9b69-9176726b1603",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171238879",
        "versionId": "79977142-e076-4727-9b69-9176726b1603"
    },
    \{
        "guid": "a4ccc387-912a-4b1d-8062-26b44eed7216",
        "status": "QUANTITY",
        "quantity": 25.0,
        "multiLocationId": "100000000171239701",
        "versionId": "a4ccc387-912a-4b1d-8062-26b44eed7216"
    },
    \{
        "guid": "8a2f952d-4dca-4eb0-b867-445f3a674bad",
        "status": "QUANTITY",
        "quantity": 10.75,
        "multiLocationId": "100000000171239569",
        "versionId": "8a2f952d-4dca-4eb0-b867-445f3a674bad"
    \}
]
```



(1) The GET request returns a JSON array of menu item inventory objects containing information on menu items with a status of QUANTITY or OUT_OF_STOCK.

(2) The guid value contains the unique Toast platform identifier for the menu item.

(3) The status value is QUANTITY or OUT_OF_STOCK. The /inventory endpoint only returns information for menu items that have a stock status of QUANTITY or OUT_OF_STOCK. The endpoint does not return information for menu items that have an IN_STOCK status.

(4) The multiLocationId value for the menu item.Toast support recommends using a combination of a menu item's multiLocationId and a restaurant location's GUID, instead of the menu item's guid, to identify menu items in subsequent requests. See Toast identifiers for more information.

(5) The quantity value indicates the amount of stock remaining for menu items with an inventory status of QUANTITY. The quantity value is null for menu items with an OUT_OF_STOCK inventory status.

  
## Getting inventory by status

You can restrict menu items in the response to those with either a `QUANTITY` or `OUT_OF_STOCK` status by using the `status` query parameter of the `/inventory`endpoint. The format of the `status` request parameter is one of the following:

- Use a value of `QUANTITY` to get all menu items with an inventory status of `QUANTITY`:

```
https://`[toast-api-hostname]`/stock/v1/inventory?status=QUANTITY
```


- Use a value of `OUT_OF_STOCK` to get all menu items with an inventory status of `OUT_OF_STOCK`:

```
https://`[toast-api-hostname]`/stock/v1/inventory?status=OUT_OF_STOCK
```



The request returns a JSON array of `MenuItemInventory` objects containing inventory information for the menu items. Information is returned only for menu items that have the requested inventory status.

The following example **curl** command sends a `GET` request to the `/inventory`endpoint with a `status` query parameter of `OUT_OF_STOCK`.

**Example 5.3. Get inventory by status**

```
curl -X GET \
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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
https://`[toast-api-hostname]`/stock/v1/inventory?status=OUT_OF_STOCK
```



(1) Use the Toast-Restaurant-External-ID request parameter to specify the GUID of the restaurant from which you want to retrieve menu item inventories by status. The GUID must be for an individual restaurant, not the GUID for a restaurant group or management group.

(2) Specify status=OUT_OF_STOCK to retrieve menu items that are not in stock.

  
The following example shows the JSON response for the `GET` request.

**Example 5.4. Get inventory by status return data**

```
[
    \{
        "guid": "88521da5-198e-435b-a5ba-a09983525cf9",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171238879",
        "versionId": "88521da5-198e-435b-a5ba-a09983525cf9"
    },
    \{
        "guid": "79977142-e076-4727-9b69-9176726b1603",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171239701",
        "versionId": "79977142-e076-4727-9b69-9176726b1603"
    \}
]
```



(1) This GET request returns a JSON array of menu item inventory objects for menu items with a status of OUT_OF_STOCK.

(2) The guid value contains the unique Toast platform identifier for the menu item.

(3) The status value is OUT_OF_STOCKfor the menu item. The status value would be QUANTITY if you had specified status=QUANTITY as the request parameter.

(4) The quantity value indicates the amount of stock remaining for menu items with an inventory status of QUANTITY, and is null for menu items with an OUT_OF_STOCK inventory status.

(5) The multiLocationId value for the menu item.Toast support recommends using a combination of a menu item's multiLocationId and a restaurant location's GUID, instead of the menu item's guid, to identify menu items in subsequent requests. See Toast identifiers for more information.

  
## Searching inventory for specific menu items

To retrieve inventory information for a list of menu items, you send a `PUT` request to the `/inventory/search` endpoint. The request must include a message body that contains an `InventorySearchRequest`object with one or both of these values:

- A `multiLocationIds` value that contains an array of menu item multi-location IDs to search for.


- A `guids` value that contains an array of menu item GUIDs to search for.



For information on these two identifier types, see [Toast identifiers](portalToastIdentifiers.html).

The following example shows the message body for a `POST` request to the `/inventory/search` endpoint using both `multiLocationIds` and `guids`.

**Example 5.5. JSON message body content to search inventory by menu items**

```
\{
    "multiLocationIds": [
        "100000000171238879",
        "100000000171239701"
    ]
    "guids": [
        "88521da5-198e-435b-a5ba-a09983525cf9"
    ]
\}
```

  
The resource returns a JSON array of `MenuItemInventory` objects containing inventory information for the requested menu items. Inventory information is returned for all menu items on the list, regardless of their inventory status (`QUANTITY`, `OUT_OF_STOCK`, or `IN_STOCK`).

For requests to the `/inventory/search` endpoint, the stock API sets the `itemGuidValidity` value of the `MenuItemInventory` object to `VALID` if it finds a match for the menu item during the search. If the stock API does not find a match, it sets `itemGuidValidity` to `INVALID` for that menu item. If a menu item is invalid, your integration should update the list of menu items it associates with the restaurant location to remove that menu item.

For an invalid menu item, the stock API sets the following placeholders for the other JSON values:

- The `status` value is set to `OUT_OF_STOCK`.


- The `quantity` value is set to `null`.


- If the search request included a `guid` as the identifier for the menu item, that unmatched `guid` is retained in the `guid` value but the `multiLocationId` value is set to `null`because the stock API is unable to resolve it.


- If the search request included a `multiLocationId` as the identifier for the menu item, that unmatched `multiLocationId` is retained in the `multiLocationId` value but the `guid` is set to `null` because the stock API is unable to resolve it.



If a valid menu item went out of stock and then came back in stock, its inventory status is returned as `IN_STOCK`.

The following example **curl** command sends a `POST` request to the `/inventory/search` endpoint.

**Example 5.6. Search inventory by menu items**

```
curl -X POST \
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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
-H "Content-Type: application/json" \
-d @my-item-search-data.json \
https://`[toast-api-hostname]`/stock/v1/inventory/search
```



(1) Use the Toast-Restaurant-External-ID request parameter to specify the GUID of the restaurant from which you want to retrieve menu item inventories by status. The GUID must be for an individual restaurant location, not the GUID for a restaurant group or management group.

(2) Specify the data type of the message body in the Content-Type header field. The value must be application/json.

(3) Include the menu item list in the message body of the POST request. This example curl command sends message body data from the contents of the my-item-search-data.jsonfile.

  
The following example shows the JSON response data for a `POST` request to the `/inventory/search` resource.

**Example 5.7. Search inventory by menu items response**

```
[
    \{
        "guid": "2f91e217-ec31-4659-a7ba-dc66d76a1b5b",
        "itemGuidValidity": "VALID",
        "status": "IN_STOCK",
        "quantity": null,
        "multiLocationId": "100000000171238879",
        "versionId": "2f91e217-ec31-4659-a7ba-dc66d76a1b5b"
    },
    \{
        "guid": "ad4d928d-0740-4617-96db-bd2a4b1ae1e5",
        "itemGuidValidity": "VALID",
        "status": "QUANTITY",
        "quantity": 100.0,
        "multiLocationId": "100000000171239701",
        "versionId": "ad4d928d-0740-4617-96db-bd2a4b1ae1e5"
    },
    \{
        "guid": "88521da5-198e-435b-a5ba-a09983525cf9",
        "itemGuidValidity": "INVALID",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "null",
        "versionId": "88521da5-198e-435b-a5ba-a09983525cf9"
    },
    \{
        "guid": "null",
        "itemGuidValidity": "INVALID",
        "status": "OUT_OF_STOCK",
        "quantity": null,
        "multiLocationId": "400000000861576949",
        "versionId": "null"
    \}
]
```



(1) The GET request returns a JSON array of menu item inventory objects for the requested menu items.

(2) The guid value contains the unique Toast platform identifier for the menu item.

(3) The status value is one of QUANTITY, OUT_OF_STOCK, or IN_STOCK.

(4) The multiLocationId value for the menu item.Toast support recommends using a combination of a menu item's multiLocationId and a restaurant location's GUID, instead of the menu item's guid, to identify menu items in subsequent requests. See Toast identifiers for more information.

(5) The quantity value indicates the amount of stock remaining for menu items with an inventory status of QUANTITY, and is null for OUT_OF_STOCK and IN_STOCK menu items.

(6) An example of a guid search for a menu item that does not exist at the restaurant being queried or has been archived. Your integration should update the list of menu items it associates with the restaurant location to remove this menu item.

(7) An example of a multiLocationId search for a menu item that does not exist at the restaurant being queried or has been archived. Your integration should update the list of menu items it associates with the restaurant location to remove this menu item.

  
