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


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>Value name</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>restaurantGuid</code></td>
      <td>The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>orderNumber</code></td>
      <td>The number of the order.</td>
    </tr>
    <tr>
      <td><code>orderGuid</code></td>
      <td>The unique identifier assigned to the order by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>checkNumber</code></td>
      <td>The number of the check.</td>
    </tr>
    <tr>
      <td><code>checkGuid</code></td>
      <td>The unique identifier assigned to the check by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>orderOpenedDate</code></td>
      <td>The business date for when the order is initially expected to be fulfilled. This date determines whether a check is within the requested time range or not.</td>
    </tr>
    <tr>
      <td><code>checkPaidDateTime</code></td>
      <td>The most recent date the check received payment.</td>
    </tr>
    <tr>
      <td><code>checkModifiedDateTime</code></td>
      <td>The most recent date that the check was modified.</td>
    </tr>
    <tr>
      <td><code>checkStatus </code></td>
      <td>The payment state of the check. The state can be one of the following values: <ul><li><code>OPEN</code> : The check is open and unpaid.</li><li><code>PAID</code> : The check is paid, but the payment is not finalized.</li><li><code>CLOSED</code> : The check payment is finalized.</li></ul></td>
    </tr>
    <tr>
      <td><code>checkVoidedStatus</code></td>
      <td>Indicates whether the check was voided or not. A <code>true</code> value indicates the check was voided, while a <code>false</code> value indicates the check was not voided.</td>
    </tr>
    <tr>
      <td><code>diningOption</code></td>
      <td>The dining option for the check data.</td>
    </tr>
    <tr>
      <td><code>revenueCenter</code></td>
      <td>The revenue center for the check data.</td>
    </tr>
    <tr>
      <td><code>serverName</code></td>
      <td>The first and last name of the employee who created the order.</td>
    </tr>
    <tr>
      <td><code>checkTotalAmount</code></td>
      <td>The total amount of the check.</td>
    </tr>
    <tr>
      <td><code>checkDiscountAmount</code></td>
      <td>The total discounted amount of the check.</td>
    </tr>
    <tr>
      <td><code>checkTaxAmount</code></td>
      <td>The total tax amount of the check.</td>
    </tr>
    <tr>
      <td><code>checkTipAmount</code></td>
      <td>The total tip amount of the check.</td>
    </tr>
    <tr>
      <td><code>checkGratuityAmount</code></td>
      <td>The total gratuity amount of the check.</td>
    </tr>
    <tr>
      <td><code>checkRefundAmount</code></td>
      <td>The total refund amount of the check.</td>
    </tr>
    <tr>
      <td><code>restaurantName</code></td>
      <td>The restaurant’s name. This is included when you set the <code>fetchRestaurantNames</code> parameter to <code>true</code> in the <code>GET</code> request.</td>
    </tr>
  </tbody>
</table>
</div>

