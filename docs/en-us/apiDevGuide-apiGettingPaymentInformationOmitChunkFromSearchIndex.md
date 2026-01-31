---
title: "Getting payment information"
id: apiGettingPaymentInformationOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 3. Payments"
previousSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 3. Payments"
nextSectionFile: apiDevGuide-apiPaymentntInformation.md
nextSectionTitle: "Getting information about a specific payment"
keywords: [getting,payment,information]
procedures: 0
codeExamples: 0
---

### Getting all payments for a restaurant

Send a `GET` request to the `/payments` endpoint of the orders API to get a JSON array of the GUIDs of the payments processed in a business day at your restaurant. A business day's cutoff is defined by the restaurant's `closeoutHour`, which you can retrieve with the [restaurant API](apiRestaurantInformation.html).

Depending on the query parameter that you use, you can retrieve the following types of payments:

- The `paidBusinessDate` query parameter returns a list of the payments made during the business day. The payment method can be of any type, such as by cash, credit card, or gift card.


- The `refundBusinessDate` query parameter returns a list of the payments that were refunded during the business day. For details on refunded payments, see [Refunded payments](apiPaymentntInformation.html#apiRefundedPayments).


- The `voidBusinessDate` query parameter returns a list of the payments that were voided during the business day. For details on voided payments, see [Voided payments](apiPaymentntInformation.html#apiVoidedPayments).



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
      76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf" \[(1)](apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.html#d1e703C0BDE523-B62F-4A49-BD00-2E7817FF64CD-co)
      https://`[toast-api-hostname]`/orders/v2/payments?paidBusinessDate=20200211[(2)](apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.html#d1e708C0BDE523-B62F-4A49-BD00-2E7817FF64CD-co)
```



(1) Use the Toast-Restaurant-External-ID request parameter to specify the GUID of the restaurant for which payments will be returned.

(2) Specify the business date for order payments in the paidBusinessDate query parameter. Alternatively, you could query for refunds with the refundBusinessDate query parameter or for voids with the voidBusinessDate query parameter.

  
The following example shows the JSON response data for a GET request to the `/payments` endpoint.

**Example 3.2. Get all payments return data**

```
[[(1)](apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.html#d1e724C0BDE523-B62F-4A49-BD00-2E7817FF64CD-co)
  "361d140a-aa0b-43ad-98d6-516c416555d9",
  "198790e9-ea0d-4eb1-9bed-fc6c3d71d71e",
  "249c4be9-2236-4636-a90a-3ad15fb1fc69"
]
```



(1) The /payments endpoint returns a JSON array of payment GUIDs. In this example, the query returns three payments.

  
