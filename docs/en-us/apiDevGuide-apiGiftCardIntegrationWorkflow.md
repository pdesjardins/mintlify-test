---
title: "Gift card integration workflow"
id: apiGiftCardIntegrationWorkflow
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Gift Card Integrations"
previousSectionFile: apiDevGuide-apiGiftCardIntegrationOverview.md
previousSectionTitle: "Gift card integration overview"
nextSectionFile: apiDevGuide-apiGiftCardIntegrationAuthentication.md
nextSectionTitle: "Gift card integration authentication"
externalReferences: [https://central.toasttab.com/s/article/Cashing-Out-the-Remaining-Balance-of-a-Gift-Card]
excerpt: "The Toast platform sends requests to your..."
procedures: 0
codeExamples: 0
---

The Toast platform sends requests to your gift card API
    implementation when it processes gift card transactions at restaurants
    that use your gift card provider service. Your implementation of the gift
    card API must return information about the results of your attempt to
    process the transaction.

The following sections provide more information about the gift card
    transaction workflow in a Toast platform gift card integration.

- [Single endpoint](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationSingleEndpoint)


- [HTTP required for REST requests and responses](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationHttpsRequired)


- [Gift card transaction types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationTransactionTypes)


- [Verification Codes (PINs)](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationVerificationsCodes)


- [Response status types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationResponseTypes)


- [Multiple requests for a gift card transaction](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationMultipleRequestsForTransaction)


- [Cash out transactions](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardApiCashOutRedeem)



## Single endpoint

The Toast gift card API specification includes a single endpoint.
      The Toast platform sends information about all gift card transaction
      types to that endpoint. The information in the HTTP request indicates
      the type of transaction and provides details about it.

You can name the single endpoint of your gift card integration API
      anything that you want. For example, the REST path in the URL for your
      API might be `https://my-host-name/v1/myTransactions`. You
      define every part of that URL. During the integration process, the Toast
      integrations team will configure the REST path to your endpoint in the
      Toast platform.

The Toast platform indicates the type of each transaction request
      by including a transaction type identifier in the
      `Toast-Transaction-Type` HTTP header parameter. For
      information about gift card transaction type identifiers see [Gift card transaction types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationTransactionTypes).

The Toast platform includes a set of values that provide
      information about the gift card transaction in the JSON
      `GiftCardTransaction` object in the message body parameter
      for each request.

Your single endpoint must return a JSON
      `GiftCardTransactionResponse` object in the message body of
      the HTTP response to each request. The
      `GiftCardTransactionResponse` object indicates the success or
      failure of transaction processing and provides information about the
      state of the gift card after the transaction is processed. The
      `transactionStatus` value of the
      `GiftCardTransactionResponse` object includes a status
      identifier. For information about `transactionStatus` values,
      see [Response status types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationResponseTypes).



> **Important**
> 
> Your gift card API implementation must use HTTPS for all REST
        requests and responses.


## HTTP required for REST requests and responses

Your gift card API implementation must use HTTPS for all REST
      requests and responses. HTTPS uses Transport Layer Security (TLS) to
      encrypt and secure communications between the API client and
      server.

## Gift card transaction types

The following table describes the transaction types that the Toast
      platform sends to your gift card provider service. The Toast platform
      includes the transaction type identifier in the
      `Toast-Transaction-Type` header parameter for each gift card
      transaction API request.

| Transaction type | Description | 
| --- | --- |
| `GIFTCARD_ACTIVATE` | Activates a new gift card. For
              example, the Toast platform sends a
              `GIFTCARD_ACTIVATE` request when it handles a gift
              card sale transaction.**Optional **Your gift card implementation can either handle
                  requests with this transaction type or may return a
                  `ERROR_TOAST_TRANSACTION_TYPE_NOT_SUPPORTED`
                  response status. | 
| `GIFTCARD_ADD_VALUE` | Increases the amount of money available on a gift
              card.For example, the Toast platform sends a
              GIFTCARD_ADD_VALUE request when it handles a gift card sale
              (initial balance) or when a restaurant guest purchases
              additional value to add to a gift card balance.
              **Optional **Your gift card implementation can either handle
                  requests with this transaction type or may return a
                  `ERROR_TOAST_TRANSACTION_TYPE_NOT_SUPPORTED`
                  response status. | 
| `GIFTCARD_GET_BALANCE` | Requests the amount of money that is available for
              purchases on a gift card.For example, the Toast
              platform sends a `GIFTCARD_GET_BALANCE` request when
              a restaurant guest asks a restaurant employee to check the
              amount of money that is available.

> **Note**
> 
> In some situations, the Toast platform might send a
                  `GIFTCARD_GET_BALANCE` request to verify that a
                  gift card is not active or that it has a zero balance. For
                  example, the Toast platform might send a
                  `GIFTCARD_GET_BALANCE` request to verify that a
                  card is not already active during a gift card sale.


**Required **Your gift card implementation must handle requests
                  with this transaction type. | 
| `GIFTCARD_REDEEM` | Decreases the amount of money available on a gift
              card.For example, the Toast platform sends a
              `GIFTCARD_REDEEM` request when a restaurant guest
              makes a purchase using a gift card as a form of
              payment.If the redeem request is for a cash-out
              transaction, the `isCashOut` value of the
              `TransactionInformationRedeem` object is
              `true`. In a cash-out gift card redeem transaction,
              the guest receives cash instead of using gift card funds for a
              purchase. For more information about cash-out redeem
              transactions, see [Cash out transactions](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardApiCashOutRedeem).**Optional **Your gift card implementation can either handle
                  requests with this transaction type or may return a
                  `ERROR_TOAST_TRANSACTION_TYPE_NOT_SUPPORTED`
                  response status. | 
| `GIFTCARD_REVERSE` | Undoes a previous gift card
              transaction.For example, the Toast platform sends a
              `GIFTCARD_REVERSE` request when a restaurant employee
              voids a purchase made with a gift card.**Required **Your gift card implementation must handle requests
                  with this transaction type. | 

## Verification Codes (PINs)

All transaction types can support verification codes (also known
      as PINs). You may choose to support verification codes (PINs) for your
      Toast gift card API implementation. If you’d like to add this to your
      existing Toast gift card API implementation, reach out to the Developer
      Relations team to inquire about adding Verification Code (PIN) support
      to your Toast API implementation scope.

If a user enters a verification code, the Toast platform sends it
      as part of any of the transactions listed below. The Toast platform also
      indicates if the card number is entered via swipe, manual entry (keyed),
      or scan (1D or 2D barcode). The provider must validate the verification
      code and use the corresponding response type. If a verification code is
      not entered but is required, the provider can choose to respond with
      “ERROR_VERIFICATION_REQUIRED” to indicate the user must resubmit using a
      verification code (PIN).

## Response status types

The following table describes the response status types that your
      gift card provider service can send to the Toast platform. Your gift
      card integration API implementation returns a transaction status
      identifier in the `transactionStatus` value of the
      GiftCardTransactionResponse object.

| Transaction status | Description | 
| --- | --- |
| `ACCEPT` | The transaction was handled
              successfully. | 
| `ERROR_TOAST_TRANSACTION_TYPE_NOT_SUPPORTED` | Your implementation does not handle the optional
              transaction type that was supplied in the
              request.Return this response status type when the
              request transaction type *is one of the types
              defined* by the gift card integration API
              specification but you have decided not to support
              it. | 
| `ERROR_INVALID_TOAST_TRANSACTION_TYPE` | The transaction type identifier supplied in the
              `Toast-Transaction-Type` header parameter of the
              request is not one of the recognized transaction
              types.Return this response status type when the
              request transaction type *is not one of the types
              defined* by the gift card integration API
              specification. | 
| `ERROR_CARD_ALREADY_ACTIVATED` | The transaction attempted to activate a gift card
              that is already active. | 
| `ERROR_CARD_NOT_ACTIVATED` | The gift card is not active.

> **Note**
> 
> In some situations, the Toast platform might make a
                  transaction request to verify that a gift card is not
                  already active. In this situation, the Toast platform
                  expects to receive a `ERROR_CARD_NOT_ACTIVATED`
                  transaction status. For more information, see [Multiple requests for a gift card transaction](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationMultipleRequestsForTransaction).


 | 
| `ERROR_CARD_INVALID` | The gift card identifier is not in the set of
              identifiers that correspond to the current
              restaurant.For example, if a gift card identifier
              is entered incorrectly or if the gift card identifier
              corresponds to a different restaurant location, your
              implementation returns this status. | 
| `ERROR_INVALID_INPUT_PROPERTIES` | The values that the Toast platform supplied in the
              `GiftCardTransaction` object in the request message
              body do not match the requirements of the transaction
              type. | 
| `ERROR_TRANSACTION_DOES_NOT_EXIST` | The transaction specified by a
              `GIFTCARD_REVERSE` type request does not
              exist. | 
| `ERROR_INVALID_TOKEN` | The authentication token supplied in the
              `Authorization` header parameter is invalid or cannot
              be validated. For information about request authentication, see
              [Gift card integration authentication](apiDevGuide-apiGiftCardIntegrationAuthentication). | 
| `ERROR_TRANSACTION_CANNOT_BE_REVERSED` | The transaction specified by a
              `GIFTCARD_REVERSE` type request cannot be reversed.
              The following transaction types cannot be
              reversed:- `GIFTCARD_GET_BALANCE`
- `GIFTCARD_REVERSE`
- Transactions that have already been reversed

 | 
| `ERROR_INVALID_RESTAURANT` | The restaurant identifier included in the
              `Toast-Restaurant-External-ID` header parameter of
              the request is not recognized by the gift card provider
              integration implementation.You receive the
              identifiers for Toast platform restaurants from the Toast
              integrations team when you implement your gift card
              integration. | 
| `ERROR_VERIFICATION_FAILED` | The verification code (PIN) data specified by the
              JSON body is invalid. | 
| `ERROR_VERIFICATION_REQUIRED` | Verification code (PIN) data is necessary to
              complete the transaction but the data is missing or `null` in
              the JSON body. | 
| `ERROR_VERIFICATION_NOT_SUPPORTED` | Verification code (PIN) data is provided by the
              JSON body but the provider doesn't support verification
              code. | 

## Multiple requests for a gift card transaction

The Toast platform may send multiple requests to your gift card
      integration API implementation when it processes a gift card
      transaction.

For example, when a restaurant employee sells a new gift card to a
      guest:

- First, the Toast platform sends a balance inquiry request to
          verify that the new gift card is not already active and that it does
          not have an existing balance


- Then the Toast platform sends an activate request to add value
          and make the card usable for transactions.



The following procedures describe the sequence of integration API
      requests that the Toast platform sends to a gift card integration API
      implementation to handle common gift card transaction types.



> **Note**
> 
> The sequence of requests is described here to show the way that
        the Toast platform combines request types for a transaction. The
        specific sequence of requests is determined by the internal
        implementation of the Toast platform software. *Make sure
        that your integration API implementation does not rely on any specific
        sequence of requests. The specific sequence of requests will change
        without notice.*


**Procedure 10.1. Selling a new gift card, successful result**

1. Toast platform sends a `GIFTCARD_GET_BALANCE`
          request for the new gift card.


2. Gift card provider sends a
          `ERROR_CARD_NOT_ACTIVATED` transaction status in the
          `GiftCardTransactionResponse`.


3. Toast platform sends a `GIFTCARD_ACTIVATE` request
          for the new gift card.


4. Gift card provider sends an `ACCEPT` transaction
          status in the `GiftCardTransactionResponse`.



**Procedure 10.2. Selling a new gift card, failure**

1. Toast platform sends a `GIFTCARD_GET_BALANCE`
          request for the new gift card.


2. Gift card provider sends an `ACCEPT` transaction
          status and information about the card balance in the
          `GiftCardTransactionResponse`.


3. Toast platform reports that the gift card is already active to
          restaurant employee and takes no further action.



**Procedure 10.3. Adding value to a gift card, successful result**

1. Toast platform sends a `GIFTCARD_GET_BALANCE`
          request for the new gift card.


2. Gift card provider sends an `ACCEPT` transaction
          status and information about the card balance in the
          `GiftCardTransactionResponse`.


3. Toast platform sends a `GIFTCARD_ADD_VALUE` request
          for the new gift card.


4. Gift card provider sends an `ACCEPT` transaction
          status in the `GiftCardTransactionResponse`.



**Procedure 10.4. Adding value to a gift card, failure**

1. Toast platform sends a `GIFTCARD_GET_BALANCE`
          request for the new gift card.


2. Gift card provider sends an
          `ERROR_CARD_NOT_ACTIVATED` transaction status in the
          `GiftCardTransactionResponse`.


3. Toast platform reports that the gift card is not active to
          restaurant employee and takes no further action.



## Cash out transactions

Restaurant locations that use the Toast gift card provider
      integration can give guests cash as a gift card redeem transaction when
      applicable regulations require cash-out transactions. For example, some
      gift-card regulations require that guests can withdraw all remaining
      funds available on a gift card when the balance is below a specific
      threshold. A cash-out redeem transaction deducts funds from the gift
      card account and the guest receives the funds directly in cash. A guest
      must cash out the entire available balance of a gift card account. A
      cash out transaction leaves the gift card account with a 0.00 currency
      balance and you should update the card's balance to zero in your system.
      See [this
      article](https://central.toasttab.com/s/article/Cashing-Out-the-Remaining-Balance-of-a-Gift-Card) for more information about cash out transactions.

If a gift card redemption is a cash out, the
      `isCashOut` value on the transaction will be
      `true`. Otherwise, `isCashOut` will be
      `false`.

Some restaurant locations are subject to regulations that require
      that guests be allowed to redeem gift card balances in cash.

Restaurant locations can enable or disable cash-out transactions
      for the gift card integration. Restaurant locations can set a maximum
      currency amount for cash-out transactions. If a gift card balance is
      greater than the cash-out transaction threshold, the Toast platform does
      not allow the cash-out redeem transaction.

