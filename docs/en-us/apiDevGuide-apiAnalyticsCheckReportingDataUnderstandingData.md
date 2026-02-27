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
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Value name</th>
      <th className="">Definition</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><code className="">restaurantGuid</code></td>
      <td className="">The unique identifier assigned to the restaurant by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orderNumber</code></td>
      <td className="">The number of the order.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orderGuid</code></td>
      <td className="">The unique identifier assigned to the order by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkNumber</code></td>
      <td className="">The number of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkGuid</code></td>
      <td className="">The unique identifier assigned to the check by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orderOpenedDate</code></td>
      <td className="">The business date for when the order is initially expected to be fulfilled. This date determines whether a check is within the requested time range or not.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkPaidDateTime</code></td>
      <td className="">The most recent date the check received payment.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkModifiedDateTime</code></td>
      <td className="">The most recent date that the check was modified.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkStatus </code></td>
      <td className="">The payment state of the check. The state can be one of the following values: <ul className=""><li className=""><code className="">OPEN</code> : The check is open and unpaid.</li><li className=""><code className="">PAID</code> : The check is paid, but the payment is not finalized.</li><li className=""><code className="">CLOSED</code> : The check payment is finalized.</li></ul></td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkVoidedStatus</code></td>
      <td className="">Indicates whether the check was voided or not. A <code className="">true</code> value indicates the check was voided, while a <code className="">false</code> value indicates the check was not voided.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">diningOption</code></td>
      <td className="">The dining option for the check data.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">revenueCenter</code></td>
      <td className="">The revenue center for the check data.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">serverName</code></td>
      <td className="">The first and last name of the employee who created the order.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkTotalAmount</code></td>
      <td className="">The total amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkDiscountAmount</code></td>
      <td className="">The total discounted amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkTaxAmount</code></td>
      <td className="">The total tax amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkTipAmount</code></td>
      <td className="">The total tip amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkGratuityAmount</code></td>
      <td className="">The total gratuity amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">checkRefundAmount</code></td>
      <td className="">The total refund amount of the check.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantName</code></td>
      <td className="">The restaurant’s name. This is included when you set the <code className="">fetchRestaurantNames</code> parameter to <code className="">true</code> in the <code className="">GET</code> request.</td>
    </tr>
  </tbody>
</table>
</div>

