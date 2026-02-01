---
title: "Understanding the guest reporting data"
id: apiAnalyticsGuestDataUnderstandData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsGuestDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsGuestDataRetrieveData.md
previousSectionTitle: "Retrieving the guest reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsRestaurantInfoOmitChunkFromSearchIndex.md
nextSectionTitle: "Restaurant information"
excerpt: "Guest reporting data contains objects for each payment corresponding to the specified restaurants and payment dates. You can also choose to retrieve data for currently..."
keywords: ["understanding", "guest", "reporting", "data", "restaurantIds", "excludedRestaurantIds", "restaurantGuid", "restaurantName", "restaurantLocationName", "restaurantLocationCode"]
procedures: 0
codeExamples: 0
---

### Understanding the guest reporting data

Guest reporting data contains objects for each payment corresponding to the specified restaurants and payment dates. You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

The restaurants included in the guest reporting data can be limited using either the `restaurantIds` or `excludedRestaurantIds` value in the message body. You can include restaurant GUIDs for only one of these values. Any restaurants listed with the `restaurantIds` value are included in the guest reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the guest reporting data, with any restaurants not listed included. When both are left blank, all restaurants are included automatically.

The following table specifies the returned set of values in the guest reporting data. The values are listed in the order they appear.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the restaurant by the Toast platform. | 
| `restaurantName` | The restaurant’s name. | 
| `restaurantLocationName` | The restaurant’s location name. | 
| `restaurantLocationCode` | The restaurant’s location code. | 
| `paymentDate` | The date when the payment was processed, in `YYYYMMDD` format. | 
| `orderGuid` | The unique identifier assigned to the order by the Toast platform. | 
| `paymentGuid` | The unique identifier assigned to the payment by the Toast platform. | 
| `cardFingerprint` | The unique identifier assigned to a guest's payment card by the Toast platform.

> **Note**
> 
> `cardFingerprint` data is only available for payments processed starting in August 2024. `cardFingerprint` data is not supported for older payments.


 | 

