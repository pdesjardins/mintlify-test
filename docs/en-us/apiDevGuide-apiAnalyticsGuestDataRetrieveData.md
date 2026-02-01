---
title: "Retrieving the guest reporting data"
id: apiAnalyticsGuestDataRetrieveData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataCreateRequest.md
previousSectionTitle: "Creating a request for guest reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsGuestDataUnderstandData.md
nextSectionTitle: "Understanding the guest reporting data"
excerpt: "Send a GET..."
keywords: ["retrieving", "guest", "reporting", "data", "/era/v1/guest/payments/{reportRequestGuid}", "reportRequestGuid"]
procedures: 0
codeExamples: 0
---

### Retrieving the guest reporting data

Send a `GET` request to the `/era/v1/guest/payments/\{reportRequestGuid\}` endpoint to retrieve guest reporting data. The rate limit for this endpoint and method type is five requests per second and 30 requests per minute. For more information about API rate limits for the analytics API, see [Analytics API rate limits](apiAnalyticsRateLimiting.html).

To request the guest reporting data, you must include the guest reporting data request GUID, or `reportRequestGuid`, as a path parameter.

#### Request to retrieve guest reporting data

The following **curl** command sends a `GET` request to the `/era/v1/guest/payments/\{reportRequestGuid\}`endpoint.

```
curl -X GET \ 'https://[toast-api-hostname]/era/v1/guest/payments/
fb23cfaa-56d7-4cb9-829d-531a8d02274a/' \
  -H 'Authorization: Bearer [token]'
```



(1) Send a GET request to the /era/v1/guest/payments endpoint of the analytics API.

(2) Include the reportRequestGuid. For more information about how to retrieve data using the analytics API, see Understanding the analytics API process.

(3) Include an authentication token. For more information, see Authentication and restaurant access.

#### Response to the retrieval request for guest reporting data

The following example shows the response from the `/era/v1/guest/payments/\{reportRequestGuid\}`endpoint.

```
[
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240924",
        "orderGuid": "f949eefc-06e4-4ff0-9bde-7e85b732fb36",
        "paymentGuid": "5a3dd0fd-48e0-4f32-8dc4-500784498477",
        "cardFingerprint": "22030f99-0bd1-4766-9bd4-9dd33576684f"
    },
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240924",
        "orderGuid": "27e00ac6-14ce-4a7c-baf2-93ee8ae54535",
        "paymentGuid": "95a97b2d-31a2-46a3-8592-5fb5fb74cf13",
        "cardFingerprint": "5391bff6-f5fa-4f0b-9df6-6125f1254737"
    },
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240924",
        "orderGuid": "07a64cf7-4c72-4f91-84ac-06c3659fd983",
        "paymentGuid": "2659d1bb-3265-41f5-8c59-7f51859fff9f",
        "cardFingerprint": "88ec15f8-4b4a-4071-925a-340ce5e313b1"
    },
    [content omitted]
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240926",
        "orderGuid": "eb0d9e22-a232-4e02-aea6-36f229c31c87",
        "paymentGuid": "95dba2a7-caa9-437d-81c7-e04c9b770241",
        "cardFingerprint": "d180c71f-a80d-4030-914d-f11a42664223"
    },
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240925",
        "orderGuid": "2df74a8d-6ce8-4e72-a672-c529ffbc00e1",
        "paymentGuid": "3641122d-9d3e-4f2e-b081-e5ce472546e9",
        "cardFingerprint": "35962871-10ae-4b98-89a9-f81a049552fd"
    },
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240925",
        "orderGuid": "d5fbb6dd-bdbe-4bed-bc21-d878bf695fe5",
        "paymentGuid": "ae9e449c-3998-40fc-834a-11b8d8a99830",
        "cardFingerprint": "22030f99-0bd1-4766-9bd4-9dd33576684f"
    },
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240924",
        "orderGuid": "b6865f15-5909-4d56-a3fc-66ae08cc22aa",
        "paymentGuid": "a4be40b5-7747-427f-9e78-b50802660cff",
        "cardFingerprint": "a85ae337-8c00-41a6-bd79-0efec7870575"
    },
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240924",
        "orderGuid": "561e2aae-a668-40cd-ae69-936428a58a8e",
        "paymentGuid": "42250a18-a5a2-4079-a7a9-1aa57fd045e0",
        "cardFingerprint": "ea918c06-f999-4c30-99c6-486fad5f9918"
    },
    [content omitted]
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240925",
        "orderGuid": "3b5d6ee5-a94f-440f-863c-150d7e0a72c3",
        "paymentGuid": "a4049a1b-59e0-46af-bac5-f9d971dfc094",
        "cardFingerprint": "e6e7b568-0375-47ff-a380-fd1f44101a4e"
    },
    \{
        "restaurantGuid": "95a96d7b-dbf5-46d3-98c5-c65c8ad18021",
        "restaurantName": "Grove Place Cafe",
        "restaurantLocationName": "Richmond",
        "restaurantLocationCode": "1737",
        "paymentDate": "20240926",
        "orderGuid": "66774f2e-2a63-4576-bda9-1714f96ca92f",
        "paymentGuid": "0bf2b932-d849-4229-ab5f-7857c612dc38",
        "cardFingerprint": "e6e7b568-0375-47ff-a380-fd1f44101a4e"
    },
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240924",
        "orderGuid": "fbea2cd5-2e4f-42b4-9d29-1b534ff99a7c",
        "paymentGuid": "1cef78b9-51da-48c6-b03a-3a34f0728742",
        "cardFingerprint": "b46dca14-e213-4c04-9c88-8ecf09d1ca04"
    },
    \{
        "restaurantGuid": "6b853fa7-b3dc-4db7-a528-c3599823ccd1",
        "restaurantName": "Summer Street Cafe",
        "restaurantLocationName": "Boston",
        "restaurantLocationCode": "1630",
        "paymentDate": "20240925",
        "orderGuid": "a773d61d-d0c7-4d98-94ad-100a5e6be980",
        "paymentGuid": "5e1f17d7-21df-43fa-8af6-81a2f36828a5",
        "cardFingerprint": "22030f99-0bd1-4766-9bd4-9dd33576684f"
    \}
    [content omitted]
]
```

For more information about the values in the response, see [Understanding the guest reporting data](apiAnalyticsGuestDataUnderstandData.html).

