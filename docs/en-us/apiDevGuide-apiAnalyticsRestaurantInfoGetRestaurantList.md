---
title: "Getting a list of restaurants in a management group"
id: apiAnalyticsRestaurantInfoGetRestaurantList
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Restaurant information"
previousSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.md
previousSectionTitle: "Restaurant information"
excerpt: "You can use the /era/v1/restaurants-information endpoint of the analytics API to retrieve a list of the restaurants and their statuses..."
keywords: [getting,list,restaurants,management,group,restaurantGuid,restaurantName,testMode]
procedures: 0
codeExamples: 0
---

### Getting a list of restaurants in a management group

You can use the `/era/v1/restaurants-information`endpoint of the analytics API to retrieve a list of the restaurants and their statuses in the management group associated with your account. This list includes the `restaurantGuid`and the `restaurantName`, and the restaurant statuses for `active`, `testMode`, and `archived`.

- The `restaurantGuid`is the unique GUID assigned to the restaurant by the Toast platform.


- The `restaurantName`is the restaurant’s name.


- The `active`value indicates whether the restaurant is activated or not. A `true`value indicates the restaurant is activated, while a `false`value indicates the restaurant is deactivated.


- The `testMode`value indicates whether the restaurant is in test mode or not. A `true`value indicates the restaurant is in test mode, while a `false`value indicates the restaurant is not in test mode.


- The `archived`value indicates whether the restaurant is archived or not. A `true`value indicates the restaurant is archived, while a `false`value indicates the restaurant is not archived. A common reason for archiving a restaurant is if the restaurant was created in error.



The `restaurantGuid`is the unique GUID assigned to the restaurant by the Toast platform. The `restaurantName`is the restaurant’s name.

The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsOmitChunkFromSearchIndex.html#apiAnalyticsRateLimiting).

#### Request for restaurant information

The following example shows a **curl**command that sends a `GET`request to the `/era/v1/restaurants-information`endpoint.

```
curl -X GET 'https://*`[toast-api-hostname]`*/era/v1/restaurants-information' \[(1)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e17846FAD0EEB-57EF-441A-9E58-614F985F6270-co)
-H 'Authorization: Bearer *`[token]`*'[(2)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e17866FAD0EEB-57EF-441A-9E58-614F985F6270-co)

```



(1) Send a GETrequest to the /era/v1/restaurants-informationendpoint of the analytics API.

(2) Include an authentication token. For more information, see Authentication and restaurant access .

#### Response to the request for restaurant information

The following example shows the response from the `/era/v1/restaurants-information`endpoint.

```
[
    {
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",[(1)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e1009877E149E8-9F61-41FB-B0A1-9C937BA546FC-co)
        "restaurantName": "Grove Place Cafe"[(2)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e1010077E149E8-9F61-41FB-B0A1-9C937BA546FC-co)
        "active": true,[(3)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e1010277E149E8-9F61-41FB-B0A1-9C937BA546FC-co)
        "testMode": false,[(4)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e1010477E149E8-9F61-41FB-B0A1-9C937BA546FC-co)
        "archived": false[(5)](apiDevGuide-apiAnalyticsRestaurantInfoGetRestaurantList.html#d1e1010677E149E8-9F61-41FB-B0A1-9C937BA546FC-co)
    },
    {
        "restaurantGuid": "b6bae410-1316-4d3b-b01f-47a758811db2",
        "restaurantName": "Summer Street Cafe"
        "active": true,
        "testMode": false,
        "archived": false
    },
    {
        "restaurantGuid": "b6108638-ed33-4a26-b78d-37a9ae68f71f",
        "restaurantName": "Third Street Cafe"
        "active": false,
        "testMode": true,
        "archived": false
    },
    {
        "restaurantGuid": "43211888-2860-46c7-a8c8-32ba462e1280",
        "restaurantName": "West End Cafe"
        "active": true,
        "testMode": false,
        "archived": false
    }
]

```



(1) The unique GUID assigned to the restaurant by the Toast platform.

(2) The restaurant’s name.

(3) Indicates whether or not the restaurant is activated. For this example, the restaurant is activated.

(4) Indicates whether or not the restaurant is in test mode. For this example, the restaurant is not in test mode.

(5) Indicates whether or not the restaurant is archived. For this example, the restaurant is not archived.

