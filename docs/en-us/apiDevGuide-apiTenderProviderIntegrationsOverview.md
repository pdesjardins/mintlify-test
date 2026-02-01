---
title: "Tender provider integrations overview"
id: apiTenderProviderIntegrationsOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingATenderProviderIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Tender provider integrations"
previousSectionFile: apiDevGuide-apiBuildingATenderProviderIntegrationOmitChunkFromSearchIndex.md
previousSectionTitle: "Tender provider integrations"
nextSectionFile: apiDevGuide-apiTenderPmsIntegration.md
nextSectionTitle: "Hotel property management system integration"
externalReferences: [https://doc.toasttab.com/openapi/tender/paths/~1yourendpointname/post/]
excerpt: "You can use the Toast tender API to integrate your tender provider with the Toast platform. The tender API supports the and enables a hotel restaurant to directly bill a guest at the hotel, for..."
keywords: ["tender", "provider", "integrations", "overview", "POST", "TenderTransaction", "Toast-Transaction-Type"]
procedures: 0
codeExamples: 1
---

### Tender provider integrations overview

You can use the Toast tender API to integrate your tender provider with the Toast platform. The tender API supports the [Hotel property management system integration](apiTenderPmsIntegration.html) and enables a hotel restaurant to directly bill a guest at the hotel, for example, by using their room number or name.

In addition, the tender API allows you to apply discounts from a third-party system and refund payments and discounts on a check.

The API can be defined by:

- Transaction requests


- Transaction responses


- Error codes



Transaction types define the action to take and the related payload. Transactions between the Toast platform and the tender provider during a tender transaction are represented in the following figure.

![A diagram showing the REST HTTP request and response interactions between the Toast platform and a tender provider.](https://doc.toasttab.com/doc/media/tender_transactions1.png)

Your implementation is responsible for returning the response synchronously.

Tender integrations define a single HTTPS endpoint. In your implementation, all requests are posted to this single endpoint. Requests from restaurants configured to use your service are sent to this endpoint. For example, you can name your endpoint to be:

```
https://`toastapi.com/tenderapi`
```

Each `POST` request to the endpoint includes:

- A `TenderTransaction` object in the message body, which contains information specific to the `Toast-Transaction-Type`.


- Headers sent by the Toast platform. For a complete list of these headers, see the [API reference documentation](https://doc.toasttab.com/openapi/tender/paths/~1yourendpointname/post/).



For more information about the transaction descriptions, workflows and examples, see [Transaction descriptions](apiTenderPmsIntegration.html#apiTenderTransactionDescriptionsPMS).

#### Error handling

Your tender interface implementation must return the following HTTPS responses to the requests that it receives from the Toast platform.

200 means a successful response and has a status in the response:

- `ACCEPT`: The tender service provider processed the transaction successfully.



400 means an unsuccessful request. The `transactionStatus` value of the `TenderTransactionResponse` object indicates the source of the error. The error source must be one of the following:

- `ERROR_ACCOUNT_INVALID`: The tender identifier is not in the set of identifiers that correspond to the current restaurant. For example, if a guest account is entered incorrectly, your implementation returns this status.


- `ERROR_ACCOUNT_NO_POST`: The tender identifier provided corresponds to an account which has no card on file or has been marked as "no post".


- `ERROR_FOLIO_IN_USE`: The guest folio is in use elsewhere on the property and the guest folio is locked and unavailable for room charge posting.


- `ERROR_INSUFFICIENT_FUNDS`: The tender account does not have sufficient payment to make a payment or tip specified in a `TENDER_RETRIEVE_PAYMENTS` or `TENDER_RETRIEVE_GRATUITY`.


- `ERROR_INVALID_INPUT_PROPERTIES`: The JSON values specified in the `tenderTransaction` object in the request body do not match the requirements of the transaction type.


- `ERROR_INVALID_RESTAURANT`: The restaurant identifier included in the `Toast-Restaurant-External-ID`header parameter of the request is not recognized by the tender provider integration implementation. You receive the identifiers for your connected restaurants when implementing the tender API.


- `ERROR_INVALID_TOAST_TRANSACTION_TYPE`: Your implementation does not handle the transaction type supplied in the request. Return this response when the requested transaction type is defined by the tender API but you decided not to support it.


- `ERROR_INVALID_TOKEN`: The authentication token supplied in the `Authorization` header parameter is invalid or cannot be validated. For information about request authentication, see [Authenticating outbound API requests](apiAuthenticatingRequestsFromToastApiClients.html).


- `ERROR_TRANSACTION_CANNOT_BE_REVERSED`: The transaction specified by a `TENDER_REVERSE` request cannot be reversed.


- `ERROR_TRANSACTION_DOES_NOT_EXIST`: The reverse request, specified by a `TENDER_REVERSE`, is for a transaction that does not exist.


- `ERROR_UNABLE_TO_PROCESS`: The transaction cannot be processed by the partner. This can be due to an issue that occurred on the partner's end.



500 means there was an internal server error.

#### Latency requirements

The Toast platform expects a 500ms average response time from your tender API endpoint. The maximum response time must be five seconds, after which the Toast platform may close the socket and send another request. Response times should be as short as possible.

#### Limitations

- You cannot use the tender API to pay for checks generated using the orders API or Toast Online Ordering. The tender API is only supported through the Toast platform.


- You cannot use the tender API with contactless payment methods.



