---
title: "Building a gift card integration"
id: apiHowToGiftCard
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookGiftCardsOmitChunkFromSearchIndex.md
parentSectionTitle: "Gift cards"
previousSectionFile: devCookbook-cookbookGiftCardsOmitChunkFromSearchIndex.md
previousSectionTitle: "Gift cards"
nextSectionFile: devCookbook-cookbookLoyaltyOmitChunkFromSearchIndex.md
nextSectionTitle: "Loyalty"
externalReferences: [https://central.toasttab.com/s/article/Using-a-Gift-Card-Partner-Integration]
excerpt: "Follow the steps below to build a gift card integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build a gift card integration with the Toast platform.

This integration allows customers to use your gift card functionality in their Toast POS workflows.

## Setup

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Submit endpoint to Toast

Your gift card integration requires a [single endpoint](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationSingleEndpoint). Submit your test environment endpoint to Toast support so they can set up the endpoint in the sandbox environment.

### Review initial information

Review the [gift card integration overview](apiDevGuide-apiGiftCardIntegrationOverview) to understand the flow of information in a gift card integration.

In addition, familiarize yourself with [physical card requirements](apiDevGuide-apiPhysicalGiftCardRequirements) and [workflows that involve multiple transactions](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationMultipleRequestsForTransaction).

### Decide card vendor

If your integration will support physical gift cards, you must select a card vendor.

When restaurants purchase new physical cards, they should import the card numbers into your platform so that you recognize those card numbers when you receive gift card transactions from them.

For more information, see [Gift card requirements](apiDevGuide-apiPhysicalGiftCardRequirements).

## Success responses

### Support balance inquiries

When you receive a `GIFTCARD_GET_BALANCE` request, you should return the balance of this card and a 200 HTTP response status code.

### Develop success workflow

Review all [gift card transaction types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationTransactionTypes) and determine which of the following transaction types you will support:

- `GIFTCARD_ACTIVATE`


- `GIFTCARD_ADD_VALUE`


- `GIFTCARD_REDEEM`



Toast support recommends that you support all of these transaction types. For each transaction type that you support, develop successful responses that contain a 200 HTTP response status code and a `transactionStatus` of `ACCEPT`.

For transaction types that you do not support, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_TOAST_TRANSACTION_TYPE_NOT_SUPPORTED`.

### Develop reversal workflow

The following transactions can be reversed through a `GIFTCARD_REVERSE` request:

- `GIFTCARD_ACTIVATE`


- `GIFTCARD_ADD_VALUE`


- `GIFTCARD_REDEEM`



When you receive a `GIFTCARD_REVERSE` request, you must reverse the transaction whose `Toast-Transaction-GUID` is in the `previousTransaction` value.

### Validate endpoint idempotence

Ensure that your endpoint is idempotent using the `Toast-Transaction-GUID` header on the transactions you receive.

If two requests contain the same `Toast-Transaction-GUID`, they are the same request.

### Validate that you send timely responses

Ensure that your endpoint adheres to Toast gift card [latency requirements](apiDevGuide-apiLoyaltyLatencyRequirements). This allows the Toast platform to correctly understand how you processed the transaction in your system.

If your endpoint does not adhere to timeout requirements, guests will see an error message on the POS app that instructs them to contact your support team.

### Handle cash-out transactions

Some restaurant locations are subject to regulations that require that guests be allowed to redeem gift card balances in cash.

If the `isCashOut` value on a gift card transaction is `true`, your reports should reflect that the guest received the gift card balance in cash.

### Handle verification codes

If you plan to support verification codes (PINs) with your Toast integration, validate you send the proper responses based on your expectations for transactions that require a verification code. As an example, you may enforce that all keyed/manually typed gift cards have verification codes. If `identifierSource` is `KEYED` and `verificationCode` is `NULL`, you would return `ERROR_VERIFICATION_REQUIRED`.

## Failure responses

### Handle unknown restaurants

Your system must maintain an allowlist of restaurant GUIDs that your integration recognizes.

If the `Toast-Restaurant-External-ID` header in a gift card transaction contains a restaurant GUID that is not on your allowlist, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_INVALID_RESTAURANT`.

### Handle invalid authentication tokens

Your endpoint must validate that gift card transactions came from the Toast production environment.

If your [gift card authentication](apiDevGuide-apiGiftCardIntegrationAuthentication) process determined that a transaction came from somewhere other than the Toast production environment, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_INVALID_TOKEN`.

### Handle unknown card numbers

If you receive a gift card transaction whose `giftCardIdentifier` you do not recognize, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_CARD_INVALID`.

### Handle duplicate card activation attempts

If you receive a `GIFTCARD_ACTIVATE` transaction for a card that is already active, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_CARD_ALREADY_ACTIVATED`.

### Handle unexpected information from Toast

If you receive unexpected information from the Toast platform, your endpoint must return a 400 HTTP response status code and one of the following values for `transactionStatus`, depending on the information you receive:

- `ERROR_INVALID_TOAST_TRANSACTION_TYPE`


- `ERROR_INVALID_INPUT_PROPERTIES`


- `ERROR_TRANSACTION_DOES_NOT_EXIST`


- `ERROR_TRANSACTION_CANNOT_BE_REVERSED`


- `ERROR_VERIFICATION_FAILED`


- `ERROR_VERIFICATION_NOT_SUPPORTED`



See [Response status types](apiDevGuide-apiGiftCardIntegrationWorkflow#apiGiftCardIntegrationResponseTypes) for more information.

### Handle unexpected errors in your system

If your system has an unexpected error, your endpoint must return a 500 HTTP response status code.

## Test your integration

### Run through the test plan

Use the [gift card integration test plan](apiDevGuide-integrationTestPlans#apiIntegrationChecklistGiftCard) to validate that you correctly handle each test case.

### Load-test your endpoint

To ensure that your endpoint can handle a high volume of gift card transactions at a time, add 10+ gift cards to a POS order to ensure that your endpoint can handle this volume.

Consider any additional load-test workflows you should validate before going live.

### Review functionality with Toast team

Contact the Toast support team about walking through the test plan together.

After the Toast team confirms that your integration is ready to go live, send your production endpoint to the Toast support team.

### Plan for onboarding

Set up the allowlist of restaurant GUIDs you support and prepare a sample email for requesting new integration connections.

The Toast support team will supply you with a guide for integration enablement.

Bookmark [this Toast Central article](https://central.toasttab.com/s/article/Using-a-Gift-Card-Partner-Integration) to distribute to customers to help them understand the integration onboarding process.

## Reporting

### Build gift card reports

After you build your core gift card functionality, create reports that restaurants can use to understand gift card cash flow.

Here are some ideas for information to report on over time:



****Sales****
: - Number of gift cards sold


- Currency value of gift cards sold


- Average value of gift card sold





****Redemptions****
: - Number of gift cards fully redeemed


- Currency value of gift card redemptions





****Balances****
: - Average balance on active cards





****Escheatment****
: - Number of gift cards that expired


- Average value of expired gift cards





****Cash-outs****
: - Total currency value of cash-out transactions


- Average currency value of cash-out transactions







