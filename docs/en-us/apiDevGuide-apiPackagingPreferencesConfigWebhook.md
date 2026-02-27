---
title: "Packaging preferences configuration webhook"
id: apiPackagingPreferencesConfigWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-devOrdersWebhookRef.md
previousSectionTitle: "Orders webhook"
nextSectionFile: apiDevGuide-apiPartnersWebhook.md
nextSectionTitle: "Partners webhook"
externalReferences: [https://central.toasttab.com/s/article/Configure-Packaging-Preferences-for-Takeout-and-Delivery]
excerpt: "The..."
keywords: ["packaging_updated", "eventCategory", "eventType"]
procedures: 0
codeExamples: 0
---

The packaging preferences configuration webhook sends you a message when a restaurant updates its packaging preferences in Toast Web. The message payload includes: 

- The GUID of the restaurant changing its packaging preferences.


- The time stamp of the change.


- Details of what was changed.



 For information on how a restaurant can configure packaging preferences, see this [Toast Central article](https://central.toasttab.com/s/article/Configure-Packaging-Preferences-for-Takeout-and-Delivery).

When a restaurant sets their packaging preferences, and you receive the `packaging_updated` webhook message with the updates, you can submit orders using the [orders API](apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesUsingTheOrdersApi) with packaging preferences.

Packaging preferences configuration webhook messages follow the [standard message data schema](apiDevGuide-apiMessageDataSchema). When a message is published to your webhook endpoint for the `packaging` event category, the `eventCategory` value is set to `partner` and the `eventType` is set to `packaging_updated`.

## packaging_updated

A restaurant using your integration has updated its packaging preferences configuration in Toast Web.

The packaging preferences configuration webhook `eventType` is `packaging_updated`. The webhook payload is similar to the packaging preferences response data from the [packagingConfig endpoint](apiDevGuide-apiOrdersPackagingPreferences).

Attributes in the `packaging_updated` event's payload include:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Value</th>
      <th className="">Description</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><code className="">packagingConfig</code></td>
      <td className="">The parent object that holds the following information about the specific packaging preference configurations. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">enabled</code></td>
      <td className="">Indicates whether the restaurant is currently using packaging preferences in this object. If <code className="">TRUE</code>, you display the packaging options to guests in your ordering interface. If <code className="">FALSE</code>, do not display the options.  <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">items</code></td>
      <td className="">The list of available packaging items. The <code className="">items</code> array contains the following fields and values:<ul className=""><li className=""><code className="">id</code>: The unique identifier for a packaging item. The id is required to apply packaging preferences when you submit an order using the <a href="apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesUsingTheOrdersApi" className="">orders API</a>.</li><li className=""><code className="">itemTypes</code>: The packaging categories an item can belong to, such as napkins or condiments. One packaging item may qualify as several different <code className="">itemTypes</code>. For example, an item named "to-go items” that has <code className="">itemTypes</code> of napkins and utensils.</li><li className=""><code className="">guestDisplayName</code>: An alternative name the restaurant team can configure for a packaging item. For example, you may select <code className="">itemTypes</code> for <code className="">CONDIMENTS</code> but have your guests see the following message: “Ketchup and mustard.”</li><li className=""><code className="">guestInclusionType</code>: Defines how the restaurant guest should interact with the packaging preference. The available values are: <ul className=""><li className=""><code className="">OPT_IN</code>: A guest must complete an action to include packaging preferences, such as selecting a checkbox.</li><li className=""><code className="">OPT_OUT</code>: A guest must complete an action to opt out of packaging, such as de-selecting a checkbox.</li></ul></li><li className=""><code className="">guestDescription</code>: Further describes the packaging item, in addition to the <code className="">guestDisplayName</code>. For example, if the <code className="">itemType</code> is <code className="">CONDIMENTS</code>, and the <code className="">guestDisplayName</code> is "Ketchup and mustard", the <code className="">guestDescription</code> could show "Includes ketchup and mustard only."</li></ul> <br/> data type: string </td>
    </tr>
    <tr className="">
      <td className=""><code className="">guestMessage</code></td>
      <td className="">An optional message configured by the restaurant that you show to guests on your ordering interface. <br/> data type: string</td>
    </tr>
  </tbody>
</table>
</div>

**Example 9.4. Payload example for the menus_updated event**


```
{
 "timestamp": "2024-12-10T17:47:36.044Z",
 "eventCategory": "packaging",
 "eventType": "packaging_updated",
 "guid": "ae839da8-a506-498e-afb8-ff7d7dbd7231",
 "details": {
   "packagingConfig": {
     "enabled": true,
     "items": [
       {
         "id": "ccdbcbf8-5c5b-4158-ae61-3a6da8bc847d",
         "itemTypes": [
           "CONDIMENTS",
         ],

         "guestDisplayName": "Ketchup and mustard",
         "guestInclusionType": "OPT_IN",
         "guestDescription": "Includes ketchup and mustard only."
       }
     ],

     "guestMessage": "Choose your packaging preferences to complete your order. "
   }
 }
}

```

  
