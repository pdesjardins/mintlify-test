---
title: "Getting cash deposit entries"
id: apiGetCashDeposits
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingCashManagementInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting cash management information"
previousSectionFile: apiDevGuide-apiUsingCashManagementApi.md
previousSectionTitle: "Getting cash entries"
nextSectionFile: apiDevGuide-apiCalculatingExpectedCashDeposits.md
nextSectionTitle: "Calculating expected cash deposits"
excerpt: "The deposits endpoint of the cash management API returns information about the actual cash deposits for a restaurant. For example, when you close out a business day for your restaurant, you might..."
keywords: ["getting", "cash", "deposit", "entries", "yyyyMMdd", "DepositEntry"]
procedures: 0
codeExamples: 2
---

The `deposits` endpoint of the cash management API returns information about the actual cash deposits for a restaurant. For example, when you close out a business day for your restaurant, you might package any cash that is greater than the amount needed for the start of the next day and deposit it in a bank. You record the deposit amount using the deposits function of the Toast POS.

**Example 8.3. Get all cash deposits made on a specific business date**


```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
https://`[toast-api-hostname]`/cashmgmt/v1/deposits?businessDate=20190918
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e340BCBEC7F8-786B-4966-9AA6-0D290AA55A72" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">Toast-Restaurant-External-ID</code> request parameter to specify the GUID of the restaurant from which to retrieve cash deposits. The GUID must be for an individual restaurant, not the GUID for a restaurant group or management group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e345BCBEC7F8-786B-4966-9AA6-0D290AA55A72" className="">(2)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">businessDate</code> request parameter to specify the date (in <code className="font-mono text-sm">yyyyMMdd</code> format) on which the cash deposits were created.</p></div></td>
    </tr>
  
The following example shows a `DepositEntry` object in the response data from the `deposits` endpoint.

**Example 8.4. DepositEntry object in deposits endpoint response data**


```
[
  {
    "guid": "8421034f-fa0b-495c-808e-bf98f63f0de7",
    "entityType": "DepositEntry",
    "date": "2019-09-18T14:49:41.284+0000",
    "amount": 3210.98,
    "employee": {
      "guid": "9659c962-7a8a-43ec-9343-47cafb68e83b",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "undoes": null
  }
]
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e436A964BCF4-D54B-4D7D-8984-EE06A9BC0B09" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of this <code className="font-mono text-sm">DepositEntry</code> object.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e438A964BCF4-D54B-4D7D-8984-EE06A9BC0B09" className="">(2)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the cash deposit was made.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e440A964BCF4-D54B-4D7D-8984-EE06A9BC0B09" className="">(3)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the deposit. The <code className="font-mono text-sm">amount</code> value must be greater than zero.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e442A964BCF4-D54B-4D7D-8984-EE06A9BC0B09" className="">(4)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID or external identifier of the restaurant employee who created the cash deposit.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e444A964BCF4-D54B-4D7D-8984-EE06A9BC0B09" className="">(5)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the deposit entry that was undone. The value is <code className="font-mono text-sm">null</code> if this deposit entry does not undo a previous deposit entry.</p></div></td>
    </tr>
  
