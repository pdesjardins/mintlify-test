---
title: "Partners webhook"
id: apiPartnersWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiPackagingPreferencesConfigWebhook.md
previousSectionTitle: "Packaging preferences configuration webhook"
nextSectionFile: apiDevGuide-apiRxAvailabilityWebhook.md
nextSectionTitle: "Restaurant availability webhook"
externalReferences: [https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast]
excerpt: "The partners webhook allows you to receive updates when:"
keywords: ["externalGroupRef", "externalRestaurantRef", "eventCategory", "eventType"]
procedures: 0
codeExamples: 0
---

The `partners` webhook allows you to receive updates when:

- Your integration is added to a restaurant location.


- Your integration is removed from a restaurant location.


- Your integration's settings in the Toast POS system are updated, for example, when the `externalGroupRef` or `externalRestaurantRef` property is updated.



Partners webhook messages follow the [standard message data schema](apiDevGuide-apiMessageDataSchema). When a message is published to your webhook endpoint for the `partner`event category, the `eventCategory` value is set to `partner` and the `eventType` is set to one of the following:

- [partner_added](apiDevGuide-apiPartnersWebhook#apiPartnerAdded)


- [partner_removed](apiDevGuide-apiPartnersWebhook#apiPartnerDeleted)


- [partner_updated](apiDevGuide-apiPartnersWebhook#apiPartnerUpdated)



The updates published through the `partner` event category are in addition to the emails you currently receive when your integration is added to or removed from a restaurant location. For more information about how to trigger a webhook event in the `partner` category, see [this Toast Central article](https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast).

## partner_added

Your integration has been added to a new restaurant location.

Attributes in the `partner_added` event's payload include:


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
      <td className=""><code className="">restaurantGuid</code></td>
      <td className="">A unique Toast POS identifier for the restaurant. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr className="">
      <td className=""><code className="">managementGroupGuid</code></td>
      <td className="">A unique Toast POS identifier for a group of restaurants. The management group GUID will be the same for all restaurants within the same group. The management group GUID will be null if a restaurant location does not belong to a restaurant management group. <br/> May be null. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantName</code></td>
      <td className="">The human-readable name of the restaurant, set on the Restaurant Info screen of Toast Web. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">locationName</code></td>
      <td className="">The name of a specific restaurant location, set on the Restaurant Info screen of Toast Web. For example, a restaurant group might assign a location name such as <code className="">Palo Alto</code> or <code className="">Boston</code> to identify a specific location. Note that this field is not required by the Toast platform, so it may be empty. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">externalGroupRef</code></td>
      <td className="">An identifier for the restaurant group that is recognized by the the partner that made the request to the <code className="">/restaurants</code> endpoint. This information is entered by the restaurant administrator. If you need information about the restaurant group in this data string, you instruct the restaurant administrator to enter it in the Toast POS system configuration for the integration partner connection. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">externalRestaurantRef</code></td>
      <td className="">An identifier for the restaurant location that is recognized by the partner that made the request to the <code className="">/restaurants</code> endpoint. This information is entered by the restaurant administrator. If you need information about the restaurant location in this data string, you instruct the restaurant administrator to enter it in the Toast POS system configuration for the integration partner connection. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">modifiedDate</code></td>
      <td className="">The most recent date and time that the partner connection was edited. The date and time are expressed in milliseconds from the UNIX epoch, January 1, 1970 00:00:00 UTC. <br/> data type: string <br/> format: date-time</td>
    </tr>
    <tr className="">
      <td className=""><code className="">createdDate</code></td>
      <td className="">The date and time that the partner connection was created. The date and time are expressed in milliseconds from the UNIX epoch, January 1, 1970 00:00:00 UTC. <br/> data type: string <br/> format: date-time</td>
    </tr>
    <tr className="">
      <td className=""><code className="">isoModifiedDate</code></td>
      <td className="">The most recent date and time that the partner connection was edited. The date and time are expressed in ISO 8601 format. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">isoCreatedDate</code></td>
      <td className="">The date and time that the partner connection was created. The date and time are expressed in ISO 8601 format. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">createdByFirstName</code></td>
      <td className="">The first name of the restaurant employee who added the integration to the restaurant location. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">createdByLastName</code></td>
      <td className="">The last name of the restaurant employee who added the integration to the restaurant location. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">createdByEmailAddress</code></td>
      <td className="">The email address of the restaurant employee who added the integration. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">createdByPhoneNumber</code></td>
      <td className="">The phone number of the restaurant employee who added the integration. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantPhoneNumber</code></td>
      <td className="">The phone number of the restaurant location. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantAddressLine1</code></td>
      <td className="">The first line of the restaurant's address. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantAddressLine2</code></td>
      <td className="">The second line of the restaurant's address. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantCity</code></td>
      <td className="">The city the restaurant location resides in. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantState</code></td>
      <td className="">The state the restaurant location resides in. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantZipCode</code></td>
      <td className="">The zip code for the restaurant location. <br/> May be null. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantCountryCode</code></td>
      <td className="">The ISO 3166-2 country code for the restaurant location. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantTimezone</code></td>
      <td className="">The IANA time zone identifier of the restaurant location. For example, <code className="">America/New_York</code>. <br/> data type: string</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLatitude</code></td>
      <td className="">The north/south geographic coordinate of the restaurant, in decimal degrees. <br/> May be null. <br/> data type: number</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurantLongtitude</code></td>
      <td className="">The east/west geographic coordinate of the restaurant, in decimal degrees. <br/> May be null. <br/> data type: number</td>
    </tr>
  </tbody>
</table>
</div>

**Example 9.5. Payload example for the partner_added event**


```
{
    "timestamp": “2019-09-16T21:01:53.685Z”,
    "eventCategory": "partner",
    "eventType": "partner_added",
    "guid": "00000000-0000-0000-0000-000000000000",
    "details": {
        "restaurantGuid": "00000000-1111-2222-3333-444444444444",
        "managementGroupGuid": "55555555-6666-7777-8888-999999999999",
        "restaurantName": "Toast Grill & Tap",
        "locationName": "Fenway, Boston, MA",
        "externalGroupRef": null,
        "externalRestaurantRef": null,
        "modifiedDate": 1568667880240,
        "createdDate": 1568667880240,
        "isoModifiedDate": “2019-09-16T21:01:53.685Z”,
        "isoCreatedDate": “2019-09-16T21:01:53.685Z”,
        "createdByFirstName": "Toast",
        "createdByLastName": "Admin",
        "createdByEmailAddress": "admin@toasttab.com",
        "createdByPhoneNumber": null,
        "restaurantPhoneNumber": "6175551234",
        "restaurantAddressLine1": "401 Park Drive",
        "restaurantAddressLine2": null,
        "restaurantCity": "Boston",
        "restaurantState": "MA",
        "restaurantZipCode": "02215",
        "restaurantCountryCode": "US",
        "restaurantTimezone": "America/New_York",
        "restaurantLatitude": "42.344257",
        "restaurantLongitude": "-71.102181"
    }
}
```

  
## partner_removed

Your integration has been removed from a new restaurant location.

The payload for the `partner_removed` webhook event is identical to the payload for the `partner_added` event. See [partner_added](apiDevGuide-apiPartnersWebhook#apiPartnerAdded) for details.

**Example 9.6. Payload example for the partner_removed event**


```
{
    "timestamp": “2019-09-16T21:22:12.825Z”,
    "eventCategory": "partner",
    "eventType": "partner_removed",
    "guid": "00000000-0000-0000-0000-000000000000",
    "details": {
        "restaurantGuid": "00000000-1111-2222-3333-444444444444",
        "managementGroupGuid": "55555555-6666-7777-8888-999999999999",
        "restaurantName": "Toast Grill & Tap",
        "locationName": "Fenway, Boston, MA",
        "externalGroupRef": null,
        "externalRestaurantRef": null,
        "modifiedDate": 1568667880240,
        "createdDate": 1568667880240,
        "isoModifiedDate": “2019-09-16T21:01:53.685Z”,
        "isoCreatedDate": “2019-09-16T21:01:53.685Z”,
        "createdByFirstName": "Toast",
        "createdByLastName": "Admin",
        "createdByEmailAddress": "admin@toasttab.com",
        "createdByPhoneNumber": null,
        "restaurantPhoneNumber": "6175551234",
        "restaurantAddressLine1": "401 Park Drive",
        "restaurantAddressLine2": null,
        "restaurantCity": "Boston",
        "restaurantState": "MA",
        "restaurantZipCode": "02215",
        "restaurantCountryCode": "US",
        "restaurantTimezone": "America/New_York",
        "restaurantLatitude": "42.344257",
        "restaurantLongitude": "-71.102181"
    }
}
```

  
## partner_updated

Settings have been updated for your integration, for example, the `externalGroupRef` or `externalRestaurantRef`configuration has been updated.

The payload for the `partner_updated` webhook event is identical to the payload for the `partner_added` event. See [partner_added](apiDevGuide-apiPartnersWebhook#apiPartnerAdded) for details.

**Example 9.7. Payload example for the partner_updated event**


```
{
    "timestamp": “2019-09-16T21:14:02.142Z”,
    "eventCategory": "partner",
    "eventType": "partner_updated",
    "guid": "00000000-0000-0000-0000-000000000000",
    "details": {
        "restaurantGuid": "00000000-1111-2222-3333-444444444444",
        "managementGroupGuid": "55555555-6666-7777-8888-999999999999",
        "restaurantName": "Toast Grill & Tap",
        "locationName": "Fenway, Boston, MA",
        "externalGroupRef": "toastgrill",
        "externalRestaurantRef": "boston01",
        "modifiedDate": 1568667977351,
        "createdDate": 1568667880240,
        "isoModifiedDate": "2019-09-16T21:14:02.142Z",
        "isoCreatedDate": "2019-09-16T21:01:53.685Z",
        "createdByFirstName": "Toast",
        "createdByLastName": "Admin",
        "createdByEmailAddress": "admin@toasttab.com",
        "createdByPhoneNumber": null,
        "restaurantPhoneNumber": "6175551234",
        "restaurantAddressLine1": "401 Park Drive",
        "restaurantAddressLine2": null,
        "restaurantCity": "Boston",
        "restaurantState": "MA",
        "restaurantZipCode": "02215",
        "restaurantCountryCode": "US",
        "restaurantTimezone": "America/New_York",
        "restaurantLatitude": "42.344257",
        "restaurantLongitude": "-71.102181"
    }
}
```



    <tr className="">
      <td className=""><a href="#co-d1e1581578677079" className="">(1)</a></td>
      <td className="">The <code className="">externalGroupRef</code> field has been updated.</td>
    </tr>
    <tr className="">
      <td className=""><a href="#co-d1e1601578677079" className="">(2)</a></td>
      <td className="">The <code className="">externalRestaurantRef</code> field has been updated.</td>
    </tr>
  
