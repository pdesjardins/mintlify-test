---
title: "Loyalty"
id: cookbookLoyaltyOmitChunkFromSearchIndex
type: section
documentId: devCookbook
parentSectionFile: devCookbook-devPortalCookbookHowToOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 1. Recipes"
previousSectionFile: devCookbook-cookbookGiftCardsOmitChunkFromSearchIndex.md
previousSectionTitle: "Gift cards"
nextSectionFile: devCookbook-cookbookOrderingOmitChunkFromSearchIndex.md
nextSectionTitle: "Ordering"
externalReferences: [https://central.toasttab.com/s/article/Using-a-Gift-Card-Partner-Integration]
procedures: 0
codeExamples: 0
---

### Building a loyalty integration

Follow the steps below to build a loyalty integration with the Toast platform, which allows customers to use your loyalty functionality in their Toast POS workflows.

#### Setup

##### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devPortalCookbookHowToOmitChunkFromSearchIndex.html#apiIntegrationChecklistGeneral).

##### Submit endpoint to Toast

Your loyalty integration requires a [single endpoint](apiLoyaltyIntegrationOverview.html). Submit your test environment endpoint to Toast support so that they can set up the endpoint in the Toast sandbox environment.

##### Review initial information

First, review the [loyalty integration overview](apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.html#apiLoyaltyProgramIntegrationOverview) and [POS workflow](apiLoyaltyPosWorkflow.html) to understand the flow of information in a loyalty integration.

##### Decide discount types you will support

Familiarize yourself with [reward processing information](apiLoyaltyDiscountProcessing.html).

Decide whether you will support check-level discounts, item-level discounts, or both.

##### Perform an initial test

If your integration supports item-level discounts, you must use the [menus API](portalApiGettingMenusOmitChunkFromSearchIndex.html#apiGettingMenuInformationFromTheMenusAPI)to save menu information so that restaurant administrators can map discounts from your service to menu items in the Toast platform.

##### Decide loyalty identifier structure

Your integration needs to assign a `loyaltyIdentifier`for each loyalty account in your system.

Decide the format of this identifier, such as a UUID.

Loyalty identifiers cannot contain personal information such as email addresses or phone numbers.

#### Success responses

##### Develop success workflow

Review all [loyalty transaction types](apiLoyaltyTransactionDescriptions.html).

For all transaction types, develop successful responses that contain a 200 HTTP response status code and a `transactionStatus` of `ACCEPT`.

##### Validate that you send timely responses

Ensure that your endpoint adheres to Toast loyalty [latency requirements](apiLoyaltyLatencyRequirements.html). This allows the Toast platform to correctly understand how you processed the transaction in your system.

If your endpoint does not adhere to timeout requirements, guests will see an error message on the POS that instructs them to contact your support team.

##### Handle transactions without loyalty identifiers

The `loyaltyIdentifier` value may be null on `LOYALTY_ACCRUE` and `LOYALTY_REVERSE`requests.

If the `loyaltyIdentifier` on these transactions is null and the transaction is otherwise structured correctly, your endpoint must return a 200 HTTP response status code and a `transactionStatus` of `ACCEPT`.

##### Validate endpoint idempotence

Ensure that your endpoint is idempotent using the `Toast-Transaction-GUID` header on the transactions you receive.

If two requests contain the same `Toast-Transaction-GUID`, they are the same request.

See [Network failure and idempotence](apiLoyaltyIntegrationNetworkFailureAndIdempotence.html) for more information about transaction retries and idempotence.

#### Failure responses

##### Handle unknown restaurants

Your system must maintain an allowlist of restaurant GUIDs that your integration recognizes.

If the `Toast-Restaurant-External-ID` header in a loyalty transaction contains a restaurant GUID that is not on your allowlist, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_INVALID_RESTAURANT`.

##### Handle invalid authentication tokens

Your endpoint must validate that loyalty transactions came from the Toast production environment.

If your [loyalty authentication](apiLoyaltyIntegrationAuthentication.html) process determined that a transaction came from somewhere other than the Toast production environment, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_INVALID_TOKEN`.

##### Handle unknown loyalty accounts

If you receive a loyalty transaction whose `loyaltyIdentifier` you do not recognize, your endpoint must return a 400 HTTP response status code and a `transactionStatus` of `ERROR_ACCOUNT_INVALID`.

##### Handle unexpected information from Toast

If you receive unexpected information from the Toast platform, your endpoint must return a 400 HTTP response status code and one of the following values for `transactionStatus`, depending on the information you receive:

- `ERROR_INVALID_TOAST_TRANSACTION_TYPE`


- `ERROR_INVALID_INPUT_PROPERTIES`


- `ERROR_TRANSACTION_DOES_NOT_EXIST`


- `ERROR_TRANSACTION_CANNOT_BE_REVERSED`



See [Error handling](apiLoyaltyErrorHandling.html) for more information.

##### Handle unexpected errors in your system

If your system has an unexpected error, your endpoint must return a 500 HTTP response status code and a `transactionStatus` of `ERROR`.

If you send a `message` in your response, not return any guest personal information in the message.

#### Test your integration

##### Run through the test plan

Use the [loyalty integration test plan](integrationTestPlans.html#apiIntegrationChecklistLoyalty) to validate that you correctly handle each test case.

##### Review functionality with Toast team

Contact the Toast support team about walking through the test plan together.

After the Toast team confirms that your integration is ready to go live, send your production endpoint to the Toast support team.

##### Plan for onboarding

Set up the allowlist of restaurant GUIDs you support and prepare a sample email for requesting new integration connections.

The Toast support team will supply you with a guide for integration enablement.

Bookmark [this Toast Central article](https://central.toasttab.com/s/article/Using-a-Gift-Card-Partner-Integration) to distribute to customers to help them understand the integration onboarding process.

