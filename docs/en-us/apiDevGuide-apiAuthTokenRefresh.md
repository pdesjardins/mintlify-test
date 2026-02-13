---
title: "Refreshing authentication tokens"
id: apiAuthTokenRefresh
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-authenticationOmitChunkFromSearchIndex.md
parentSectionTitle: "Authentication"
previousSectionFile: apiDevGuide-authentication.md
previousSectionTitle: "Authentication and restaurant access"
nextSectionFile: apiDevGuide-apiAuthenticationRateLimit.md
nextSectionTitle: "Authentication rate limit"
excerpt: "The exp value encoded in the accessToken within the authentication token response indicates the UNIX time when the token will expire; UNIX time represents the number of seconds past 1970-01-01..."
keywords: ["accessToken"]
procedures: 0
codeExamples: 0
---

The `exp` value encoded in the `accessToken`
  within the authentication token response indicates the UNIX time when the
  token will expire; UNIX time represents the number of seconds past
  1970-01-01 00:00:00Z. You refresh your integration's authentication token to
  get a new token that you can use after the existing one expires.

Authentication tokens are valid for one day. Multiple requests for
  authentication tokens during the same period of token validity will return
  the same token and the same expiration time. To ensure that you receive an
  authentication token with an expiration time that is later than the
  expiration time of your previous authentication token, your client
  *must* request a new authentication token during the last
  one-minute period that the previous authentication token is valid, or
  re-authenticate once the previous token expires. 

For example, if your client requests an authentication token at 15:00
  and this token expires at 21:00, and then you request another authentication
  token at 15:30, you will receive the same authentication token with the same
  expiration time (21:00) in the second request. You are not able to request a
  new unique authentication token until 20:59 PM. You must either request your
  new authentication token between 20:59 and 21:00 PM in order to consistently
  have a valid authentication token or request a new authentication token once
  the previous token expires. 

Toast support recommends that you cache only *one*
  copy of the token for all locations instead of caching one copy of the token
  per location. This reduces the chances of receiving a 429 rate-limiting
  error when authenticating with an expired token. For more information on
  authentication rate limits, please see [Authentication rate limit](apiDevGuide-apiAuthenticationRateLimit).

If you send an expired authentication token in a request to Toast's
  APIs, you will receive a 401 error in response. If you receive a 401 error,
  your integration *must* stop using this token and must
  request a new token to avoid receiving additional 401 errors.

