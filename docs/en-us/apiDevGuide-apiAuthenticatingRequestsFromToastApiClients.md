---
title: "Authenticating outbound API requests"
id: apiAuthenticatingRequestsFromToastApiClients
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalOutboundApiOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Outbound API overview"
previousSectionFile: apiDevGuide-apiUsingToastOutboundApis.md
previousSectionTitle: "Using Toast outbound APIs"
nextSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
nextSectionTitle: "Gift Card Integrations"
excerpt: "Your Toast outbound API integration can verify the authenticity of the REST API requests you receive from the Toast platform. When you implement a Toast outbound API integration, the Toast platform..."
procedures: 0
codeExamples: 0
---

### Authenticating outbound API requests

Your Toast outbound API integration can verify the authenticity of the REST API requests you receive from the Toast platform. When you implement [a Toast outbound API integration](apiUsingToastOutboundApis.html), the Toast platform sends REST requests to your server. To maintain security of your integration, you must verify that each request was sent from the Toast platform client.

#### About the outbound API authentication process

When you implement an integration with a Toast outbound API, you supply a static API key string that the Toast API client will include in the HTTP `Authorization` header field with each request. You can define any static API key that meets the authentication requirements of your integration. You provide the key string to the Toast integrations support team when you configure your integration. For more information about static API keys, see [Using static API keys](apiAuthenticatingRequestsFromToastApiClients.html#apiUsingStaticApiKeys).

The following diagram shows a Toast platform API client presenting the static API key string that you supply in the HTTP `Authorization` header field for an API request.

![A diagram showing an organization's Toast outbound API implementation providing a static API key to Toast. The Toast platform includes that static API key in the authentication header parameter for each API request.](https://doc.toasttab.com/doc/media/toast-outbound-api-authentication.png)

#### HTTP Authorization header field example

The following example shows the HTTP `Authorization`header field for a Toast platform API client request.

**Example 10.1. HTTP `Authorization` header field for a Toast platform API client request**

```
Authorization: c75a2aa085d30a90308841d388fc7828f1a28e29bdd2c82150a30cf356d4d87f
```



(1) The string value of the HTTP header Authorizationfield is the static API key that you supply to Toast when you implement your integration. For more information, see Using static API keys.

  
#### Using static API keys

You provide the static API key that a Toast platform API client includes in the HTTP header `Authorization` field. You can choose the static API key content to meet the requirements of the authentication implementation in your Toast API integration.

The maximum length of a static API key is 255 characters.

When you have the static API key string that your integration will use to authenticate Toast platform API client requests, you contact the Toast integrations team to securely transfer the key string.

Your authentication implementation should use different static API keys for the product and sandbox environments of the Toast platform. Using different static API keys ensures that requests meant for integration testing in the sandbox environment cannot affect the live restaurant operations in the production environment. For more information, see [Environments](apiEnvironments.html).

#### Rotating static API keys

To revoke and replace the static API key that a Toast platform API client includes in the HTTP header `Authorization` field you contact the Toast integrations team to coordinate a key rotation for your integration. The Toast integrations team can replace an existing static API key for your integration with a new static API key. Your integration must perform a coordinated replacement of the authentication configuration that you use to evaluate the authenticity of Toast API requests.



> **Note**
> 
> If your integration and the Toast API client configuration are not coordinated when you rotate static API keys, API requests for your integration will fail. Make sure you coordinate static API key rotation with the Toast integrations team.


