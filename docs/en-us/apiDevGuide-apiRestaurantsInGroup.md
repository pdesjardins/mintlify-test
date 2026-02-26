---
title: "Getting all restaurants in a management group"
id: apiRestaurantsInGroup
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting restaurant info"
previousSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
previousSectionTitle: "Getting restaurant info"
nextSectionFile: apiDevGuide-apiRestaurantInformation.md
nextSectionTitle: "Getting information about a specific restaurant"
excerpt: "Send a GET request to the /restaurants/v1/groups/{managementGroupGUID}/restaurants endpoint of the restaurants API to get a list of the restaurants in a restaurant management group. The endpoint..."
keywords: ["/restaurants/v1/groups/{managementGroupGUID}/restaurants", "Restaurant", "/restaurants/v1/restaurants/{restaurantGUID}"]
procedures: 0
codeExamples: 2
---

Send a `GET` request to the `/restaurants/v1/groups/{managementGroupGUID}/restaurants`endpoint of the restaurants API to get a list of the restaurants in a restaurant management group. The endpoint returns a JSON array of `Restaurant` objects. Each `Restaurant` object contains the GUID of a restaurant in the restaurant management group.

You can get a restaurant management group's GUID from either of these resources:

- The `/restaurants/v1/restaurants/{restaurantGUID}`endpoint of the restaurants API. See [Getting information about a specific restaurant](docs/en-us/apiDevGuide-apiRestaurantInformation).


- The `/partners/v1/restaurants` endpoint of the partners API (if you have partner-level credentials). See [Location access](docs/en-us/apiDevGuide-apiPartnersGettingAccessibleRestaurants).



The following example **curl** command sends a `GET` request to the `/restaurants/v1/groups/{managementGroupGUID}/restaurants`endpoint.

**Example 6.1. Get all restaurants of a management group**


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
-H "Toast-Restaurant-External-ID: 76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf" \
https://`[toast-api-hostname]`/restaurants/v1/groups/ae6c32fe-f4d2-4dcc-aa82-f30edac96296/restaurants
```



(1) Use the Toast-Restaurant-External-ID request parameter to specify the GUID of one restaurant location in the restaurant management group.

(2) Specify the GUID of the restaurant management group from which to retrieve its restaurant locations.

  
The following example shows the JSON response data for a GET request to the `/restaurants/v1/groups/{managementGroupGUID}/restaurants`endpoint.

**Example 6.2. Get all restaurants return data**


```
[
  {
    "guid": "34ac7aaf-7178-4c6f-af63-c42ebc7e91f7"
  },
  {
    "guid": "76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf"
  },
  {
    "guid": "3eb63e0d-57b1-4c9f-a1b7-5722ae4ef801"
  },
  {
    "guid": "27ffe323-1449-49c6-8d9d-347eafb03d58"
  }
]
```



(1) The guid value contains the unique Toast POS identifier for a restaurant location in the restaurant management group. In this example, the request returns four restaurant locations.

  
