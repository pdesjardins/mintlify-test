---
title: "Example gift card transaction request"
id: apiGiftCardIntegrationExampleTransactionRequests
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Gift Card Integrations"
previousSectionFile: apiDevGuide-apiPhysicalGiftCardRequirements.md
previousSectionTitle: "Physical gift card requirements"
nextSectionFile: apiDevGuide-apiGiftCardIntegrationReferenceApiImplementation.md
nextSectionTitle: "Reference gift card API implementation"
externalReferences: [https://doc.toasttab.com/openapi/giftcards/overview/]
excerpt: "The following example shows an example gift card integration API request."
keywords: ["GIFTCARD_REVERSE", "GiftCardTransaction", "GIFTCARD_REDEEM", "redeemTransactionInformation", "GiftCardTransactionResponse", "transactionStatus", "redeemResponse"]
procedures: 0
codeExamples: 2
---

The following example shows an example gift card integration API request.

**Example 10.3. Gift card integration API transaction request**


```
\> Content-Type: application/json
\> Toast-Transaction-Type: GIFTCARD_REDEEM
\> Toast-Restaurant-External-ID: 76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf
\> Toast-Transaction-GUID: 63fdc064-c97e-431f-9cb2-0699c6488237
\> Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxM
   jM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.Sf
   lKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
{
  "redeemTransactionInformation":{
    "redeemedValue":11.80,
    "giftCardIdentifier":"231952736",
    "checkIdentifier":"41531b0c-ad11-4c11-9ad6-29ba76925a13",
    "isCashOut":false
  }
}
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7809F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(1)</a></div></td>
      <td className=""><div className="">This header parameter indicates the MIME type of the message body data.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7829F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(2)</a></div></td>
      <td className=""><div className="">This header parameter indicates the type of gift card transaction. For more information, see <a href="apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationTransactionTypes" className="">Gift card transaction types</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7849F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(3)</a></div></td>
      <td className=""><div className="">This header parameter supplies the identifier of the restaurant that processed the gift card transaction. The identifier is defined by the Toast platform. You receive the identifiers for Toast platform restaurants from the Toast integrations team when you implement your gift card integration.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7869F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(4)</a></div></td>
      <td className=""><div className="">This header parameter supplies an identifier for the specific transaction request. You must keep this identifier in your integration implementation. The Toast platform may refer to the transaction identifier in a future <code className="">GIFTCARD_REVERSE</code> transaction. For more information, see <a href="apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationTransactionTypes" className="">Gift card transaction types</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7889F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(5)</a></div></td>
      <td className=""><div className="">This header parameter supplies the JWT authentication token that you can use to verify that the request is from the Toast platform and that the request has not been altered. For more information, see <a href="apiDevGuide-apiGiftCardIntegrationAuthentication" className="">Gift card integration authentication</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7919F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(6)</a></div></td>
      <td className=""><div className="">The message body of a gift card transaction request includes a JSON <code className="">GiftCardTransaction</code> object. For information about the values in a <code className="">GiftCardTransaction</code> object, see the <a href="https://doc.toasttab.com/openapi/giftcards/overview/" className="">gift card integration API reference documentation</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7939F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(7)</a></div></td>
      <td className=""><div className="">Because this gift card transaction type is <code className="">GIFTCARD_REDEEM</code>, the <code className="">GiftCardTransaction</code> object includes a <code className="">redeemTransactionInformation</code> value.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7959F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(8)</a></div></td>
      <td className=""><div className="">Indicates the amount of money that the restaurant guest redeemed from the the gift card balance. For example, the restaurant guest might have used the gift card as a form of payment for a restaurant purchase.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e7979F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(9)</a></div></td>
      <td className=""><div className="">Indicates the identifier of the specific gift card account.</div></td>
    </tr>
  
The following example shows an example gift card integration API response.

**Example 10.4. Gift card integration API transaction response**


```
{
  "transactionStatus":"ACCEPT",
  "redeemResponse":{
    "currentBalance":60.29,
    "redeemedValue":1
  }
}
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e8119F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(1)</a></div></td>
      <td className=""><div className="">Your gift card integration API implementation returns a JSON <code className="">GiftCardTransactionResponse</code> object in the HTTP response to a gift card transaction request from the Toast platform. For information about the values in a <code className="">GiftCardTransactionResponse</code> object, see the <a href="https://doc.toasttab.com/openapi/giftcards/overview/" className="">gift card integration API reference documentation</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e8139F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(2)</a></div></td>
      <td className=""><div className="">Indicates the result of your attempt to process the transaction. For more information about the <code className="">transactionStatus</code> value, see <a href="apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationResponseTypes" className="">Response status types</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e8159F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(3)</a></div></td>
      <td className=""><div className="">Because this gift card transaction type is <code className="">GIFTCARD_REDEEM</code>, the <code className="">GiftCardTransaction</code>Response object includes a <code className="">redeemResponse</code> value.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e8179F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(4)</a></div></td>
      <td className=""><div className="">Indicates the amount of money available on the gift card after the transaction.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e8199F9FF995-7EA4-424B-B7ED-3C6FDAD1DB2F" className="">(5)</a></div></td>
      <td className=""><div className="">Indicates the amount of money that the transaction deducted from the gift card balance.</div></td>
    </tr>
  
