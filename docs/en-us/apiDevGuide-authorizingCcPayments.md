---
title: "Credit card payments"
id: authorizingCcPayments
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalSubmittingPaymentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating payment information"
previousSectionFile: apiDevGuide-apiSubmittingPaymentsIntro.md
previousSectionTitle: "Submitting payments"
nextSectionFile: apiDevGuide-apiCreatingAnOrderWithPaymentInformation.md
nextSectionTitle: "Alternative payment types"
externalReferences: [https://tools.ietf.org/html/rfc4122#section-4.4, https://tools.ietf.org/html/rfc8017#section-7.1, https://www.openssl.org/docs/man1.1.1/man1/openssl-pkeyutl.html]
excerpt: "You..."
procedures: 0
codeExamples: 0
---



> **Note**
> 
> A credit card authorization must be associated with an order. This prevents authorization misuse and fines.


You can authorize a credit card payment for a check and then apply that payment to a check when you create an order. The credit cards API processes the authorization for a credit card payment. You can use the authorized credit card payment as the payment for a check that you create in the orders API.

When you authorize a credit card payment, the credit cards API places a hold for the amount of the payment on the card account. For a period of five minutes, you can submit an order to the orders API using that payment. If you do not submit an order using the payment within five minutes, the credit cards API will automatically release the hold. You cannot apply the credit card payment to a check after the credit cards API releases the hold. When you apply a credit card payment to a check, the Toast platform will automatically capture payment from the card account after business hours on the day the order is fulfilled. If it fails to capture payment within four days, it will void the payment for the order.



> **Important**
> 
> DISCLAIMER: Compliance with PCI DSS and all other regulations or laws is solely your responsibility. The information provided is for informational purposes only and should not be relied upon or used as a substitute for consultation with a Qualified Security Assessor or other legal advisor. Please consult a professional advisor for a qualified opinion on the applicability of requirements to your business operations.


For general information about using the orders API, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).

## Overview of the credit card authorization and application process

The following procedure provides an overview of the process to authorize and apply a credit card payment.

**Procedure 3.1. To authorize and apply a credit card payment for an orders API order**

1. Submit a `POST` request to the `/prices` endpoint of the orders API to get the total price of each check in an order. For more information, see [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).


2. Generate a UUID unique identifier for the credit card payment.

The payment UUID is a path parameter for a `PUT` request to the `/merchants/&#123;merchantUuid}/payments/&#123;paymentUuid&#125;`resource.

You use the payment UUID to apply the authorized credit card payment to an order.

