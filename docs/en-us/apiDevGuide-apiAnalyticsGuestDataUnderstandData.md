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

Guest reporting data contains objects for each payment corresponding to the specified restaurants and payment dates. You can also choose to retrieve data for currently inactive restaurants. For more information, see [Viewing inactive restaurant data](apiDevGuide-apiAnalyticsInactiveRestaurantData).

The restaurants included in the guest reporting data can be limited using either the `restaurantIds` or `excludedRestaurantIds` value in the message body. You can include restaurant GUIDs for only one of these values. Any restaurants listed with the `restaurantIds` value are included in the guest reporting data, with any restaurants not listed excluded. Any restaurants listed with the `excludedRestaurantIds` value are excluded from the guest reporting data, with any restaurants not listed included. When both are left blank, all restaurants are included automatically.

The following table specifies the returned set of values in the guest reporting data. The values are listed in the order they appear.


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
      <td><code>restaurantName</code></td>
      <td>The restaurant’s name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationName</code></td>
      <td>The restaurant’s location name.</td>
    </tr>
    <tr>
      <td><code>restaurantLocationCode</code></td>
      <td>The restaurant’s location code.</td>
    </tr>
    <tr>
      <td><code>paymentDate</code></td>
      <td>The date when the payment was processed, in <code>YYYYMMDD</code> format.</td>
    </tr>
    <tr>
      <td><code>orderGuid</code></td>
      <td>The unique identifier assigned to the order by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>paymentGuid</code></td>
      <td>The unique identifier assigned to the payment by the Toast platform.</td>
    </tr>
    <tr>
      <td><code>cardFingerprint</code></td>
      <td>The unique identifier assigned to a guest's payment card by the Toast platform. <blockquote><strong>Note</strong> <code>cardFingerprint</code> data is only available for payments processed starting in August 2024. <code>cardFingerprint</code> data is not supported for older payments.</blockquote> </td>
    </tr>
  </tbody>
</table>
</div>

