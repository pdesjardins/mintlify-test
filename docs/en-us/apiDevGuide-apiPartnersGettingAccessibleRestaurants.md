---
title: "Location access"
id: apiPartnersGettingAccessibleRestaurants
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAnIntegrationPartnerOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're an integration partner"
previousSectionFile: apiDevGuide-integrationDevProcess.md
previousSectionTitle: "Integration partnership process"
nextSectionFile: apiDevGuide-apiDeveloperPortal.md
nextSectionTitle: "Toast developer portal"
externalReferences: [https://doc.toasttab.com/openapi/restaurants/overview/, https://doc.toasttab.com/openapi/partners/overview/, https://doc.toasttab.com/openapi/partners/operation/connectedRestaurantsGet/]
excerpt: "The..."
procedures: 0
codeExamples: 0
---

The partners webhook and partners API both provide information about the restaurants you can access. With the partners webhook, the Toast platform pushes updates to your system when a restaurant adds your integration, removes your integration, or edits your integration's settings in the Toast platform. This is the preferred method for getting information about the restaurants you can access.

If you need to retrieve information about the restaurants you can access independently of an event that triggers a webhook update, you can use the `/restaurants` endpoint of the partners API.

The payload returned by both the partners webhook and the partners API includes location and group identifiers. You can use these identifiers to map restaurants in your system to Toast's restaurants and GUIDs. For more information, see [Using location and group identifiers](apiDevGuide-apiPartnersGettingAccessibleRestaurants#apiPartnersLocationGroupIDs).

This information only applies if you use a [partner API account](apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts). Integrations that use [restaurant management group API accounts](apiDevGuide-authentication#apiAuthenticationReturnDataRestaurant) cannot use the partners webhook or partners API.

## Getting the restaurants you can access

Restaurant employees who have the Account Admin &gt; Manage Integrations access permission can add your integration to their locations from Toast Partner Integrations, which is the Toast integration marketplace, through their Toast Web account. Restaurant employees with the Manage Integrations access permission can also remove previously connected integrations from the My Integrations page in Toast Web. For more information about restaurant employee access permissions, see [Access permissions reference](adminGuide-adminPermissions).

When a restaurant employee selects your partner integration and gives you access to integrate with that restaurant:

- Information about the restaurant is added to the JSON array that you get from the `/restaurants` endpoint of the partners API.


- A webhook update is sent to your webhook endpoint, if you have one configured.


- The Toast platform sends an automated email message to your onboarding email address. The message includes basic information about the new restaurant connections, including restaurant name, location name, location GUID, and email contact information for the restaurant employee who has added the integration. If a restaurant employee adds multiple locations at the same time, the Toast platform will include all the locations in a single email message.



When a restaurant adds your integration in Toast Partner Integrations, the Toast platform does not directly connect the restaurant to *your customer* account for that restaurant. This action authorizes and grants your partner API account access to the restaurant's data via API. As an integration partner, you are responsible for mapping your own customer accounts to Toast location GUIDs.

For more information about how restaurant employees select integration partners and enable integration access, see [Managing and using integrations and Toast Partner Integrations](adminGuide-adminRestaurantServiceIntegrationsAndToastPartnerIntegrations).

### Getting restaurant access updates from the partners webhook

To use the partners webhook, you must create a *webhook endpoint*. This is the URL of a webhook consumer service that is capable of receiving webhook events from the Toast platform.

Once you have a webhook endpoint, Toast support can create a webhook subscription for your integration that associates your webhook endpoint with the webhook updates that are triggered by restaurants adding, removing, or reconfiguring your integration.

For general information on setting up and using Toast webhooks, see [Webhook basics](apiDevGuide-apiWebhookBasics).

For detailed information on the specific updates provided by the partners webhook, including example payloads, see [Partners webhook](apiDevGuide-apiPartnersWebhook).

### Using the partners API to get restaurant information

To get information about the Toast platform restaurants that your partner API client account can access, you can use the `/restaurants` or `/connectedRestaurants` endpoint of the Toast partners API.

Only partner API accounts can use the `/restaurants`and `/connectedRestaurants` endpoint. If you have a restaurant management group API account, you can use the restaurants API to get information about the restaurants in your group. For more information about account types, see [Toast API accounts](apiDevGuide-apiClientAccounts). For more information about the restaurants API, see the [restaurants API reference documentation](https://doc.toasttab.com/openapi/restaurants/overview/).

The `/restaurants` endpoint returns an array of JSON objects containing information about each restaurant that you have access to. For more information, see the [partners API reference documentation](https://doc.toasttab.com/openapi/partners/overview/).

The `/connectedRestaurants` endpoint returns the same array of restaurant JSON objects as the `/restaurants`endpoint. Using the `/connectedRestaurants` endpoint allows you to navigate the response easier, especially if you are connected to many restaurants.

The `/connectedRestaurants` endpoint uses pagination and allows for additional query parameters. Each response page is also tokenized using page tokens should you need to refer back to a specific data snapshot. For more information on pagination see [Paginating response data](apiDevGuide-apiResponseDataPagination). For more information on using the `/connectedRestaurants`endpoint see [Get connected restaurants](https://doc.toasttab.com/openapi/partners/operation/connectedRestaurantsGet/).



> **Note**
> 
> The partners API updates the list of restaurants that you have access to immediately after a restaurant employee selects your integration.
> For other Toast APIs, such as the orders API or the labor API, it can take up to 15 minutes from the time a restaurant employee gives your integration access before they update their access lists and allow your integration to perform operations at a restaurant. Please note that in some cases, even after the typical 15-minute delay, the Toast platform may require additional time before the newly-connected restaurants become available.


If a restaurant removes a partner's integration, this restaurant is no longer present in the `/restaurants` or `/connectedRestaurants` endpoint return data. Consider restaurant additions and removals when you review the results of this endpoint.

#### How to make a request to /restaurants

Send a `GET` request to the `/restaurants`endpoint of the Toast partners API.


```
https://`[toast-api-hostname]`/partners/v1/restaurants
```



> **Note**
> 
> The `/restaurants` endpoint uses the same rate limiting functionality as other Toast API endpoints. For more information, see [Rate limiting](apiDevGuide-apiRateLimiting).


**Procedure 1.1. To get information about the restaurants you have access to**

1. Authenticate with the Toast user management service using a partner API account. For more information, see [Authentication and restaurant access](apiDevGuide-authentication).


2. Send a `GET` request to the `/restaurants` endpoint of the partners API.

Optionally, include the `lastModified` parameter to limit the return data to restaurants created or modified after a specific date and time. The date and time must be a UTC timestamp in ISO 8601 format, for example: `2020-03-01T00:00:00.000-0000`.

You must URL encode the timestamp before sending it in a request. For example, `2020-03-01T00%3A00%3A00.000%2B0000`.


3. Review the information about each restaurant that you have access to in the JSON data that the `/restaurants`endpoint returns.

The GUID for a restaurant is in the `restaurantGuid` value of the return data. The GUID is a unique identifier. You use the Toast platform GUID for a restaurant when you make Toast API requests for that restaurant.



#### Information in the /restaurants return data

For each restaurant, the `/restaurants` endpoint the JSON response contains the following values:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`restaurantGuid`</td>
      <td>The unique Toast platform identifier for the restaurant.</td>
    </tr>
    <tr>
      <td>`managementGroupGuid`</td>
      <td>The unique Toast platform identifier for a group of restaurants. The management group GUID is the same for all restaurants in the same group. <br/> If a restaurant location does not belong to a restaurant management group, then the management group GUID is null.</td>
    </tr>
    <tr>
      <td>`restaurantName`</td>
      <td>The human-readable name of the restaurant location.</td>
    </tr>
    <tr>
      <td>`locationName`</td>
      <td>The identifier of a specific restaurant location, set on the Restaurant Info screen of the Toast Web. <br/> For example, a restaurant group might assign a location code such as `#1234` to a specific location.</td>
    </tr>
    <tr>
      <td>`createdByEmailAddress`</td>
      <td>The email address of the restaurant employee who connected the restaurant to the partner or who edited the connection details.</td>
    </tr>
    <tr>
      <td>`externalGroupRef`</td>
      <td>An identifier for the restaurant group that is recognized by the partner that made the request to the `/restaurants` endpoint. <br/> This information is entered by the restaurant administrator. If you need information about the restaurant group in this data string, you instruct the restaurant administrator to enter it in the Toast platform configuration for the integration partner connection. <br/> For more information, see [Using location and group identifiers](apiDevGuide-apiPartnersGettingAccessibleRestaurants#apiPartnersLocationGroupIDs).</td>
    </tr>
    <tr>
      <td>`externalRestaurantRef`</td>
      <td>An identifier for the restaurant location that is recognized by the partner that made the request to the `/restaurants` endpoint. <br/> This information is entered by the restaurant administrator. If you need information about the restaurant location in this data string, you instruct the restaurant administrator to enter it in the Toast platform configuration for the integration partner connection. <br/> For more information, see [Using location and group identifiers](apiDevGuide-apiPartnersGettingAccessibleRestaurants#apiPartnersLocationGroupIDs).</td>
    </tr>
    <tr>
      <td>`isoCreatedDate`</td>
      <td>The date and time that the partner connection was created, expressed in ISO 8601 format.</td>
    </tr>
    <tr>
      <td>`isoModifiedDate`</td>
      <td>The most recent date and time that the partner connection was edited, expressed in ISO 8601 format.</td>
    </tr>
    <tr>
      <td>`createdDate`</td>
      <td>The date and time that the partner connection was created, expressed in milliseconds from the UNIX epoch, January 1, 1970 00:00:00 UTC.</td>
    </tr>
    <tr>
      <td>`modifiedDate`</td>
      <td>The most recent date and time that the partner connection was edited, expressed in milliseconds from the UNIX epoch, January 1, 1970 00:00:00 UTC.</td>
    </tr>
  </tbody>
</table>

#### Example /restaurants response

The following example shows the response data from the `/restaurants` endpoint of the partners API.

**Example 1.1. Response data from the /restaurants endpoint**


```
[
   {
      "restaurantGuid":"0001ac81-423c-a426-0008-02426ac8423c",
      "managementGroupGuid":"88f3cca5-39d9-4acc-8627-3116c748f344",
      "restaurantName":"The Good Restaurant",
      "locationName":null, 
      "createdByEmailAddress":"hester@goodrestaurant.com",
      "externalGroupRef":"goodRestaurant",
      "externalRestaurantRef":"East 25th Street",
      "modifiedDate": 1544022583582,
      "createdDate": 1544022583582,
      "isoModifiedDate": "2018-12-05T15:09:43.582Z",
      "isoCreatedDate": "2018-12-05T15:09:43.582Z"
   },
   {
      "restaurantGuid":"00034778-423c-a426-0008-02561ac81ce6",
      "managementGroupGuid":null,
      "restaurantName":"The Better Restaurant",
      "locationName":null,
      "createdByEmailAddress":"werner@betterrestaurant.com",
      "externalGroupRef": null,
      "externalRestaurantRef": null,
      "modifiedDate": 1544136793429,
      "createdDate": 1544136793429,
      "isoModifiedDate": "2018-12-06T22:53:13.429Z",
      "isoCreatedDate": "2018-12-06T22:53:13.429Z"
   },
   {
      "restaurantGuid":"00013478-1ce6-a426-0008-02561ac81ce6",
      "managementGroupGuid":"88f3cca5-39d9-4acc-8627-3116c748f344",
      "restaurantName":"The Best Restaurant",
      "locationName":null,
      "createdByEmailAddress":"berthoud@bestrestaurant.com",
      "externalGroupRef":"BEST_RESTAURANT",
      "externalRestaurantRef":"Sheffield_008",
      "modifiedDate": 1544626611217,
      "createdDate": 1544626611217,
      "isoModifiedDate": "2018-12-12T14:56:51.217Z",
      "isoCreatedDate": "2018-12-12T14:56:51.217Z"
   }
]
```

  
#### How to make a request to /connectedRestaurants

Send a `GET` request to the `/connectedRestaurants` endpoint of the Toast partners API.


```
https://`{toast-api-hostname}`/partners/v1/connectedRestaurants
```



> **Note**
> 
> The `/connectedRestaurants` endpoint uses the same rate limiting functionality as other Toast API endpoints. For more information, see [Rate limiting](apiDevGuide-apiRateLimiting).


**Procedure 1.2. To get information about the restaurants you are connected to**

1. Authenticate with the Toast user management service using a partner API account. For more information, see [Authentication and restaurant access](apiDevGuide-authentication).


2. Send a `GET` request to the `/connectedRestaurants` endpoint of the partners API.

Optionally, include the `lastModified` parameter to limit the response data to connections created or modified after a specific date and time. The date and time must be a UTC timestamp in ISO 8601 format, for example: `2020-03-01T00:00:00.000-0000`.


3. Review the information about each restaurant that you have access to in the JSON data that the `/connectedRestaurants` endpoint returns.



#### Query parameters

You can query your response by adding the following parameters:

- `page`: The specific page of the results. The response includes the `lastPageNum` field. Use this value to know how many pages there are total in the response for a more accurate `page` query.


- `pageSize`: The amount of records in the total response. 100 is is the `pageSize` default. You can use the `totalResultCount` value in the response to create a more accurate query but knowing how many results there are in total.



#### Information in the /connectedRestaurants response data

For each restaurant, the `/connectedRestaurants` JSON response data contains the same values seen from the [`/restaurants`response data](apiDevGuide-apiPartnersGettingAccessibleRestaurants#apiGetRestaurantsReturnFieldList), as well as the following values:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`currentPageNum`</td>
      <td>The active page number from the return response.</td>
    </tr>
    <tr>
      <td>`totalResultCount`</td>
      <td>The total number of results in the response. This number matches `totalCount`.</td>
    </tr>
    <tr>
      <td>`pageSize`</td>
      <td>The active page size used when viewing the response data. This can be modified using the `pageSize` query parameter.</td>
    </tr>
    <tr>
      <td>`currentPageToken`</td>
      <td>The token for the current page information snapshot. Refer to this if you need to return to this exact dataset.</td>
    </tr>
    <tr>
      <td>`nextPageToken`</td>
      <td>The token for the next page information snapshot. Refer to this if you need to return to the next page's exact dataset.</td>
    </tr>
    <tr>
      <td>`totalCount`</td>
      <td>The total number of results in the response. This number matches `totalResultCount`.</td>
    </tr>
    <tr>
      <td>`nextPageNum`</td>
      <td>The next available page in the response. `Null` if you have come to the end of available pages.</td>
    </tr>
    <tr>
      <td>`lastPageNumber`</td>
      <td>The last available page in the response.</td>
    </tr>
    <tr>
      <td>`previousPageNum`</td>
      <td>The page number for the previous page in the response. `Null` when you are on the first page of the response.</td>
    </tr>
  </tbody>
</table>

#### /connectedRestaurants example return data

The following example shows the return data from the `/connectedRestaurants` endpoint of the partners API.

**Example 1.2. Return data from the /connectedrestaurants endpoint**


```
{
    "currentPageNum": 1,
    "results": [
        {
            "restaurantGuid": "a1fa1689-3ba1-43c2-ba31-300f3d7abe2c",
            "managementGroupGuid": "1606c177-9a18-45fb-b022-446ec6a80431",
            "restaurantName": "Astro Doughnuts and Fried Chicken",
            "locationName": "1819 7th ST NW",
            "createdByEmailAddress": "email@toasttab.com",
            "externalGroupRef": null,
            "externalRestaurantRef": null,
            "modifiedDate": 1644263179752,
            "createdDate": 1636044303499,
            "isoModifiedDate": "2022-02-07T19:46:19.752Z",
            "isoCreatedDate": "2021-11-04T16:45:03.499Z"
        },
        {
            "restaurantGuid": "7c0b44f7-e5fe-4ab7-a036-59e541fa93a8",
            "managementGroupGuid": "2a541c86-5da4-401b-a2f0-182c1459ee45",
            "restaurantName": "Test's Cafe",
            "locationName": "Boston",
            "createdByEmailAddress": "email@toasttab.com",
            "externalGroupRef": null,
            "externalRestaurantRef": null,
            "modifiedDate": 1654788101013,
            "createdDate": 1636743654371,
            "isoModifiedDate": "2022-06-09T15:21:41.013Z",
            "isoCreatedDate": "2021-11-12T19:00:54.371Z"
        },
        {
            "restaurantGuid": "b1139b0d-6014-4c56-966a-262770a69cbf",
            "managementGroupGuid": "b3cc3a6c-45d7-4ce4-96da-9b8c1bf05fcb",
            "restaurantName": "Astro Doughnuts and Fried Chicken",
            "locationName": "Catering DC",
            "createdByEmailAddress": "email@toasttab.com",
            "externalGroupRef": null,
            "externalRestaurantRef": null,
            "modifiedDate": 1644263179792,
            "createdDate": 1636365873198,
            "isoModifiedDate": "2022-02-07T19:46:19.792Z",
            "isoCreatedDate": "2021-11-08T10:04:33.198Z"
        }
    ],
    "totalResultCount": 33,
    "pageSize": 100,
    "currentPageToken": "cD0xLHM6MTAw",
    "nextPageToken": "cD9yLHM6MTAw",
    "totalCount": 33,
    "nextPageNum": null,
    "lastPageNum": 1,
    "previousPageNum": null
}
    
```

  
## Using location and group identifiers

The **My Integrations** page contains optional free-text Group ID and Location ID fields, which you can use to map restaurants in your system to Toast's restaurants.

For example, if a restaurant location has a numeric account number in your system, they can add their account identifier to the Location ID field. If a restaurant group has an alphanumeric group identifier in your system, they can add their group identifier to the Group ID field.

![Group ID and Location ID fields for a restaurant location](https://doc.toasttab.com/doc/media/externalIDs.png)

Location ID and group ID values are available in the partners API in the `externalGroupRef` and `externalRestaurantRef`fields.


```
[
   {
      "restaurantGuid":"10c8b667-36cf-4048-8a1c-7e48390768d0",
      "managementGroupGuid":"23a5cb86-8913-4f8f-bdea-bb478c058fac",
      "restaurantName":"Toast Grill & Tap",
      "locationName":"MA",
      "createdByEmailAddress":"werner@toasttrattoria.com",
      "externalGroupRef": "123#",
      "externalRestaurantRef": "ABC",
      "modifiedDate": 1544136793429,
      "createdDate": 1544136793429,
      "isoModifiedDate": "2019-12-06T22:53:13.429Z",
      "isoCreatedDate": "2019-12-06T22:53:13.429Z"
   }
]
```

If you use a [partner API account](apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts), Toast support recommends that you include information in your onboarding documentation instructing users on how to fill out these fields.

Integrations that use [restaurant management group API accounts](apiDevGuide-authentication#apiAuthenticationReturnDataRestaurant) cannot use these fields.

