---
title: "Authentication rate limit"
id: apiAuthenticationRateLimit
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-authenticationOmitChunkFromSearchIndex.md
parentSectionTitle: "Authentication"
previousSectionFile: apiDevGuide-apiAuthTokenRefresh.md
previousSectionTitle: "Refreshing authentication tokens"
nextSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "General Toast API information"
excerpt: "Your Toast API client must reuse authentication tokens for as long as possible before getting a new token from the Toast authentication API. Authentication tokens are typically valid for one day..."
keywords: ["expires_in", ""expires_in": 3599"]
procedures: 0
codeExamples: 0
---

### Authentication rate limit

Your Toast API client must reuse authentication tokens for as long as possible before getting a new token from the Toast authentication API. Authentication tokens are typically valid for one day after they are initially issued.

Try to request no more than one or two authentication tokens per day.

**Do not request a new authentication token more than twice in a one-hour period.** Make sure that you implement client software in a way that reuses authentication tokens for at least 30 minutes.



> **Note**
> 
> Your Toast API client software *must* be prepared to reuse authentication tokens and conform to the authentication rate limit.
> The current Toast authentication API enforces the [Toast global rate limit](apiRateLimiting.html#apiToastRateLimits) by IP address on requests for authentication tokens. Future versions of the authentication API may enforce the limit on the number of requests.
> If the Toast team determines that you are requesting an unreasonably high number of authentication tokens per hour, the Toast integrations team reserves the right to terminate API access until you can decrease your volume of requests for authentication tokens.


The length of time that an authentication token is valid depends on the Toast API environment you are using. The `expires_in` value in the JSON return data from the user management API indicates the length of time, in seconds, that the token is valid. For example, if the return data for an authentication token request includes the value `"expires_in":
  3599` you can reuse the authentication token for approximately one hour. For more information about the return data from the user management system, see [Getting an authentication token](authentication.html#getting-authentication-token).

