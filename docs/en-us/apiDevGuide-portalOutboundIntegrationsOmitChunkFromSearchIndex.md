---
title: "Chapter 10. Outbound integrations"
id: portalOutboundIntegrationsOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiStockWebhook.md
previousSectionTitle: "Stock webhook"
nextSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
nextSectionTitle: "Gift Card Integrations"
procedures: 0
codeExamples: 0
---

# Chapter 10. Outbound integrations

## Outbound API overview

### Using Toast outbound APIs

You can use Toast outbound APIs to integrate restaurant services with the Toast platform. A Toast outbound API includes a REST API server specification that your organization implements and maintains. In a Toast outbound API integration, the Toast platform acts as the API client, and sends HTTP requests to your organization's API server. For example, the Toast platform might send API requests to your organization's outbound API server during a Toast POS app workflow to integrate a gift card, loyalty program, or other restaurant service.

The following diagram shows the Toast platform making HTTP requests as an API client and receiving HTTP responses from the API server that your organization implements.

![A diagram showing the Toast platform making HTTP requests as an API client and receiving HTTP responses from your organization's API server.](https://doc.toasttab.com/doc/media/toast-outbound-apis.png)

A Toast outbound API is similar to a webhook in that the Toast platform sends HTTP messages to your organization to communicate about specific Toast platform events. Toast outbound APIs include richer information about Toast platform operations than a webhook and directly interact with your organization's API implementation based on its HTTP responses in a way that is more dynamic than webhooks. For information about Toast platform webhooks, see [Webhook basics](portalWebhooksOmitChunkFromSearchIndex.html#apiWebhookBasics).

### Authenticating outbound API requests

Your Toast outbound API integration can verify the authenticity of the REST API requests you receive from the Toast platform. When you implement [a Toast outbound API integration](portalOutboundIntegrationsOmitChunkFromSearchIndex.html#apiUsingToastOutboundApis), the Toast platform sends REST requests to your server. To maintain security of your integration, you must verify that each request was sent from the Toast platform client.

#### About the outbound API authentication process

When you implement an integration with a Toast outbound API, you supply a static API key string that the Toast API client will include in the HTTP `Authorization`header field with each request. You can define any static API key that meets the authentication requirements of your integration. You provide the key string to the Toast integrations support team when you configure your integration. For more information about static API keys, see [Using static API keys](portalOutboundIntegrationsOmitChunkFromSearchIndex.html#apiUsingStaticApiKeys).

The following diagram shows a Toast platform API client presenting the static API key string that you supply in the HTTP `Authorization`header field for an API request.

![A diagram showing an organization's Toast outbound API implementation providing a static API key to Toast. The Toast platform includes that static API key in the authentication header parameter for each API request.](https://doc.toasttab.com/doc/media/toast-outbound-api-authentication.png)

#### HTTP Authorization header field example

The following example shows the HTTP `Authorization`header field for a Toast platform API client request.

**Example 10.1. HTTP `Authorization`header field for a Toast platform API client request**

```
Authorization: c75a2aa085d30a90308841d388fc7828f1a28e29bdd2c82150a30cf356d4d87f[(1)](apiDevGuide-portalOutboundIntegrationsOmitChunkFromSearchIndex.html#d1e46506D541D-DE75-41D1-8E80-09960B9A3502-co)
```



(1) The string value of the HTTP header Authorizationfield is the static API key that you supply to Toast when you implement your integration. For more information, see Using static API keys .

  
#### Using static API keys

You provide the static API key that a Toast platform API client includes in the HTTP header `Authorization`field. You can choose the static API key content to meet the requirements of the authentication implementation in your Toast API integration.

The maximum length of a static API key is 255 characters.

When you have the static API key string that your integration will use to authenticate Toast platform API client requests, you contact the Toast integrations team to securely transfer the key string.

Your authentication implementation should use different static API keys for the product and sandbox environments of the Toast platform. Using different static API keys ensures that requests meant for integration testing in the sandbox environment cannot affect the live restaurant operations in the production environment. For more information, see [Environments](apiEnvironments.html).

#### Rotating static API keys

To revoke and replace the static API key that a Toast platform API client includes in the HTTP header `Authorization`field you contact the Toast integrations team to coordinate a key rotation for your integration. The Toast integrations team can replace an existing static API key for your integration with a new static API key. Your integration must perform a coordinated replacement of the authentication configuration that you use to evaluate the authenticity of Toast API requests.



> **Note**
> 
> If your integration and the Toast API client configuration are not coordinated when you rotate static API keys, API requests for your integration will fail. Make sure you coordinate static API key rotation with the Toast integrations team.


