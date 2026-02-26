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
keywords: ["understanding", "check", "reporting", "data", "restaurantGuid", "orderNumber", "orderGuid", "checkNumber", "checkGuid", "orderOpenedDate"]
procedures: 0
codeExamples: 0
---

Check reporting data contains a constant set of values. These values appear for every check and are organized by active restaurant. Optionally, you can choose to include the restaurant name in the check reporting data. For more information, see [Retrieving the check reporting data](apiDevGuide-apiAnalyticsCheckReportingDataRetrieveData). For more information about inactive restaurant data, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the check reporting data can be limited by adding the GUIDs of restaurants to either include only or exclude only. For more information about choosing specific restaurants, see [Creating a request for check reporting data](apiDevGuide-apiAnalyticsCheckReportingDataCreateRequest).

The following table specifies the set of values returned in the check reporting data. The values are listed in the order that they appear.


<table>
  <thead>
    <tr>
      <th>Value name</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`restaurantGuid`</td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td>`orderNumber`</td>
      <td>The number of the order.</td>
    </tr>
    <tr>
      <td>`orderGuid`</td>
      <td>The unique identifier assigned to the order by the Toast platform.</td>
    </tr>
    <tr>
      <td>`checkNumber`</td>
      <td>The number of the check.</td>
    </tr>
    <tr>
      <td>`checkGuid`</td>
      <td>The unique identifier assigned to the check by the Toast platform.</td>
    </tr>
    <tr>
      <td>`orderOpenedDate`</td>
      <td>The business date for when the order is initially expected to be fulfilled. This date determines whether a check is within the requested time range or not.</td>
    </tr>
    <tr>
      <td>`checkPaidDateTime`</td>
      <td>The most recent date the check received payment.</td>
    </tr>
    <tr>
      <td>`checkModifiedDateTime`</td>
      <td>The most recent date that the check was modified.</td>
    </tr>
    <tr>
      <td>`checkStatus `</td>
      <td>The payment state of the check. The state can be one of the following values: <ul><li>`OPEN` : The check is open and unpaid.</li><li>`PAID` : The check is paid, but the payment is not finalized.</li><li>`CLOSED` : The check payment is finalized.</li></ul></td>
    </tr>
    <tr>
      <td>`checkVoidedStatus`</td>
      <td>Indicates whether the check was voided or not. A `true` value indicates the check was voided, while a `false` value indicates the check was not voided.</td>
    </tr>
    <tr>
      <td>`diningOption`</td>
      <td>The dining option for the check data.</td>
    </tr>
    <tr>
      <td>`revenueCenter`</td>
      <td>The revenue center for the check data.</td>
    </tr>
    <tr>
      <td>`serverName`</td>
      <td>The first and last name of the employee who created the order.</td>
    </tr>
    <tr>
      <td>`checkTotalAmount`</td>
      <td>The total amount of the check.</td>
    </tr>
    <tr>
      <td>`checkDiscountAmount`</td>
      <td>The total discounted amount of the check.</td>
    </tr>
    <tr>
      <td>`checkTaxAmount`</td>
      <td>The total tax amount of the check.</td>
    </tr>
    <tr>
      <td>`checkTipAmount`</td>
      <td>The total tip amount of the check.</td>
    </tr>
    <tr>
      <td>`checkGratuityAmount`</td>
      <td>The total gratuity amount of the check.</td>
    </tr>
    <tr>
      <td>`checkRefundAmount`</td>
      <td>The total refund amount of the check.</td>
    </tr>
    <tr>
      <td>`restaurantName`</td>
      <td>The restaurant’s name. This is included when you set the `fetchRestaurantNames` parameter to `true` in the `GET` request.</td>
    </tr>
  </tbody>
</table>

