---
title: "Gift card integration authentication"
id: apiGiftCardIntegrationAuthentication
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Gift Card Integrations"
previousSectionFile: apiDevGuide-apiGiftCardIntegrationWorkflow.md
previousSectionTitle: "Gift card integration workflow"
nextSectionFile: apiDevGuide-apiPhysicalGiftCardRequirements.md
nextSectionTitle: "Physical gift card requirements"
externalReferences: [https://jwt.io/]
excerpt: "You..."
keywords: ["Authorization"]
procedures: 0
codeExamples: 2
---



> **Important**
> 
> The authentication method described in this section is deprecated. The preferred authentication method for the Toast gift card API is static API key authentication. For information about using static API authentication, see [Authenticating outbound API requests](apiDevGuide-apiAuthenticatingRequestsFromToastApiClients).


You can verify that gift card transaction requests are from the Toast platform by validating the JSON Web Token (JWT) in the header of every request. Each gift card transaction request includes a JWT in the `Authorization` header field.

You can validate the JWT for a request with a public key that you get from the Toast API user management service.

You use the public key that matches the Toast environment that you are integrating with. For information about Toast API environments, see [Environments](apiDevGuide-apiEnvironments).

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

The following example shows the public key string in the JSON response from the `usermgmt/v1/oauth/token_key` endpoint. The JSON value named `value` contains the public key string. The key string in this example is not functional.

**Example 10.2. Example public key for partner API authentication**


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



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e581CC3353FE-F616-4AA1-97F1-00D3437AB330" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">/oauth/token_key</code> endpoint returns a JSON object that contains multiple values. One of the values provides the public key string.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e583CC3353FE-F616-4AA1-97F1-00D3437AB330" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">alg</code> value indicates the encryption algorithm used for the public key.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e585CC3353FE-F616-4AA1-97F1-00D3437AB330" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">value</code> value includes the public key string. You can use the string supplied in the <code className="font-mono text-sm">value</code> value to validate the authentication tokens in a Toast platform gift card transaction request.</p></div></td>
    </tr>
  
## Using the public key to validate JWTs

You can validate JSON Web Tokens (JWTs) using several libraries for common programming languages. For more information about working with JWTs, see [https://jwt.io/](https://jwt.io/). The JWT web site also includes a tool that you can use to verify a token manually.

## Refreshing the public key

Typically, the Toast integrations team does not change the key pair used to sign JWTs. You can cache the public key that you get from the Toast API user management service. You do not need to get a new copy of the public key every time you verify an incoming request.

To maintain security, the Toast integrations team may replace the key pair at any time. When the key pair changes, you must get a new public key from the user management service.

To make your integration more flexible when the Toast integrations team replaces the key pair, get and cache a new copy of the public key each time you start your service. When the Toast integrations team replaces the key pair, you can stop and restart your service to refresh the public key.

