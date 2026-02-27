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
      <td className=""><code className="">restaurantName</code></td>
      <td className="">The restaurant’s name.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLocationName</code></td>
      <td className="">The restaurant’s location name.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLocationCode</code></td>
      <td className="">The restaurant’s location code.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">paymentDate</code></td>
      <td className="">The date when the payment was processed, in <code className="">YYYYMMDD</code> format.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orderGuid</code></td>
      <td className="">The unique identifier assigned to the order by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">paymentGuid</code></td>
      <td className="">The unique identifier assigned to the payment by the Toast platform.</td>
    </tr>
    <tr className="">
      <td className=""><code className="">cardFingerprint</code></td>
      <td className="">The unique identifier assigned to a guest's payment card by the Toast platform. <blockquote><strong>Note</strong> <code className="">cardFingerprint</code> data is only available for payments processed starting in August 2024. <code className="">cardFingerprint</code> data is not supported for older payments.</blockquote> </td>
    </tr>
  </tbody>
</table>
</div>

