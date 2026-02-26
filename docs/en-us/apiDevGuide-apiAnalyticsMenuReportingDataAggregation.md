---
title: "Aggregating the menu reporting data"
id: apiAnalyticsMenuReportingDataAggregation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataRetrieveData.md
previousSectionTitle: "Retrieving the menu reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsMenuReportingDataUnderstandingData.md
nextSectionTitle: "Understanding the menu reporting data"
excerpt: "The default way to view menu reporting data is by day for each location. You can choose to further aggregate the data by menu, menu group, menu item, or modifier. The groupBy value in the message..."
keywords: ["aggregating", "menu", "reporting", "data", "groupBy", "MENU", "MENU_GROUP", "MENU_ITEM", "MODIFIER", "YYYYMMDD"]
procedures: 0
codeExamples: 5
---

The default way to view menu reporting data is by day for each location. You can choose to further aggregate the data by menu, menu group, menu item, or modifier. The `groupBy` value in the message body of the `/era/v1/menu/day` or `/era/v1/menu/week` request groups the data by one of these options:

- `MENU` to group by menu


- `MENU_GROUP` to group by menu group


- `MENU_ITEM` to group by menu item


- `MODIFIER` to group by modifier





> **Note**
> 
> You can only use the `groupBy` value if requesting data for a `day` or `week` time range.


The menu reporting data you retrieve includes an object for every available combination of business date, restaurant, and menu entity. If there is no information correlated to a combination of data, then there is no object. For example, if a menu item was not ordered on Monday, there is no data available for the menu item on Monday for the restaurant. Another example is a menu that is only available on Sundays. There is no data for that menu at that restaurant for days other than Sunday.



> **Note**
> 
> You can only aggregate using one value, either `MENU`, `MENU_GROUP`, `MENU_ITEM`, or `MODIFIER`.


The following example shows the message body for a `/era/v1/menu/day` request that uses the `groupBy`value with `MENU`.