To generate the payment UUID, you must use the algorithm described in [version four of the UUID standard](https://tools.ietf.org/html/rfc4122#section-4.4).


3. Submit a `PUT` request to the `/merchants/&#123;merchantUuid}/payments/&#123;paymentUuid&#125;` resource of the credit cards API.

In the message body of the request, include the total price for all checks and encrypted credit card information. For more information, see [Authorizing a credit card payment](apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment).


4. Within five minutes, submit a `POST`request to the `/orders` endpoint of the orders API to add the order.

In the JSON message body data for a check, set the `guid` value of the payment object to the payment UUID of the credit card payment. For more information, see [Applying an authorized credit card payment to an orders API check](apiDevGuide-authorizingCcPayments#apiApplyingCCPaymentToOrder).



If a credit card payment cannot be authorized, the [ErrorMessage object](apiDevGuide-apiResponsesAndErrors#apiErrorMessage) typically includes a generic, non-null, error message such as `Invalid card data`.

Error messages in the credit cards API are intentionally not specific or detailed, to minimize the error information that reaches attackers that are attempting to make fraudulent payments.

For a list of common reasons for card denial, see [Card declined message reference](adminGuide-adminCreditCardDeclinedMessageReference).

## Authorizing a credit card payment

To authorize a credit card payment for a check, you send a `PUT` request to the `/merchants/&#123;merchantUuid}/payments/&#123;paymentUuid&#125;` resource of the credit cards API.

The credit cards API verifies that the credit card account has sufficient funds available and places a hold on the account for the amount of the payment.

**PUT request path parameters**

- *`merchantUuid`* - The Toast GUID for the restaurant that will collect the funds from the credit card payment.


- *`paymentUuid`* - A UUID unique identifier for the credit card payment. You generate the UUID for the payment. You use the identifier when you apply the credit card payment to a check. To generate the payment UUID, you must use the algorithm described in [version four of the UUID standard](https://tools.ietf.org/html/rfc4122#section-4.4).



The message body parameter for the `PUT`request is a JSON `PaymentAuthorization` object. The `PaymentAuthorization` object includes the information described in the following list.

**PUT request message body parameter information**

- How your integration received the credit card information for the authorization, and whether your organization will store the information for later use


- Encrypted and non-encrypted information about the credit card account


- The payment amount and tip amount for the authorization



The following example shows the JSON message body to `PUT` a credit card payment authorization request.

**Example 3.7. Authorization request message body**


```
{
  "encryptedCardData": "FBRdBx38xrQ8UUQTAVUI3mLddkqtuxX6huPOsI
1WKVS97ffQITY2yToeJU0e16aRo6ehZZxBO6YU0DKUOXiX8Kww1jXE3Rn5J8Do
8n3wSeLV3Qomn0VvAd+5YT8bUijVs0aRUy3u34DpYwMkon0WMkq8BNGQWk3Whd
3qJEdi/SagofuO0yExxlixklflwAIkbuZZ2tHtp+FV7n+UAfXPeSgXRrX6Rkal
ir3OKZtUrC8aiymc7Xs9G4w4+bDBa/kArP1D7e3A42+wIsQicc9rL//B0GyQll
Cu2dnrEDSllcU3wZSRLVPjuoXmyK28JO40Grzeq2ZKAKepnTDW9m84ag==",
  "keyId": "RSA-OAEP-SHA256::a253759c-1c91-4f22-9db9-71ba24738f8d_PartnerName"
  "amount": 98.76,
  "tipAmount": 24.69,
  "willSaveCard": true,
  "cardNumberOrigin": "PARTNER_VAULT",
  "requestMetadata": {
    "localTransactionDate": "2019-08-24T22:00:00.000+0000",
    "originIPAddr": "189.219.91.62",
    "partnerServiceInfo": {
      "instanceId": "my-api-client"
    },
    "cardFirst6": "411111",
    "cardLast4": "1111",
    "billingAddress": {
        "name": "Clark Kent",
        "phone": "555-555-5555",
        "address1": "123 Main Street",
        "address2": "",
        "city": "Boston",
        "region": "MA",
        "postalCode": 02215,
        "country": "USA"
    },
    "deliveryAddress": {
        "name": "Lois Lane",
        "phone": "111-555-5555",
        "address1": "789 Grand Avenue",
        "address2": "",
        "city": "New York",
        "region": "NY",
        "postalCode": 10001,
        "country": "USA"
    },
    "guestIdentifier": "toastyguest@domain.com",(14)
    "guestEmail": "toastyguest@domain.com",
    "userAgent": "Browser/1.0",
    "appName": "Our Company's Amazing Android App",
    "appVersion": "4.2"
  }
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e111F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Identifying credit card information, including the account number. You must encrypt this information and encode it in base64 format. For more information, see <a href="apiDevGuide-authorizingCcPayments#apiEncryptingCreditCardInformation" className="">Encrypting credit card information</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e113F291C744-5561-42C1-BD4E-F18BB8532ABC" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The encryption key identifier that you receive from from Toast integration support. The identifier string indicates the algorithm and the specific encryption key used to encrypt the credit card data for the request. For information about encryption algorithms and key identifiers, see <a href="apiDevGuide-authorizingCcPayments#apiCreditCardInformationEncryptionAlgorithms" className="">Encryption algorithms</a> and <a href="apiDevGuide-authorizingCcPayments#apiEncryptionKeysAndKeyIdentifiers" className="">Encryption keys and key identifiers</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e113F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the check that you will apply the credit card payment to. For information about getting the total price of a check, see <a href="apiDevGuide-apiOrderPrices#apiGettingCheckPrices" className="">Getting check prices before you submit an order</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e115F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the gratuity that the guest applied to the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#willSaveCard" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">willSaveCard</code> value indicates whether organizations store restaurant guests' credit card information for future use. <code className="font-mono text-sm">true</code> indicates that your organization stores credit card information used in a credit card authorization. <code className="font-mono text-sm">false</code> indicates that your organization does not store the credit card information used in a credit card authorization.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#cardNumberOrigin" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">cardNumberOrigin</code> value is used for "card on file" reporting. If your organization uses stored credit card information for a credit card authorization, you must set the value of <code className="font-mono text-sm">cardNumberOrigin</code> to <code className="font-mono text-sm">PARTNER_VAULT</code>. The default value for <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">END_USER</code>. For more information, see <a href="apiDevGuide-authorizingCcPayments#apiCardNumberOriginForFraudDetection" className="">Using card number origin values</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e117F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when the guest presents their credit card, in <a href="apiDevGuide-api_dates_and_timestamps" className="">ISO 8601 format</a>. The <code className="font-mono text-sm">localTransactionDate</code> must be set to the current date and time, and cannot be a future date.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e119F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e122F291C744-5561-42C1-BD4E-F18BB8532F7A" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An identifier for the server or process that operates as an API client to process the credit card authorization. For example, this might be the identifier of a client software process that appears in log information.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#first6" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The first six digits of the credit card number. The first six digits are the bank identification number (BIN) for the card. The value must match exactly the information provided in the encrypted card data. This value is required when <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">END_USER</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#last4" className="">(11)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The last four digits of the credit card number. The value must match exactly the information provided in the encrypted card data. This value is required when <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">END_USER</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#billingAddress" className="">(12)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The billing address associated with the credit card. When <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">END_USER</code>, <code className="font-mono text-sm">billingAddress</code> is required and must include at least a <code className="font-mono text-sm">postalCode</code> and <code className="font-mono text-sm">country</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#deliveryAddress" className="">(13)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A delivery address for the order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#guestID" className="">(14)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An identifier for the guest making the payment, such as an email address or phone number. This value is required when <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">END_USER</code>. For more information, see <a href="apiDevGuide-authorizingCcPayments#apiUsingGuestIdentifierValues" className="">Using guestIdentifier values</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#guestEmail" className="">(15)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The email address of the guest placing the payment. If you include an email address in the <code className="font-mono text-sm">guestIdentifier</code> value, the email address in the <code className="font-mono text-sm">guestEmail</code> value should match the <code className="font-mono text-sm">guestIdentifier</code>. This can help prevent fraudulent transactions. This field is optional.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#userAgent" className="">(16)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For payments taken through a web browser, the browser's user agent string.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#appName" className="">(17)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A company-specific name for the mobile app (if any) the payment is made through. For example, use 'MyCompany Android App' instead of 'Android App'.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#appVersion" className="">(18)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The version of the mobile app (if any) that the payment is made through. You can use any string to represent the app version. There are no format or content requirements.</p></div></td>
    </tr>
  
## Optimizing fraud detection

The Toast platform performs fraud detection when it authorizes credit card payments. To ensure maximum protection from fraudulent transactions for your organization and for restaurant guests, your integration *must* send accurate information about the credit card transaction and the transaction type.

Toast platform fraud detection uses the following information from a credit card authorization request:

- `cardNumberOrigin` - Indicates whether the credit card information in the authorization request was supplied directly by the guest or from stored credit card information from a previous transaction.

You include the `cardNumberOrigin` value in a `PaymentAuthorization` object in the message body parameter of a credit card authorization request. For more information, see [Table 3.1, “cardNumberOrigin values”](apiDevGuide-authorizingCcPayments#apiCardNumberOriginValues).


- `guestIdentifier` - An identification string that your integration assigns to guests who initiate credit card authorizations.

You include the `guestIdentifier` value in the `PaymentRequestMetadata` object for your credit card authorization request. For more information, see [Using guestIdentifier values](apiDevGuide-authorizingCcPayments#apiUsingGuestIdentifierValues).



### Using card number origin values

The `PUT` request message body for authorizing a payment includes a `cardNumberOrigin` value. This value indicates whether:

- The guest provided the credit card information directly (`END_USER`)


- The credit card information was retrieved from secure storage (`PARTNER_VAULT`)



To ensure that your guests' transactions receive adequate fraud protection, your integration *must* send the `cardNumberOrigin` value that correctly indicates the way that your integration acquired credit card information.

- If a guest provided credit card information directly, you must set the `cardNumberOrigin` value to `END_USER`.


- If your integration retrieved the credit card information from secure storage, you must set the `cardNumberOrigin` value to `PARTNER_VAULT`.





> **Important**
> 
> If you do not include the `cardNumberOrigin` value that correctly indicates the source of the credit card information, you reduce the effectiveness of the fraud detection provided by the Toast platform. Make sure that your integration includes the correct `cardNumberOrigin` value to ensure the most accurate fraud detection and to minimize unnecessarily declined transactions.




> **Note**
> 
> The `PaymentRequestMetadata` object in the `requestMetadata` value *must* include the following values:
- `cardFirst6`


- `cardLast4`


- `billingAddress`


- `guestIdentifier`


- `originIPAddr`





The following table provides more information about the values you include in the `cardNumberOrigin` value in a `PaymentAuthorization` object in the message body parameter of a credit card authorization request.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Value</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Explanation</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">END_USER</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The guest provided the credit card information directly.</p> <p className="text-base leading-relaxed">The <code className="font-mono text-sm">PaymentRequestMetadata</code> object in the <code className="font-mono text-sm">requestMetadata</code> value <em className="">must</em>  include: </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">cardFirst6</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">cardLast4</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">billingAddress</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">guestIdentifier</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">originIPAddr</code></p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">PARTNER_VAULT</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Your integration retrieved the credit card information from secure storage.</p> <p className="text-base leading-relaxed">The <code className="font-mono text-sm">PaymentRequestMetadata</code> object in the <code className="font-mono text-sm">requestMetadata</code> value <em className="">must</em>  include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">cardFirst6</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">cardLast4</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">billingAddress</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">guestIdentifier</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">originIPAddr</code></p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>



> **Note**
> 
> When you authorize a payment for a new credit card, you must set the `cardNumberOrigin` value to `END_USER`, even if you use an external credit card vaulting service to save guests' credit cards. Setting the `cardNumberOrigin` value to `END_USER` gives you additional fraud protection when authorizing payment for new credit cards.


### Using guestIdentifier values

The Toast platform uses the `guestIdentifier` value for fraud evaluation. The `guestIdentifier` value is a unique identifier for a restaurant guest associated with a credit card payment.

You use the same identifier for a guest even when that guest uses different methods of payment. The `guestIdentifier` value should be unique per guest but not unique per credit card. In other words, if one guest uses two credit cards, you use the same `guestIdentifier` when authorizing both cards. An example of a value for the `guestIdentifier` field is a guest's email address.

If you use the same `guestIdentifier` value repeatedly on many card authorizations for multiple guests, authorizations using this `guestIdentifier` are likely to be declined because of the suspicious activity. A `guestIdentifier` value of `0` will cause credit card authorizations to fail.

## Applying an authorized credit card payment to an orders API check

To apply an authorized credit card payment to a check in an orders API order, you include the payment UUID that you authorized as the payment GUID. The Toast platform applies the credit card payment to the check and attempts to capture the funds later in the business day.



> **Note**
> 
> You must `POST` an order within five minutes of the credit card payment authorization. After five minutes, the credit card API automatically voids the payment.


The following example shows the JSON message body data that applies an authorized credit card payment to a check. Most contents of the order object have been omitted from this example. For more information about `POST`ing orders in the orders API, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).

**Example 3.8. Example of applying an authorized credit card payment to a check**


```
{
  "entityType": "Order",

    [contents omitted]

  "checks": [
    {
      "entityType": "Check",

        [contents omitted]

      "payments": [
        {
          "guid": "78700301-55B6-4C0F-8C69-69E8D3593850",
          "paidDate": "2018-01-24T22:00:00.000+0000",
          "type": "CREDIT",
          "amount": "98.76",
          "tipAmount": "24.69"
        }
      ]
    }
  ]
}

```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e195A18BC72A-4EBC-425E-BD6C-E5E3E35516D3" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment UUID that you assign to the payment when you authorize it in the credit cards API. You supply this UUID in the <em className=""><code className="font-mono text-sm">paymentUuid</code></em>  path parameter for the <code className="font-mono text-sm">PUT</code> request to authorize the payment. For more information, see <a href="apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment" className="">Authorizing a credit card payment</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e197A18BC72A-4EBC-425E-BD6C-E5E3E35516D3" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time when Toast processes the credit card payment, presented in ISO 8601 format. Credit card authorizations expire within seven days, therefore the <code className="font-mono text-sm">paidDate</code> cannot be more than seven days after the <code className="font-mono text-sm">localTransactionDate</code>. The <code className="font-mono text-sm">paidDate</code> is available in reporting data.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e199A18BC72A-4EBC-425E-BD6C-E5E3E35516D3" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The type of payment. For credit card payments, this value is <code className="font-mono text-sm">CREDIT</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e201A18BC72A-4EBC-425E-BD6C-E5E3E35516D3" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price of the check that you will apply the credit card payment to. For information about getting the total price of a check, see <a href="apiDevGuide-apiOrderPrices#apiGettingCheckPrices" className="">Getting check prices before you submit an order</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e203A18BC72A-4EBC-425E-BD6C-E5E3E35516D3" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The amount of the gratuity that the guest applied to the check.</p></div></td>
    </tr>
  
## Encrypting credit card information



> **Important**
> 
> DISCLAIMER: Compliance with PCI DSS and all other regulations or laws is solely your responsibility. The information provided is for informational purposes only and should not be relied upon or used as a substitute for consultation with a Qualified Security Assessor or other legal advisor. Please consult a professional advisor for a qualified opinion on the applicability of requirements to your business operations.


When you send a `PUT` request to authorize a payment in the credit cards API, you include identifying credit card information in the message body data. The JSON payment authorization object in the message body data includes an `encryptedCardData`value that contains a base64 representation of the encrypted credit card information.

To compose the `encryptedCardData` value, you include credit card information in a JSON object and encrypt it using the encryption algorithm and RSA public key that corresponds to the encryption key identifier (`keyId`) that you receive from Toast integration support.

For information about supported encryption algorithms, see [Encryption algorithms](apiDevGuide-authorizingCcPayments#apiCreditCardInformationEncryptionAlgorithms). For information about key identifiers, see [Encryption keys and key identifiers](apiDevGuide-authorizingCcPayments#apiEncryptionKeysAndKeyIdentifiers).

The following example shows credit card information that you encrypt and base64 encode in order to generate an `encryptedCardData`value.

**Example 3.9. Example credit card information for an encryptedCardData value**


```
{
  "cardNumber" : "4111111111111111",
  "zipCode" : "01234",
  "cvv" : "321",
  "expMonth" : "01",
  "expYear" : "20",
  "country" : "USA"
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e5385CE9715-52F9-43FB-AB1A-9F382E163FBA" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The primary account number (PAN) of the card, which the API validates using the ISO-standard Luhn algorithm.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e5585CE9715-52F9-43FB-AB1A-9F382E163FBA" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The ZIP or postal code of the card holder's billing address. This value is required, must be numeric, and must not be an empty string. Do not include hyphens (<code className="font-mono text-sm">-</code>) in the string.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e5785CE9715-52F9-43FB-AB1A-9F382E163FBA" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The three- or four-digit card verification value (CVV) of the card. When <code className="font-mono text-sm">cardNumberOrigin</code> is <code className="font-mono text-sm">PARTNER_VAULT</code> in the credit card authorization request, the CVV is not required, but it is validated for correctness if it is submitted. If you do not submit a CVV on a credit card authorization request, you can either omit the <code className="font-mono text-sm">cvv</code> value on your authorization, or submit a <code className="font-mono text-sm">cvv</code> value of <code className="font-mono text-sm">null</code>. The <code className="font-mono text-sm">cvv</code> value you submit should not be an empty string (<code className="font-mono text-sm">""</code>).</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e5985CE9715-52F9-43FB-AB1A-9F382E163FBA" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The two-digit month of the expiration date for the card.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e6185CE9715-52F9-43FB-AB1A-9F382E163FBA" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The two-digit year of the expiration date for the card.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-apiCcEncryptedInfoCountry" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The country of the card holder's billing address, in ISO 3166-1 alpha-3 format.</p></div></td>
    </tr>
  
The following example shows the base64-encoded and encrypted credit card information in the `encryptedCardData` value.

**Example 3.10. Base64-encoded and encrypted credit card information in the `encryptedCardData` value**


```
{
  "encryptedCardData": "yu3BmKwL65F3UVOrsQEZxhrSyN//QkwIhEjgAFVYV
    nl28IyQ+bHIdez1bcU0CSuljngjkQHGTAjQumBpSfqqDd61bKQw/drHJAWR10
    bIZU/q0iLHPf3bvt6h1rA0ViN0byr+zkFDo5tosGGf9VeJz6Dd5OMNunbgViO
    HC1TPDS6bE90oqczsJjVwjS2/n2hO444gb1wPl3GbcwHmsrGDxW4KYn99FOk7
    gLzY4C5QvQG5bNRm4mA/30bMEAeu9hzlQSGS0b/J2EKAjkHV1+b1jA91rwHDV
    +DQ0iRPRQIvAY/UF4qrQwMC0SgmEHLMqaoPtCi4qEvWe0JCQ48LxeUmDg==",
  "keyId": "RSA-OAEP-SHA256::dff3e2eb-3abd-458c-b7fc-7692202d5895_myKeyIdentifier",
  "willSaveCard": false,
  "cardNumberOrigin": "END_USER",
  "amount": 100.00,
  "tipAmount": 25.00,
  "requestMetadata": {
    "localTransactionDate": "2019-03-11T17:32:00.000+0000",
    "originIPAddr": "123.456.78.90",
    "partnerServiceInfo": {
      "instanceId": "myClient"
    }
  }
}
```

  
### Encryption algorithms

When you request credit card authorization for a payment, you encrypt credit card information. The public key that you receive from the Toast integrations team uses one of the following encryption algorithms to encrypt credit card information in an authentication request:

- RSA-OAEP with SHA256 hashing ([RSAES-OAEP](https://tools.ietf.org/html/rfc8017#section-7.1))

This algorithm is supported by modern web browsers by default. The Toast integrations team issues encryption keys that use this algorithm.


- RSA-OAEP with SHA1 hashing ([RSAES-OAEP](https://tools.ietf.org/html/rfc8017#section-7.1))



> **Important**
> 
> The RSA-OAEP with SHA1 hashing padding encryption algorithm is deprecated.




#### Identifying the encryption algorithm in an authorization request

The encryption key identifier string that you receive from the Toast integrations team identifies the algorithm that you use to encrypt credit card information.



> **Note**
> 
> You must use the encryption algorithm that corresponds to the encryption key that you receive from the Toast integrations team. *Do not alter any part of the encryption key identifier string. Do not use the contents of the identifier string to control any part of your integration software.*


The encryption key identifier string includes:

- The identification string for the algorithm


- Two colon characters


- The identifier of the public encryption key that you received from the Toast integrations team



For more information about key identifiers, see [Encryption keys and key identifiers](apiDevGuide-authorizingCcPayments#apiEncryptionKeysAndKeyIdentifiers).

The following example shows the identification string for an encryption algorithm and the identifier of a public encryption key in a `keyId` value.


```
RSA-OAEP-SHA256::a253759c-1c91-4f22-9db9-71ba24738f8d_MyRestaurantService
```

The following table includes the identification strings for the encryption algorithms that you can use in credit cards API authorization requests.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Algorithm</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Identification string</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">RSA-OAEP with SHA256 hashing</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">RSA-OAEP-SHA256</div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">RSA-OAEP with SHA1 hashing, deprecated</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">RSA-OAEP-SHA1</div></td>
    </tr>
  </tbody>
</table>
</div>

For more information about making an authorization request, see [Authorizing a credit card payment](apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment).



> **Important**
> 
> The RSA-OAEP with SHA1 hashing encryption algorithm is deprecated.


#### Example encryption using RSA OAEP with SHA256 hashing

The following example UNIX command-line command uses the **openssl** version 1.1.1 utility to encrypt and base64 encode a file that contains JSON credit card information. *This example command is intended for integration development and testing. It is not suitable for production use.*

**Example 3.11. Example openssl commands to encrypt and base64 encode an encryptedCardData value**


```
openssl pkeyutl \
-in `my-credit-card-information.json` \
-encrypt -pubin -inkey `my-public-key.pem` \
-pkeyopt rsa_padding_mode:oaep -pkeyopt rsa_mgf1_md:sha256 -pkeyopt rsa_oaep_md:sha256 \
| openssl base64 \
| tr -d "\n"
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e63595B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <strong className="font-semibold">pkeyutl</strong>  command for the <strong className="font-semibold">openssl</strong>  utility can encrypt values. For more information, see the <strong className="font-semibold">openssl</strong>  utility <a href="https://www.openssl.org/docs/man1.1.1/man1/openssl-pkeyutl.html" className="">documentation</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e64095B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <em className=""><code className="font-mono text-sm">-in</code></em>  argument provides the path to a file holding the JSON credit card information. See <a href="apiDevGuide-authorizingCcPayments#apiExampleJsonCreditCardInformation" className="">Example 3.9, “Example credit card information for an encryptedCardData value”</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e64595B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <em className=""><code className="font-mono text-sm">-inkey</code></em>  argument provides the path to a file holding the RSA public key that corresponds with your Toast API client identifier.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e64895B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">These arguments set openssl utility options to use the RSA-OAEP with SHA256 hashing encryption algorithm.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e65095B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <strong className="font-semibold">base64</strong>  command for the <strong className="font-semibold">openssl</strong>  utility encodes binary data in base64 format.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e65295B32F21-5B43-4BA2-9C4E-6CE0DE6C4387" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This <strong className="font-semibold">tr</strong>  command strips new line characters out of the base64-encoded credit card information. Removing new line characters makes it easier to include the base64-encoded string in the JSON <code className="font-mono text-sm">encryptedCardData</code> value for a credit cards API authorization request.</p></div></td>
    </tr>
  
### Encryption keys and key identifiers

When you make a credit card authorization request, you specify the identifier of the encryption key that you are using. The Toast integrations team can issue you multiple encryption keys to make it easier for you to refresh your keys without interrupting your credit cards API integration. Specifying which key you use to encrypt credit card information allows the Toast platform to use the correct algorithm and private key to decrypt the information in your request.

In an authorization request, you include the identifier of the public encryption key that you received from the Toast integrations team in the `keyId` value of a `PaymentAuthorization`object in the request message body. For information about encryption algorithm identifiers, see [Identifying the encryption algorithm in an authorization request](apiDevGuide-authorizingCcPayments#apiSpecifyingEncryptionAlgorithmInAnAuthorizationRequest).

For more information about making an authorization request, see [Authorizing a credit card payment](apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment).

### Testing encryption in the sandbox environment

You can test encrypting credit card information for credit cards API authorization requests in the sandbox environment.

- The sandbox environment supports the RSA-OAEP with SHA256 and SHA1 hashing encryption algorithms.


- You receive separate encryption keys from Toast integrations support for the production and sandbox environments. Encryption keys for the sandbox environment do not work in the production environment.


- You can use a test public encryption key for the sandbox environment. The Toast integrations support team provides you with a test encryption key.


- In the sandbox environment, the credit cards API does not validate whether the CVV, ZIP code or expiration date you submit are formatted correctly. For more information about the correct way to format these values see [Encrypting credit card information](apiDevGuide-authorizingCcPayments#apiEncryptingCreditCardInformation).



For more information about Toast API environments, see [Environments](apiDevGuide-apiEnvironments).

