---
title: "Guest reporting data overview"
id: apiAnalyticsGuestDataOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
previousSectionTitle: "Guest reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsGuestDataCreateRequest.md
nextSectionTitle: "Creating a request for guest reporting data"
excerpt: "Guest reporting data includes payment details associated with a guest's payment card. For more information, see . For more information about inactive restaurant data, see ."
keywords: ["guest", "reporting", "data", "overview", "cardFingerprint", "/era/v1/guest/payments/{timeRange}", "reportRequestGuid", "/era/v1/guest/payments/{reportRequestGuid}"]
procedures: 0
codeExamples: 0
---

Guest reporting data includes payment details associated with a guest's payment card. For more information, see [Understanding the guest reporting data](docs/en-us/apiDevGuide-apiAnalyticsGuestDataUnderstandData). For more information about inactive restaurant data, see [Viewing inactive restaurant data](docs/en-us/apiDevGuide-apiAnalyticsInactiveRestaurantData).



> **Note**
> 
> `cardFingerprint` data is only available for payments processed starting in August 2024. `cardFingerprint` data is not supported for older payments.


Retrieving the guest reporting data is a two-step process. You must:

1. Send a `POST` request to the `/era/v1/guest/payments/{timeRange}` endpoint to create a request for guest reporting data organized by payment for the restaurants in a management group. The response is the `reportRequestGuid`, which is the unique request identifier. The analytics API supports retrieving guest reporting data for the `day` and `week` time ranges. For more information, see [Creating a request for guest reporting data](docs/en-us/apiDevGuide-apiAnalyticsGuestDataCreateRequest).


2. Send a `GET` request to the `/era/v1/guest/payments/{reportRequestGuid}` endpoint to retrieve the guest reporting data organized by payment. For more information, see [Retrieving the guest reporting data](docs/en-us/apiDevGuide-apiAnalyticsGuestDataRetrieveData).





> **Note**
> 
> The `reportRequestGuid` expires seven days after you create it. Using an expired or invalid `reportRequestGuid`results in a 404 error. The message of the response body contains additional information about the cause of the error.


