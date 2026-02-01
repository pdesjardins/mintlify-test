---
title: "Understanding the check reporting data"
id: apiAnalyticsCheckReportingDataUnderstandingData
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataOmitChunkFromSearchIndex.md
parentSectionTitle: "Check reporting data"
previousSectionFile: apiDevGuide-apiAnalyticsCheckReportingDataRetrieveData.md
previousSectionTitle: "Retrieving the check reporting data"
nextSectionFile: apiDevGuide-apiAnalyticsLaborReportingDataOmitChunkFromSearchIndex.md
nextSectionTitle: "Labor reporting data"
excerpt: "Check reporting data contains a constant set of values. These values appear for every..."
keywords: [understanding,check,reporting,data,restaurantGuid,orderNumber,orderGuid,checkNumber,checkGuid,orderOpenedDate]
procedures: 0
codeExamples: 0
---

### Understanding the check reporting data

Check reporting data contains a constant set of values. These values appear for every check and are organized by active restaurant. Optionally, you can choose to include the restaurant name in the check reporting data. For more information, see [Retrieving the check reporting data](apiAnalyticsCheckReportingDataRetrieveData.html). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiAnalyticsInactiveRestaurantData.html).

The restaurants included in the check reporting data can be limited by adding the GUIDs of restaurants to either include only or exclude only. For more information about choosing specific restaurants, see [Creating a request for check reporting data](apiAnalyticsCheckReportingDataCreateRequest.html).

The following table specifies the set of values returned in the check reporting data. The values are listed in the order that they appear.

| Value name | Definition | 
| --- | --- |
| `restaurantGuid` | The unique identifier assigned to the restaurant by the Toast platform. | 
| `orderNumber` | The number of the order. | 
| `orderGuid` | The unique identifier assigned to the order by the Toast platform. | 
| `checkNumber` | The number of the check. | 
| `checkGuid` | The unique identifier assigned to the check by the Toast platform. | 
| `orderOpenedDate` | The business date for when the order is initially expected to be fulfilled. This date determines whether a check is within the requested time range or not. | 
| `checkPaidDateTime` | The most recent date the check received payment. | 
| `checkModifiedDateTime` | The most recent date that the check was modified. | 
| `checkStatus ` | The payment state of the check. The state can be one of the following values: - `OPEN` : The check is open and unpaid.
- `PAID` : The check is paid, but the payment is not finalized.
- `CLOSED` : The check payment is finalized.

 | 
| `checkVoidedStatus` | Indicates whether the check was voided or not. A `true` value indicates the check was voided, while a `false` value indicates the check was not voided. | 
| `diningOption` | The dining option for the check data. | 
| `revenueCenter` | The revenue center for the check data. | 
| `serverName` | The first and last name of the employee who created the order. | 
| `checkTotalAmount` | The total amount of the check. | 
| `checkDiscountAmount` | The total discounted amount of the check. | 
| `checkTaxAmount` | The total tax amount of the check. | 
| `checkTipAmount` | The total tip amount of the check. | 
| `checkGratuityAmount` | The total gratuity amount of the check. | 
| `checkRefundAmount` | The total refund amount of the check. | 
| `restaurantName` | The restaurant’s name. This is included when you set the `fetchRestaurantNames` parameter to `true` in the `GET`request. | 

