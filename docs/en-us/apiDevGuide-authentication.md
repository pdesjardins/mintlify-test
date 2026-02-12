---
title: "Authentication and restaurant access"
id: authentication
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-authenticationOmitChunkFromSearchIndex.md
parentSectionTitle: "Authentication"
previousSectionFile: apiDevGuide-authenticationOmitChunkFromSearchIndex.md
previousSectionTitle: "Authentication"
nextSectionFile: apiDevGuide-apiAuthTokenRefresh.md
nextSectionTitle: "Refreshing authentication tokens"
externalReferences: [https://tools.ietf.org/html/rfc6749, https://curl.haxx.se/]
excerpt: "Toast..."
procedures: 0
codeExamples: 0
---

Toast APIs use the [OAuth 2](https://tools.ietf.org/html/rfc6749)client-credentials grant type to authenticate access to secure resources. When you send requests to secure API resources, you include an OAuth 2 bearer authentication token in the Authorization HTTP header field of your request.



> **Note**
> 
> The authentication endpoint and procedure described here replaced an earlier Toast API authentication service. If your integration uses the legacy authentication endpoint, you must implement support for the authentication process described here. For information about the legacy authentication endpoint and process, see [Legacy API authentication (deprecated)](apiDevGuide-apiDeprecatedApiFunctions#apiLegacyAuthentication).


## About authentication tokens

An authentication token is an encoded text string that you can get from the authentication API (`/authentication`). To request an authentication token, you send the client identifier and client secret in the message body of a `POST` request to the `/authentication/login` endpoint of the authentication API (`/authentication/v1/authentication/login`).

Authentication tokens are valid for a limited period of time. The length of time is determined by the Toast API environment that you use. When it returns the token, the authentication API response specifies how long an authentication token is valid. After an authentication token expires, you must get a new token from the authentication API.

## Getting API credentials

Before you can authenticate, you need API credentials. The way you get credentials depends on your integration access type. Credentials include a `clientId` and `clientSecret`. The table below shows how credentials are issued for each integration type. For more information, see [Integration types](apiDevGuide-apiIntegrationTypes).

| Integration Type | Credentials | 
| --- | --- |
| Partner integrations | Credentials are created by the Toast integrations team after your application has been reviewed and approved. For more information see, [Integration partnership process](apiDevGuide-integrationDevProcess). | 
| Custom integrations | Credentials are created by the Toast integrations team after you have been approved for custom integration access. For more information see, [Custom integration overview](apiDevGuide-apiCustomIntegrationOverview). | 
| Standard API access | You create your own credentials through Toast Web. For more information, see [Creating standard API access credentials](apiDevGuide-devApiAccessCredentials#devApiAccessCreatingCredentials). | 
| Analytics API access | You create your own credentials through Toast Web. For more information, see [Creating analytics API access credentials](apiDevGuide-apiAnalyticsAccessCreatingCredentials). | 

## Credential storage guidelines

API credentials provide access to valuable and sensitive information and must be saved in a secure way. If your API credentials are exposed, the Toast integrations team deactivates the compromised credentials and generates new ones.

To decrease the likelihood of exposing your API credentials, follow these guidelines for your production and sandbox API credentials.

### Do this

It is best to do the following things:

- Save your API credentials as environment variables. If your team needs local access to credential strings, share them using a secret management service and store them in local environment variables.


- Programmatically retrieve your API credentials at runtime from a secret management service. This allows you to rotate credentials without the need to update environment variables.


- When possible, visually mask your client secret to decrease the likelihood of displaying the secret when you use a screen-sharing service or when other people can see your computer display.



### Don't do this

It is best *not* to do the following things:

- Do not store API credentials in your Toast integration code.


- Do not store API credentials in any repositories saved to the cloud, whether public or private.


- Do not display your client secret while using a screen-sharing service.


- Do not send an unencrypted client secret via email or in a messenger application.



### Indicators of credential compromise

If any of the following things occurs, your API credentials are considered compromised. Contact Toast support immediately so that you can receive a new client secret.

- Your client secret is committed to a repository that is not a purpose-built secret management service.


- Your client secret is deployed in your code.


- Somebody sends your client secret in plain text via email or on a messenger application.


- Your client secret is displayed on a screen-share recording that is saved to the cloud.


- You have any other known or suspected security breach.



## Getting an authentication token

### Making the request

To get an authentication token, you send a `POST` request to the `/authentication/login` endpoint of the Toast authentication API. The following example shows the URL of the endpoint.

```
https://`[toast-api-hostname]`/authentication/v1/authentication/login
```

You must include your client identifier and client secret string in the message body of a `POST` request for an authentication token. You receive a client identifier string (*`clientId`*) and client secret string (*`clientSecret`*) from the Toast support team. Follow [these guidelines](apiDevGuide-authentication#apiAuthTokenStorage) when storing your API credentials.

When the authentication API determines that the client identifier and client secret string are valid, it returns an authentication token along with a set of data describing the way you can use it. For more information, see [Toast API accounts](apiDevGuide-apiClientAccounts).

You include the following JSON object in the message body parameter of an `/authentication/login` endpoint request.

**Example 1.3. Message body parameter for an `/authentication/login` endpoint request**

```
myToastApiClientSecret
```



(1) The identifier string for your Toast API client.

(2) The secret string that corresponds to your Toast API client.

(3) Always include the userAccessType value and set it to TOAST_MACHINE_CLIENT.

  
The following **curl** command requests an authentication token from the `/authentication/login` resource. For more information about the curl utility, see [https://curl.haxx.se/](https://curl.haxx.se/).

**Example 1.4. Authentication request using curl program command**

```
curl -X POST \
-H "Content-Type: application/json" \
-d @`file-containing-message-body-parameter.json` \
https://`[toast-api-hostname]`/authentication/v1/authentication/login

```



(1) Use the POST HTTP method to make an authentication request.

(2) Include the HTTP Content-Type header field and set its value to application/json.

(3) Include a JSON object including your client identifier and client secret in the message body parameter. See Example 1.3, “Message body parameter for an /authentication/login endpoint request”.

(4) Send the request to the /authentication/loginendpoint of the authentication API.

  
### Authentication return data

The return data that you receive depends on the type of Toast API client you are using. Toast APIs support partner clients and restaurant management group clients. For more information about the types of Toast API clients, see [Toast API accounts](apiDevGuide-apiClientAccounts).

#### Authentication return data for a partner API client

The authentication API returns the information shown in the following example for a successful authentication request using a partner API client. For more information about partner API accounts, see [Toast API accounts](apiDevGuide-apiClientAccounts).

**Example 1.5. Authentication return data for a partner API client**

```
\{
  "@class": ".SuccessfulResponse",
  "token": \{
    "tokenType": "Bearer",
    "scope": null, 
    "expiresIn": 19168,
    "accessToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwYXJ0bmVyR3
      V3JkZXJzOnYThkYWE5LWIyMDQtNDhhZi1iZDY2LWZiMzZkNzViYjU1NiIsIm5hbWl
      uZ0F1dGhvcml05NiIGlBFVEVSUEFSVE5FUiIsImF6cCI6InBldGVyLXBhcnRuZXIi
      LCJzY29wZSI6WyJjcm0iLCJsYWJvciIsImNvbmZpZ3VyYXRpb24iLCJjYXNobWdtd
      CIsInBhcnRuZXJzIiwiZ3Vlc3QucGk6cmVhZCIsImRlbGlcml05X2luZm8uYWRkcm
      VzczpyZWFkIiwib3JkZXJzO5NiIGQiLCJvcmRlcnMub3JkZXJzOndyaXRlIiwib3J
      kZXJzIiwiY3JlZGl0X2NhcmRzLmF1dGhvcml6YXRpb2463JkZXJzOnSwiZXhwIjox
      NTg4MTc2NDY2LCJqdGkiOiIyMTk4OWQwNS1jNzg4LTQzNWYtODQyMi0xYjRjZTM5O
      DdlODgiLCJjbGllbnRfaWQiOiJwZXRlci1wYXJ0bmVyIn0.BxROzc5ZyKVgkdsLTF
      LbyPR_dt5NiIG8vtJd3JkZXJzOnOQiJRtfx6sfse1i2ZG6VWIz_jVOvOiR2zaWra0
      yCcml051AVNV3xxn7u4finETPzm43lhf5NiIGYKqUD_HM-Z1B-CCAj-7C6nOGQWI9
      G_PYZRsb7lwmJG3tPW74bDKZhYJVnPO3HMNnd93A8AL4QVOVBO6L6BdqsK3lZ7nzY
      0hALk-LzyD-w_maz-s2kFx7vbWrp0l2X_gSpEi3JkZXJzOn81T-2bBtz4vkObQm27
      iI0Ww8K2ZeRwkSaR8zL2Qo-5NiIGRcml059S1_halz_GuWy4xOctS5WZOuIe5FaA",
    "idToken": null,
    "refreshToken": null
  \},
  "status": "SUCCESS"
\}

```



 For internal use.

 The OAuth 2 authentication scheme used for the authentication token. Toast API authentication uses the bearer authentication scheme.

 The scope value in your authentication token request response will be null. Your JSON Web Token (JWT) contains your list of scopes.

 The number of remaining seconds that the authentication token is valid. For more information, see Refreshing authentication tokens.

 A JSON Web Token (JWT) string that contains an authentication token. You present this string when you make requests to other Toast API resources. The JWT includes information about your Toast API client. For more information, see Example 1.6, “JWT payload contents for partner API client access token”.

 For internal use.

 For internal use.

 Indicates that your authentication request was successful.

  
The following example shows the JWT payload contents for a partner API client access token.

**Example 1.6. JWT payload contents for partner API client access token**

```
\{
  "https://toasttab.com/client_name": "`MYNAMINGAUTHORITY`",
  "https://toasttab.com/access_type": "TOAST_MACHINE_CLIENT",
  "https://toasttab.com/partner_guid": "23a8eca9-b403-45bf-cd66-fb36a85be556",
  "https://toasttab.com/type": "CUSTOMER",
  "iss": "[Toast-token-issuer]",
  "sub": "`my-client-id`@clients",
  "aud": "https://toast-services-api/",
  "iat": 1603107025,
  "exp": 1588176466,
  "azp": "`my-client-id`",
  "scope": "orders:read menus:read",
  "gty": "client-credentials"
\}
```



(1) A human-readable name representing your API client.

(2) The types of users that can authenticate through the system. For API clients, this is TOAST_MACHINE_CLIENT. TOAST_MACHINE_CLIENT represents the type of access credentials issued to services that use Toast APIs. 

(3) The unique Toast platform identifier for the integration partner organization.

(4) The type of client requesting authentication. For partner API clients, this is PARTNER. 

(5) The issuer of the authentication token.

(6) The subject of the token being issued. This value will be set to your client identifier and the string @clients.

(7) The intended audience of your API usage.

(8) A standard JWT claim indicating the time that the authentication token was issued. The time is presented in UNIX epoch format.

(9) A standard JWT claim indicating the time that the authentication token expires. The time is presented in UNIX epoch format.

(10) A standard JWT claim containing the identifier for the Toast API client.

(11) The API functionality that your client ID is provisioned to use. For more information about API scopes, see API scopes page.

(12) The grant type of this API client. This value will be client-credentials.

  
#### Authentication return data for a restaurant management group API client

The authentication API returns the information shown in the following example for a successful authentication request using a restaurant management group API client. For more information about restaurant management group API accounts, see [Toast API accounts](apiDevGuide-apiClientAccounts).

**Example 1.7. Authentication return data for a restaurant management group client**

```
\{
  "@class": ".SuccessfulResponse",
  "token": \{
    "tokenType": "Bearer",
    "scope": null, 
    "expiresIn": 19168,
    "accessToken": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwYXJ0bmVyR3
      V3JkZXJzOnYThkYWE5LWIyMDQtNDhhZi1iZDY2LWZiMzZkNzViYjU1NiIsIm5hbWl
      uZ0F1dGhvcml05NiIGlBFVEVSUEFSVE5FUiIsImF6cCI6InBldGVyLXBhcnRuZXIi
      LCJzY29wZSI6WyJjcm0iLCJsYWJvciIsImNvbmZpZ3VyYXRpb24iLCJjYXNobWdtd
      CIsInBhcnRuZXJzIiwiZ3Vlc3QucGk6cmVhZCIsImRlbGlcml05X2luZm8uYWRkcm
      VzczpyZWFkIiwib3JkZXJzO5NiIGQiLCJvcmRlcnMub3JkZXJzOndyaXRlIiwib3J
      kZXJzIiwiY3JlZGl0X2NhcmRzLmF1dGhvcml6YXRpb2463JkZXJzOnSwiZXhwIjox
      NTg4MTc2NDY2LCJqdGkiOiIyMTk4OWQwNS1jNzg4LTQzNWYtODQyMi0xYjRjZTM5O
      DdlODgiLCJjbGllbnRfaWQiOiJwZXRlci1wYXJ0bmVyIn0.BxROzc5ZyKVgkdsLTF
      LbyPR_dt5NiIG8vtJd3JkZXJzOnOQiJRtfx6sfse1i2ZG6VWIz_jVOvOiR2zaWra0
      yCcml051AVNV3xxn7u4finETPzm43lhf5NiIGYKqUD_HM-Z1B-CCAj-7C6nOGQWI9
      G_PYZRsb7lwmJG3tPW74bDKZhYJVnPO3HMNnd93A8AL4QVOVBO6L6BdqsK3lZ7nzY
      0hALk-LzyD-w_maz-s2kFx7vbWrp0l2X_gSpEi3JkZXJzOn81T-2bBtz4vkObQm27
      iI0Ww8K2ZeRwkSaR8zL2Qo-5NiIGRcml059S1_halz_GuWy4xOctS5WZOuIe5FaA",
    "idToken": null,
    "refreshToken": null
  \},
  "status": "SUCCESS"
\}

```



(1) For internal use.

(2) The OAuth 2 authentication scheme used for the authentication token. Toast API authentication uses the bearer authentication scheme.

(3) The scope value in your authentication token request response will be null. Your JSON Web Token (JWT) contains your list of scopes.

(4) The number of remaining seconds that the authentication token is valid. For more information, see Refreshing authentication tokens.

(5) A JSON Web Token (JWT) string that contains an authentication token. You present this string when you make requests to other Toast API resources. The JWT includes information about your Toast API client. For more information, see Example 1.8, “JWT payload contents for restaurant management group API client access token”.

(6) For internal use.

(7) For internal use.

(8) Indicates that your authentication request was successful.

  
The following example shows the JWT payload contents for a restaurant management group API client access token.

**Example 1.8. JWT payload contents for restaurant management group API client access token**

```
\{
  "https://toasttab.com/client_name": "`MYNAMINGAUTHORITY`",
  "https://toasttab.com/access_type": "TOAST_MACHINE_CLIENT",
  "https://toasttab.com/management_set_guid": "0423ad35-8ba2-45cf-9b6b-7da03f982c46",
  "https://toasttab.com/type": "CUSTOMER",
  "iss": "[Toast-token-issuer]",
  "sub": "`my-client-id`@clients",
  "aud": "https://toast-services-api/",
  "iat": 1603107025,
  "exp": 1588176466,
  "azp": "`my-client-id`",
  "scope": "orders:read menus:read",
  "gty": "client-credentials"
\}
```



(1) A human-readable name representing your API client.

(2) The types of users that can authenticate through the system. For API clients, this is TOAST_MACHINE_CLIENT. TOAST_MACHINE_CLIENT represents the type of access credentials issued to services that use Toast APIs. 

(3) The unique Toast platform identifier for the restaurant management group this client can access.

(4) The type of client requesting authentication. For restaurant management group API clients, this is CUSTOMER. 

(5) The issuer of the authentication token.

(6) The subject of the token being issued. This value will be set to your client identifier and the string @clients.

(7) The intended audience of your API usage.

(8) A standard JWT claim indicating the time that the authentication token was issued. The time is presented in UNIX epoch format.

(9) A standard JWT claim indicating the time that the authentication token expires. The time is presented in UNIX epoch format.

(10) A standard JWT claim containing the identifier for the Toast API client.

(11) The API functionality that your client ID is provisioned to use. For more information about API scopes, see the API scopes page.

(12) The grant type of this API client. This value will be client-credentials.

  
## Using an authentication token

To use secured Toast API resources, when you make a request you:

- Present a valid authentication token in the *`Authorization`* HTTP header field when you make a request. An authentication token is a text string that you can get from the `/authentication/login` endpoint of the authentication API. See [Getting an authentication token](apiDevGuide-authentication#getting-authentication-token).

The Toast API uses bearer authentication tokens. You must include the string `Bearer` in the value of the *`Authorization`* HTTP header field, before the token string, to indicate the type of the token. For example, `Authorization: Bearer
        [<em>my-authentication-token</em>]`.


- Specify the individual restaurant context for your request in the *`Toast-Restaurant-External-ID`* header field.

To specify the restaurant that is the subject of a Toast API request, you include the Toast system GUID for that restaurant in the *`Toast-Restaurant-External-ID`* HTTP header field. For example, `Toast-Restaurant-External-ID:
        47286e0a4-4fef-9230-b3dae11e7a9`.



The following **curl** command presents an authentication token when it makes a Toast API request.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQLCJqdLWFlODItNGFlYy04ND
M1LLCJqdRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedLCJqdK9ghNZVCs28
Td2Sp3IxLCJqdbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GLCJqdlryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4721e7a9-b4ae-4fef-9230-b3dae186e0a4" \
https://`[toast-api-hostname]`/labor/v1/employees

```

