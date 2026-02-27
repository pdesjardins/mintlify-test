---
title: "Getting information about a specific payment"
id: apiPaymentntInformation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting payment information"
previousSectionFile: apiDevGuide-apiAllPaymentsInRestaurants.md
previousSectionTitle: "Getting all payments for a restaurant"
nextSectionFile: apiDevGuide-portalSubmittingPaymentsOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating payment information"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/]
excerpt: "Send a GET request to..."
keywords: ["getting", "information", "about", "specific", "payment", "Payment", "CREDIT", "VoidInformation", "Refund"]
procedures: 0
codeExamples: 2
---

Send a `GET` request to the `/payments/<em>&#123;guid&#125;</em>` endpoint of the orders API to obtain detailed information about a specific payment. The endpoint returns a `Payment` object that contains information about the payment. For information about the values of the `Payment` object, see [reference documentation for the orders API](https://doc.toasttab.com/openapi/orders/overview/).

The following example **curl** command sends a `GET` request to the `/payments/<em>&#123;guid&#125;</em>` endpoint for a specific payment.

**Example 3.3. Get information of a specific payment**


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
      https://`[toast-api-hostname]`/orders/v2/payments/361d140a-aa0b-43ad-98d6-516c416555d9
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8108E4737FC-3875-4918-866A-092F630A0814" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use the <code className="font-mono text-sm">Toast-Restaurant-External-ID</code> request parameter to specify the GUID of the restaurant in which the payment was made.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8158E4737FC-3875-4918-866A-092F630A0814" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specify the payment GUID, which you can get from the <code className="font-mono text-sm">/payments</code> endpoint of the orders API.</p></div></td>
    </tr>
  
The following example shows the JSON response data for a GET request to the `/payments/<em>&#123;guid&#125;</em>`endpoint. The payment method for this sample payment was a credit card.

**Example 3.4. Get payment return data**


```
{
  "guid": "361d140a-aa0b-43ad-98d6-516c416555d9",
  "entityType": "OrderPayment",
  "externalId": null,
  "originalProcessingFee": null,
  "amount": 57.73,
  "tipAmount": 0,
  "amountTendered": 0,
  "cashDrawer": null,
  "cardType": "VISA",
  "lastModifiedDevice": {
    "id": "7c664bbbb33913bd"
  },
  "refundStatus": "NONE",
  "houseAccount": null,
  "type": "CREDIT",
  "voidInfo": null,
  "otherPayment": null,
  "mcaRepaymentAmount": null,
  "createdDevice": {
    "id": "7c664bbbb33913bd"
  },
  "paidDate": "2020-02-11T16:38:32.774+0000",
  "cardEntryMode": "KEYED",
  "paymentStatus": "CAPTURED",
  "paidBusinessDate": 20200211,
  "last4Digits": "1111",
  "refund": null,
  "orderGuid": "86675d88-b27e-4850-94ab-48662563eae8",
  "checkGuid": "ed4b222f-5259-43fd-8db0-1243a11ed554"
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8554F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">guid</code> value contains the unique Toast POS identifier of the payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8574F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the payment, including taxes and service charges but excluding tips.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8594F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount tipped on this payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8614F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If a house account was used to pay the check, this value contains reference information (such as the GUID) of the house account. The value is <code className="font-mono text-sm">null</code> if a house account was not used for payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8634F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment method, such as <code className="font-mono text-sm">CREDIT</code> for a credit card.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8664F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the payment was voided, this value contains a <code className="font-mono text-sm">VoidInformation</code> object with information about the void. For details, see <a href="apiDevGuide-apiPaymentntInformation#apiVoidedPayments" className="">Voided payments</a>. The value is <code className="font-mono text-sm">null</code> if the payment has not been voided.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8684F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reference information (such as the GUID) of an other payment option used to pay the check. The value is <code className="font-mono text-sm">null</code> if an other payment option was not used for payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8704F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the payment was made.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8724F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For credit card payments, specifies how the credit card data was obtained. The value is <code className="font-mono text-sm">null</code> if a credit card was not used for payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8744F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The status of the payment. In this example, the payment has been captured.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8764F5CFC3E-3A32-4EF2-AB9F-D1CA606D8F49" className="">(11)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the payment has been refunded, this value contains a <code className="font-mono text-sm">Refund</code> object with information about the refund. For details, see <a href="apiDevGuide-apiPaymentntInformation#apiRefundedPayments" className="">Refunded payments</a>. The value is <code className="font-mono text-sm">null</code> if the payment has not been refunded.</p></div></td>
    </tr>
  
The following sections provide information about voided and refunded payments.

- [Voided payments](apiDevGuide-apiPaymentntInformation#apiVoidedPayments)


- [Refunded payments](apiDevGuide-apiPaymentntInformation#apiRefundedPayments)



## Voided payments

The `/payments/<em>&#123;guid&#125;</em>`endpoint can return data for voided payments. A void is a payment that has been fully or partially voided. Voids can be issued on the entire check or on one or more specific items.

With one exception, any payment can be voided. The exception is a credit card payment that has been captured (the payment cannot be voided but can be refunded).

In the return data for a voided payment, the `Payment` object includes a `VoidInformation`object that contains details of the void operation.

The following example shows the JSON response data for a voided cash payment.

**Example 3.5. Example of a voided cash payment**


```
{
  "guid": "2f20387c-2b39-4c67-8898-b3faccb3ce06",
  "entityType": "OrderPayment",
  "externalId": null,
  "originalProcessingFee": null,
  "amount": 42.8,
  "tipAmount": 0,
  "amountTendered": 42.8,
  "cashDrawer": {
    "guid": "30795302-5fc9-461c-b314-ac8ea6e55cd5",
    "entityType": "CashDrawer",
    "externalId": null
  },
  "cardType": null,
  "lastModifiedDevice": {
    "id": "7c664bbbb33913bd"
  },
  "refundStatus": "NONE",
  "houseAccount": null,
  "type": "CASH",
  "voidInfo": {
    "voidUser": {
      "guid": "9659c962-7a8a-43ec-9343-47cafb68e83b",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "voidApprover": {
      "guid": "9659c962-7a8a-43ec-9343-47cafb68e83b",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "voidDate": "2020-02-18T19:24:56.311+0000",
    "voidBusinessDate": 20200218,
    "voidReason": null 
  },
  "otherPayment": null,
  "mcaRepaymentAmount": null,
  "createdDevice": {
    "id": "7c664bbbb33913bd"
  },
  "paidDate": "2020-02-18T18:10:28.187+0000",
  "cardEntryMode": null,
  "paymentStatus": "VOIDED",
  "paidBusinessDate": 20200218, 
  "last4Digits": null, 
  "refund": null
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8873DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">VoidInformation</code> object with details of the void.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8893DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant employee who voided the check or the item. The <code className="font-mono text-sm">guid</code> value lists the unique Toast POS identifier of the employee. For details on retrieving information about employees, see <a href="apiDevGuide-api_get_all_employees" className="">Getting all employees of a restaurant</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8913DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant employee who approved the void. The employee approving the void may be the same person who voided the payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8933DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the payment was voided.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8953DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The business date when the payment was voided.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e8983DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The pre-configured void reason that was specified for the void. The value is <code className="font-mono text-sm">null</code> if a void reason was not specified.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9003DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the original (pre-void) payment was made.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e9023DB65CBB-6A0B-4300-B1BB-FB6BFFD86ACF" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The current status of the payment, which is <code className="font-mono text-sm">VOIDED</code> for voided payments.</p></div></td>
    </tr>
  
## Refunded payments

The `/payments/<em>&#123;guid&#125;</em>`endpoint can return data for refunded payments. A refund is a credit card payment that has been fully reversed after it was captured. Refunds cannot be issued on specific items, but instead can only be issued on the entire check.

In the return data for a refunded payment, the `Payment` object includes a `Refund` object with details of the refund operation.

The following example shows the JSON response data for a refunded credit card payment.

**Example 3.6. Example of a refunded payment**


```
{
  "guid": "3e95fde2-da0f-4057-b91c-840b43e637c5",
  "entityType": "OrderPayment",
  "externalId": null,
  "originalProcessingFee": null,
  "amount": 6.36,
  "tipAmount": 0.0,
  "amountTendered": 6.36,
  "cashDrawer": null,
  "cardType": "VISA",
  "lastModifiedDevice": {
    "id": null
  },
  "refundStatus": "FULL",
  "houseAccount": null,
  "type": "CREDIT",
  "voidInfo": null,
  "otherPayment": null,
  "mcaRepaymentAmount": null,
  "createdDevice": {
    "id": null
  },
  "paidDate": "2020-02-19T19:47:51.206+0000",
  "cardEntryMode": "ONLINE",
  "paymentStatus": "CAPTURED",
  "paidBusinessDate": 20200219,
  "last4Digits": "1111",
  "refund": {
    "refundAmount": 6.36,
    "tipRefundAmount": 0.0,
    "refundDate": "2020-02-19T19:48:31.828+0000",
    "refundBusinessDate": 20200219
  }
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11385397DA82-3E87-45E1-9461-6911EBC8A028" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The status of the refund. A <code className="font-mono text-sm">FULL</code> status means that a full refund was made on this payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11405397DA82-3E87-45E1-9461-6911EBC8A028" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the original (pre-refund) payment was made.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11425397DA82-3E87-45E1-9461-6911EBC8A028" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">Refund</code> object with details of the refund.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11445397DA82-3E87-45E1-9461-6911EBC8A028" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the refund, excluding the tip.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11465397DA82-3E87-45E1-9461-6911EBC8A028" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the tip refund.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11495397DA82-3E87-45E1-9461-6911EBC8A028" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the payment was refunded.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e11515397DA82-3E87-45E1-9461-6911EBC8A028" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The business date when the payment was refunded.</p></div></td>
    </tr>
  
