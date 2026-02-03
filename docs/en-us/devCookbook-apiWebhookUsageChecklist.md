---
title: "Adding a webhook subscription"
id: apiWebhookUsageChecklist
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks"
previousSectionFile: devCookbook-cookbookWebhooksOmitChunkFromSearchIndex.md
previousSectionTitle: "Webhooks"
externalReferences: [https://hookdeck.com/guides/webhooks/why-implement-asynchronous-processing-webhooks]
excerpt: "Use these instructions to add a new webhook subscription to your Toast integration."
procedures: 0
codeExamples: 0
---

Use these instructions to add a new webhook subscription to your Toast integration.

#### Setup and planning

##### Consider how webhook events will update your system

How will your system behave when you receive a webhook event? Will you automatically update data in your system? Will you prompt for action from a user?

Before you write any code, think about how webhook events should trigger updates in your system.

##### Decide fallback API polling frequency

All Toast webhooks have a fallback API. Your integration should periodically query the fallback API in case you miss a webhook.

Before you build your webhook implementation, decide how often you will poll the corresponding fallback API. For example, the [partners API](apiPartnersGettingAccessibleRestaurants.html#apiUsingPartnersApiToGetRestaurantInfo)corresponds to the [partners webhook](apiPartnersGettingAccessibleRestaurants.html#apiGettingRestaurantAccessUpdatesFromPartnersWebhook).

Toast support recommends that you poll the partners API periodically (such as once per hour) to ensure that you receive all information in the partners domain, even if you miss a webhook.

##### Make a plan for subscription pauses and stops

If your webhook endpoint is unavailable or returns a high volume of errors, the Toast platform may pause or stop your subscription until you are able to resolve the issue. You will receive a notification email if your subscription is paused or stopped.

If your subscription is stopped, you must contact Toast support to resume your subscription.

##### Send your webhook sandbox URL and notification email to Toast

Contact Toast support and submit the URL for your webhook subscription in the sandbox environment.

When you submit your URL, also include the email address that should receive notifications if your subscription is paused or stopped.

##### Test a webhook event

To view the structure of a webhook, open the Toast POS app or Toast Web and perform the action that triggers the webhook event. The [webhook reference documentation](apiWebhooksReference.html) describes how to trigger each webhook.

After you trigger the webhook event, review the JSON your endpoint receives so that you understand the structure and content of the webhook.

#### Endpoint development

##### Build successful response submission

When you receive a webhook event that is structured correctly, submit a 2xx response before you apply any additional business logic to the event. Process events asynchronously. Providing a 2xx response before you apply the business logic allows Toast API clients to scale efficiently.

You will receive webhooks for all locations that are connected to your integration. You are responsible for submitting a 2xx response when you receive webhook events for any of these locations.

See [this page](https://hookdeck.com/guides/webhooks/why-implement-asynchronous-processing-webhooks) for more information about asynchronous webhook processing.

##### Validate idempotence using event GUIDs

If your endpoint is unable to receive a webhook event, the Toast platform may try to send the event again. If you received the original webhook and the Toast platform did not recognize that you received it, the retry may result in duplicate webhook information.

To avoid this problem, use the event GUID to ensure idempotence. If two webhooks have the same event GUID, you must treat them as the same webhook event.

For more information about webhook retries, see [Retry support](apiRetrySupport.html).

##### Validate that you send timely responses

Your endpoint should adhere to Toast webhook [timeout requirements](apiTimeouts.html) for the Toast platform to correctly understand whether or not you received the webhook.

If your webhook does not adhere to timeout requirements, you may receive unnecessary duplicate webhook events, and your subscription may become paused or stopped.

##### Review endpoint requirements

Review [this list of endpoint requirements](apiEndpointRequirements.html) to ensure that you meet all requirements before you go live in production with your webhook functionality.

##### Implement message signing

Using message signing to ensure that you only take action on webhooks that were sent by the Toast platform. Message signing provides an extra layer of security against acting upon webhooks from unknown sources.

For more information, see [Message signing](apiMessageSigning.html).

#### Going live

##### Submit production endpoint to Toast

When you are ready to take your new webhook subscription live in production, submit your production URL to your Toast contact.

Toast support recommends following [these deployment practices](apiDeployment.html) as you roll out your webhook usage, though you should still return a 200 response to all correctly-structured webhooks that you receive from Toast.

In addition to your production URL, send the following information to Toast support:

- What happens in your system when you receive a webhook?


- What is your workflow if your subscription is paused or stopped?


- Will you be using message signing?


- What feedback do you have about the webhook and its documentation?



After Toast support enables your webhook in production, you are officially live on your new webhook subscription.