```
{
  "startBusinessDate": "20220101",
  "endBusinessDate": "20220101",
  "restaurantIds": [],
  "groupBy": ["MENU"]
}

```



    <tr>
      <td>[(1)](#co-d1e4831F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The start date of the time range for the menu reporting data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e4833F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The end date of the time range for the menu reporting data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e4835F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The list of restaurant GUIDs from the management group to include in the menu reporting data. If any restaurants are listed, the restaurant GUIDs not listed are excluded. When left blank, all restaurants are included by default.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e4837F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>This request is for menu reporting data grouped by menu.</td>
    </tr>
When you use `MENU`, the menu reporting data includes objects with information related to a menu for a specific restaurant and day. If there is no information correlated to a combination of data, then there is no object. The following list shows possible objects in the menu reporting data for two restaurants, covering two days and two menus. The objects can appear in any order in the menu reporting data. They are not organized chronologically or alphabetically.


```
Restaurant 1, Day 1, Menu 1
Restaurant 1, Day 1, Menu 2
Restaurant 1, Day 2, Menu 2
Restaurant 2, Day 1, Menu 1
Restaurant 2, Day 2, Menu 1
Restaurant 2, Day 2, Menu 2
```

In the list above, the first object includes menu information related to Menu 1 on Day 1 for Restaurant 1.

When you use `MENU_GROUP`, the menu reporting data includes objects with information related to a menu group for a specific restaurant and day. If there is no information correlated to a combination of data, then there is no object. The following list shows possible objects in the menu reporting data for two restaurants, covering two days and three menu groups. The objects can appear in any order in the menu reporting data. They are not organized chronologically or alphabetically.


```
Restaurant 1, Day 1, Menu Group 1
Restaurant 1, Day 1, Menu Group 2
Restaurant 1, Day 1, Menu Group 3
Restaurant 1, Day 2, Menu Group 1
Restaurant 1, Day 2, Menu Group 2
Restaurant 2, Day 1, Menu Group 1
Restaurant 2, Day 1, Menu Group 3
Restaurant 2, Day 2, Menu Group 1
Restaurant 2, Day 2, Menu Group 2
```

In the list above, the first object includes menu information related to Menu Group 1 on Day 1 for Restaurant 1.

When you use `MENU_ITEM`, the menu reporting data includes objects with information related to a menu item for a specific restaurant and day. If there is no information correlated to a combination of data, then there is no object. The following list shows possible objects in the menu reporting data for two restaurants, covering two days and four menu items. The objects can appear in any order in the menu reporting data. They are not organized chronologically or alphabetically.


```
Restaurant 1, Day 1, Menu Item 1
Restaurant 1, Day 1, Menu Item 2
Restaurant 1, Day 1, Menu Item 3
Restaurant 1, Day 2, Menu Item 1
Restaurant 1, Day 2, Menu Item 2
Restaurant 1, Day 2, Menu Item 4
Restaurant 2, Day 1, Menu Item 1
Restaurant 2, Day 1, Menu Item 3
Restaurant 2, Day 1, Menu Item 4
Restaurant 2, Day 2, Menu Item 1
Restaurant 2, Day 2, Menu Item 2
Restaurant 2, Day 2, Menu Item 4
```

In the list above, the first object includes menu information related to Menu Item 1 on Day 1 for Restaurant 1.

When you use `MODIFIER`, the menu reporting data includes objects with information related to a modifier for a specific restaurant and day. If there is no information correlated to a combination of data, then there is no object. The following list shows possible objects in the menu reporting data for two restaurants, covering two days, and three modifiers. The objects can appear in any order in the menu reporting data. They are not organized chronologically or alphabetically.

- Restaurant 1, Day 1, Modifier 1


- Restaurant 1, Day 1, Modifier 2


- Restaurant 1, Day 1, Modifier 3


- Restaurant 1, Day 2, Modifier 1


- Restaurant 1, Day 2, Modifier 2


- Restaurant 2, Day 1, Modifier 1


- Restaurant 2, Day 1, Modifier 3


- Restaurant 2, Day 2, Modifier 1


- Restaurant 2, Day 2, Modifier 2




```
Restaurant 1, Day 1, Modifier 1
Restaurant 1, Day 1, Modifier 2
Restaurant 1, Day 1, Modifier 3
Restaurant 1, Day 2, Modifier 1
Restaurant 1, Day 2, Modifier 2
Restaurant 2, Day 1, Modifier 1
Restaurant 2, Day 1, Modifier 3
Restaurant 2, Day 2, Modifier 1
Restaurant 2, Day 2, Modifier 2
```

In the list above, the first object includes menu information related to Modifier 1 on Day 1 for Restaurant 1.

## Example of menu reporting data aggregated by menu item

The following example requests menu reporting data for two days and two restaurants, and is grouped into subsections by menu item.

### Request for menu reporting data

The following example **curl** command sends a `POST` request to the `/era/v1/menu/week` endpoint.


```
curl -i -X POST \ 'https://[toast-api-hostname]/era/v1/menu/week' \
  -H 'Authorization: Bearer [token]' \
  -H 'Content-Type: application/json' \
  -d @[request-info].json \
```



    <tr>
      <td>[(1)](#co-d1e5153F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Send a `POST` request to the `/era/v1/menu/&#123;timeRange&#125;` endpoint of the analytics API. The `&#123;timeRange&#125;` in this example is `week`.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e5155F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Include an authentication token. For more information, see [Authentication and restaurant access](apiDevGuide-authentication).</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e5157F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Set the data type of the message body to `application/json`.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e5159F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Include details about the requested menu reporting data in the message body. The following example is the message body for this **curl** command example.</td>
    </tr>
### Message body for the menu reporting data request

The following example shows the message body of the `/era/v1/menu/week` request that uses the `groupBy` value with `MENU_ITEM`.


```
{
  "restaurantIds": ["95a96d7b-dbf5-46d3-98c5-c65c8ad18021", "b6bae410-1316-4d3b-b01f-47a758811db2"],
  "excludedRestaurantIds": [],
  "startBusinessDate": "20220901",
  "endBusinessDate": "20220906",
  "groupBy": ["MENU_ITEM"]
}

```



    <tr>
      <td>[(1)](#co-d1e5183F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The list of restaurant GUIDs from the management group to include in the menu reporting data. Restaurant GUIDs not listed are excluded.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e5185F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The list of restaurant GUIDs from the management group to exclude from the menu reporting data. For this example, `excludedRestaurantIds` must be empty because restaurant GUIDs are already included with the `restaurantIds` value.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e5187F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The start date of the time range for the menu reporting data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e5189F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The end date of the time range for the menu reporting data, in `YYYYMMDD` format.</td>
    </tr>
    <tr>
      <td>[(5)](#co-d1e5191F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>This request is for menu reporting data grouped by menu item.</td>
    </tr>
### Response to the menu reporting data request

The following example shows the response from the `/era/v1/menu/week` endpoint.


```
"bd9fb800-7c1e-40b8-9e5d-1010430a6a09"
```



    <tr>
      <td>[(1)](#co-d1e5210F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>The GUID for the menu reporting data request, also called the `reportRequestGuid`. For more information about how to retrieve data using the analytics API, see [Understanding the analytics API process](apiDevGuide-apiAnalyticsUnderstandingProcess).</td>
    </tr>
### Request to retrieve the menu reporting data

The following example **curl** command sends a `GET` request to the `/era/v1/menu/&#123;reportRequestGuid&#125;` endpoint.


```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/menu/
bd9fb800-7c1e-40b8-9e5d-1010430a6a09/' \
  -H 'Authorization: Bearer [token]'
```



    <tr>
      <td>[(1)](#co-d1e5235F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Send a `GET` request to the `/era/v1/menu` endpoint of the analytics API.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e5237F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Include the GUID for the menu reporting data request, also called the `reportRequestGuid`. For more information about how to retrieve data using the analytics API, see [Understanding the analytics API process](apiDevGuide-apiAnalyticsUnderstandingProcess).</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e5239F987D2F6-E937-4A8F-AC23-BD439B5BF371)</td>
      <td>Include an authentication token. For more information, see [Authentication and restaurant access](apiDevGuide-authentication).</td>
    </tr>
### Response to the retrieval request for menu reporting data

The following example shows the response from the `/era/v1/menu/&#123;reportRequestGuid&#125;` endpoint.


```
[
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220902",
        "netSalesAmount": 32.97,
        "grossSalesAmount": 32.97,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 3.0,
        "averagePrice": 10.99,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "8588c16e-5f17-4144-b4c0-47f4f42ed4c0",
        "menuItemName": "Pancake Special"
    },
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220902",
        "netSalesAmount": 5.98,
        "grossSalesAmount": 5.98,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 2.0,
        "averagePrice": 2.99,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "4f5469c1-7f55-4f80-a1a6-d69253cd916b",
        "menuItemName": "Coffee"
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220902",
        "netSalesAmount": 95.29,
        "grossSalesAmount": 107.41,
        "discountAmount": 12.12,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 9.0,
        "averagePrice": 11.93,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "a6a561ae-7c7a-4275-9345-ea3c0a72368f",
        "menuItemName": "Full English Breakfast"
    },
    [content omitted]
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220902",
        "netSalesAmount": 51.96,
        "grossSalesAmount": 51.96,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 4.0,
        "averagePrice": 12.99,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "8588c16e-5f17-4144-b4c0-47f4f42ed4c0",
        "menuItemName": "Pancake Special"
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220901",
        "netSalesAmount": 54.95,
        "grossSalesAmount": 54.95,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 5.0,
        "averagePrice": 10.99,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "8588c16e-5f17-4144-b4c0-47f4f42ed4c0",
        "menuItemName": "Pancake Special"
    },
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220901",
        "netSalesAmount": 77.5,
        "grossSalesAmount": 90.17,
        "discountAmount": 12.67,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 8.0,
        "averagePrice": 11.27,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "a6a561ae-7c7a-4275-9345-ea3c0a72368f",
        "menuItemName": "Full English Breakfast"
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220901",
        "netSalesAmount": 2.99,
        "grossSalesAmount": 2.99,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 1.0,
        "averagePrice": 2.99,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "4f5469c1-7f55-4f80-a1a6-d69253cd916b",
        "menuItemName": "Coffee"
    },
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": null,
        "restaurantLocationCode": "",
        "businessDate": "20220901",
        "netSalesAmount": 94.67,
        "grossSalesAmount": 94.67,
        "discountAmount": 0.0,
        "refundAmount": 0.0,
        "voidAmount": 0.0,
        "quantitySold": 8.0,
        "averagePrice": 11.83,
        "wasteCount": 0.0,
        "wasteAmount": 0.0,
        "menuItemGuid": "a6a561ae-7c7a-4275-9345-ea3c0a72368f",
        "menuItemName": "Full English Breakfast"
    },
    [content omitted]
]

```

