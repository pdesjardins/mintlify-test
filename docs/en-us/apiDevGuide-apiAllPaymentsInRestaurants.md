---
title: "Getting all payments for a restaurant"
id: apiAllPaymentsInRestaurants
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting payment information"
previousSectionFile: apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Getting payment information"
nextSectionFile: apiDevGuide-apiPaymentntInformation.md
nextSectionTitle: "Getting information about a specific payment"
excerpt: "Send a GET request to..."
keywords: ["closeoutHour", "paidBusinessDate", "refundBusinessDate", "voidBusinessDate"]
procedures: 0
codeExamples: 2
---

Send a `GET` request to the `/payments` endpoint of the orders API to get a JSON array of the GUIDs of the payments processed in a business day at your restaurant. A business day's cutoff is defined by the restaurant's `closeoutHour`, which you can retrieve with the [restaurant API](apiDevGuide-apiRestaurantInformation).

Depending on the query parameter that you use, you can retrieve the following types of payments:

- The `paidBusinessDate` query parameter returns a list of the payments made during the business day. The payment method can be of any type, such as by cash, credit card, or gift card.


- The `refundBusinessDate` query parameter returns a list of the payments that were refunded during the business day. For details on refunded payments, see [Refunded payments](apiDevGuide-apiPaymentntInformation#apiRefundedPayments).


- The `voidBusinessDate` query parameter returns a list of the payments that were voided during the business day. For details on voided payments, see [Voided payments](apiDevGuide-apiPaymentntInformation#apiVoidedPayments).



The following example **curl** command sends a `GET` request to the `/payments`endpoint of the orders API.

**Example 3.1. Get all payments for a restaurant**


```
curl -X GET \ -H "Authorization: Bearer
      eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
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
      dWq4Yzwo007AMgxjH9d241Y-g" \ -H "Toast-Restaurant-External-ID:
      76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf" \
      https://`[toast-api-hostname]`/orders/v2/payments?paidBusinessDate=20200211
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e703C0BDE523-B62F-4A49-BD00-2E7817FF64CD" className="">(1)</a></div></td>
      <td className=""><div className="">Use the <code className="">Toast-Restaurant-External-ID</code> request parameter to specify the GUID of the restaurant for which payments will be returned.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e708C0BDE523-B62F-4A49-BD00-2E7817FF64CD" className="">(2)</a></div></td>
      <td className=""><div className="">Specify the business date for order payments in the <code className="">paidBusinessDate</code> query parameter. Alternatively, you could query for refunds with the <code className="">refundBusinessDate</code> query parameter or for voids with the <code className="">voidBusinessDate</code> query parameter.</div></td>
    </tr>
  
The following example shows the JSON response data for a GET request to the `/payments` endpoint.

**Example 3.2. Get all payments return data**


```
[
  "361d140a-aa0b-43ad-98d6-516c416555d9",
  "198790e9-ea0d-4eb1-9bed-fc6c3d71d71e",
  "249c4be9-2236-4636-a90a-3ad15fb1fc69"
]
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e724C0BDE523-B62F-4A49-BD00-2E7817FF64CD" className="">(1)</a></div></td>
      <td className=""><div className="">The <code className="">/payments</code> endpoint returns a JSON array of payment GUIDs. In this example, the query returns three payments.</div></td>
    </tr>
  
