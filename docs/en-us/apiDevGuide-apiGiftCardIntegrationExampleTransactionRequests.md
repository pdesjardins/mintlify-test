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
keywords: [GIFTCARD_REVERSE,GiftCardTransaction,GIFTCARD_REDEEM,redeemTransactionInformation,GiftCardTransactionResponse,transactionStatus,redeemResponse]
procedures: 0
codeExamples: 2
---

### Example gift card transaction request

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
\{
  "redeemTransactionInformation":\{
    "redeemedValue":11.80,
    "giftCardIdentifier":"231952736",
    "checkIdentifier":"41531b0c-ad11-4c11-9ad6-29ba76925a13",
    "isCashOut":false
  \}
\}
```



(1) This header parameter indicates the MIME type of the message body data.

(2) This header parameter indicates the type of gift card transaction. For more information, see Gift card transaction types.

(3) This header parameter supplies the identifier of the restaurant that processed the gift card transaction. The identifier is defined by the Toast platform. You receive the identifiers for Toast platform restaurants from the Toast integrations team when you implement your gift card integration.

(4) This header parameter supplies an identifier for the specific transaction request. You must keep this identifier in your integration implementation. The Toast platform may refer to the transaction identifier in a future GIFTCARD_REVERSEtransaction. For more information, see Gift card transaction types.

(5) This header parameter supplies the JWT authentication token that you can use to verify that the request is from the Toast platform and that the request has not been altered. For more information, see Gift card integration authentication.

(6) The message body of a gift card transaction request includes a JSON GiftCardTransaction object. For information about the values in a GiftCardTransaction object, see the gift card integration API reference documentation.

(7) Because this gift card transaction type is GIFTCARD_REDEEM, the GiftCardTransactionobject includes a redeemTransactionInformationvalue.

(8) Indicates the amount of money that the restaurant guest redeemed from the the gift card balance. For example, the restaurant guest might have used the gift card as a form of payment for a restaurant purchase.

(9) Indicates the identifier of the specific gift card account.

  
The following example shows an example gift card integration API response.

**Example 10.4. Gift card integration API transaction response**

```
\{
  "transactionStatus":"ACCEPT",
  "redeemResponse":\{
    "currentBalance":60.29,
    "redeemedValue":1
  \}
\}
```



(1) Your gift card integration API implementation returns a JSON GiftCardTransactionResponse object in the HTTP response to a gift card transaction request from the Toast platform. For information about the values in a GiftCardTransactionResponse object, see the gift card integration API reference documentation.

(2) Indicates the result of your attempt to process the transaction. For more information about the transactionStatus value, see Response status types.

(3) Because this gift card transaction type is GIFTCARD_REDEEM, the GiftCardTransactionResponse object includes a redeemResponse value.

(4) Indicates the amount of money available on the gift card after the transaction.

(5) Indicates the amount of money that the transaction deducted from the gift card balance.

  
