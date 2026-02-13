---
title: "Error handling"
id: apiLoyaltyErrorHandling
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyDiscountProcessing.md
previousSectionTitle: "Reward offers processing"
nextSectionFile: apiDevGuide-apiLoyaltyLatencyRequirements.md
nextSectionTitle: "Latency requirements"
excerpt: "Your Toast POS loyalty integration interface implementation must return the following HTTPS responses to the requests that it receives from the Toast platform."
keywords: ["error", "handling", "ACCEPT", "ERROR_INVALID_TOAST_TRANSACTION_TYPE", "Toast-Transaction-Type", "ERROR_ACCOUNT_INVALID", "ERROR_INVALID_INPUT_PROPERTIES", "ERROR_TRANSACTION_DOES_NOT_EXIST", "LOYALTY_REVERSE", "ERROR_INVALID_TOKEN"]
procedures: 0
codeExamples: 0
---

Your Toast POS loyalty integration interface implementation must return the following HTTPS responses to the requests that it receives from the Toast platform.

200 means OK and has predefined success status in the response

- `ACCEPT` - The loyalty service provider processed the transaction successfully.



400 has predefined errors in the response status

- `ERROR_INVALID_TOAST_TRANSACTION_TYPE` - The requested `Toast-Transaction-Type` is not valid.


- `ERROR_ACCOUNT_INVALID` - The loyalty account is not recognized or is not valid at the current restaurant.


- `ERROR_INVALID_INPUT_PROPERTIES` - The specified JSON properties in the request body are not valid.


- `ERROR_TRANSACTION_DOES_NOT_EXIST` - The transaction that is being requested to be reversed does not exist. Only occurs on a `LOYALTY_REVERSE` transaction.


- `ERROR_INVALID_TOKEN` - The token supplied in the `Authorization` header field is invalid or cannot be validated.


- `ERROR_TRANSACTION_CANNOT_BE_REVERSED` - The specified transaction cannot be reversed. Only `LOYALTY_REDEEM` and `LOYALTY_ACCRUE`transactions can be reversed.


- `ERROR_INVALID_RESTAURANT` - The restaurant specified by the `Toast-Restaurant-External-ID` is invalid.


- `ERROR` - The request cannot be processed for a reason that is not described by any of the other error states. You can include a `message` value in the `LoyaltyTransactionResponse` object to display a custom error message string to the restaurant employee. For more information, see [Custom error messages](apiDevGuide-apiLoyaltyErrorHandling#apiLoyaltyIntegrationCustomErrorMessages).



500 unexpected error

## Custom error messages

To include a custom error message, you add a `message` value to the `LoyaltyTransactionResponse` object that you return to the Toast platform.



> **Note**
> 
> The error message you submit does not appear on the Toast POS. Submitting a custom message allows your team and the Toast team to understand error trends in logs, but servers and guests will not see this message.


**Example 10.16. LoyaltyTransactionResponse object that includes a custom error message**

```
{
  "transactionStatus": "ERROR",
  "message": "This is my helpful message about the error condition."
}
```

  
