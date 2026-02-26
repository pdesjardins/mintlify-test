---
title: "Loyalty integration authentication"
id: apiLoyaltyIntegrationAuthentication
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyIntegrationNetworkFailureAndIdempotence.md
previousSectionTitle: "Network failure and idempotence"
nextSectionFile: apiDevGuide-apiBuildingATenderProviderIntegrationOmitChunkFromSearchIndex.md
nextSectionTitle: "Tender provider integrations"
externalReferences: [https://jwt.io/]
excerpt: "You can verify..."
keywords: ["Authorization"]
procedures: 0
codeExamples: 2
---



> **Important**
> 
> The authentication method described in this section is deprecated. The preferred authentication method for the Toast loyalty API is static API key authentication. For information about using static API authentication, see [Authenticating outbound API requests](docs/en-us/apiDevGuide-apiAuthenticatingRequestsFromToastApiClients).


You can verify that loyalty transaction requests are from the Toast platform by validating the JSON Web Token (JWT) in the header of every request. Each loyalty transaction request includes a JWT in the `Authorization` header field.

You can validate the JWT for a request with a public key that you get from the Toast API user management service.

You use the public key that matches the Toast environment that you are integrating with. For information about Toast API environments, see [Environments](docs/en-us/apiDevGuide-apiEnvironments).

- For the production environment (real transactions) send a `GET` request to the following endpoint.


```
https://`[toast-production-api-hostname]`/usermgmt/v1/oauth/token_key
```


- For the sandbox environment (testing transactions) send a `GET` request to the following endpoint.


```
https://`[toast-sandbox-api-hostname]`/usermgmt/v1/oauth/token_key
```





> **Note**
> 
> The Toast integrations team supplies the host names for Toast API environments during your integration process.


## Public keys

A Toast public key for partner API authentication is an X.509 Public Key encoded in DER in PEM format.

The following example shows the public key string in the JSON response from the `/usermgmt/v1/oauth/token_key` endpoint. The JSON value named `value` contains the public key string. The key string in this example is not functional.

**Example 10.17. Example Public Key for Partner API Authentication**


```
{
   "alg":"SHA256withRSA",
   "value":"-----BEGIN PUBLIC KEY-----\nnub\nvwIDAhqhkiG9w0BAQEJ9tKko/3jXqdzI/NO4n
sAt0WZjpyovan2xPIkCv2z\nuaBBVUrOiJ6JeoJ9tKko/3jXqdzI/NO4nsLW5wq5UrPXsvbdXLZzMhu3b3
sNmFJ9tKko/3jX5AEBaf5vXZCOfBVFnWnhLX61/KkI2dxwhS7fkxnjQ8wlfrh4tp3fKjDkI\nMgxTk1teh
fWY0O3mKyKtnYvqvDSRvsZ03URzyEPddVYDYZjpyovan2xPypKRvBlxz\nxhM74p8dOhEp6zAh4pENVNyp
o+xVj/7Ko9Ie3fKjDkI\nMgxTk1tehCcNP1G/8UK\nE6oPta6r3e1Fi77K\nE6oPta66HP5KCur3mf3jQ6
Qc99xVQ8wlfrh4tp56yjRnub\nvwIDAQAB\n-----END PUBLIC KEY-----\n"
}
```



(1) The /oauth/token_key endpoint returns a JSON object that contains multiple values. One of the values provides the public key string.

(2) The alg value indicates the encryption algorithm used for the public key.

(3) The value value includes the public key string. You can use the string supplied in the value value to validate the authentication tokens in a Toast platform loyalty transaction request.

  
## Using the public key to validate JWTs

You can validate JSON Web Tokens (JWTs) using several libraries for common programming languages. For more information about working with JWTs, see [https://jwt.io/](https://jwt.io/). The JWT web site also includes a tool that you can use to verify a token manually.

## Refreshing the public key

Typically, the Toast integrations team does not change the key pair used to sign JWTs. You can cache the public key that you get from the Toast API user management service. You do not need to get a new copy of the public key every time you verify an incoming request.

To maintain security, the Toast integrations team may replace the key pair at any time. When the key pair changes, you must get a new public key from the user management service.

To make your integration more flexible when the Toast integrations team replaces the key pair, get and cache a new copy of the public key each time you start your service. When the Toast integrations team replaces the key pair, you can stop and restart your service to refresh the public key.

