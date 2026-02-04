---
title: "Rate limiting"
id: apiRateLimiting
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiClientAccounts.md
previousSectionTitle: "Toast API accounts"
nextSectionFile: apiDevGuide-portalToastIdentifiers.md
nextSectionTitle: "Toast identifiers"
excerpt: "To..."
procedures: 0
codeExamples: 0
---

To maintain the stability and availability of APIs for all client applications, Toast APIs are rate-limited. This ensures that a single API client cannot consume all API resources and deny service to other clients. Requests that exceed a rate limit are denied with an HTTP status code 429 response.

## Toast rate limit values

Here are the current rate limits for Toast APIs. These rate limits are described in more detail in [How rate limiting works](apiRateLimiting.html#apiRateLimitingOverview).



****Global rate limit****
: 20 requests per second, 10,000 requests per 15 minutes

The global rate limit limits the total number of requests that an API client can make across all APIs collectively.

For example, if your client makes 3 requests to the orders API, and 7 requests to the labor API, it made a total of 10 requests against the Toast APIs collectively.



****Default API rate limit****
: 20 requests per second, 10,000 requests per 15 minutes

API rate limits are used to limit requests to individual Toast APIs.



> **Note**
> 
> The global and default API rate limits are currently the same, but might differ in the future.
> There are currently no custom API rate limits for specific APIs.




****Endpoint-specific rate limits****
: The `GET /menus` endpoint of the menus API uses an endpoint rate limit for each client of one request per second per location. Requests that your API client makes for one restaurant do not affect the client's rate limits for any other restaurant.

The `GET /metadata` endpoint uses the default API rate limit of 20 requests per second, 10,000 requests per 15 minutes.

The `GET /ordersBulk` endpoint of the orders API uses an endpoint rate limit of five requests per client per location per second. Requests to the `/ordersBulk` endpoint for historical data using the `startDate` and `endDate` query parameters must not exceed intervals greater than one month with calls spaced at least 5-10 seconds apart.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk`endpoint.








> **Note**
> 
> An [API account](apiClientAccounts.html#apitypesOfToastApiAccounts) that integrates with many restaurant locations may have additional, account-specific rate limits. These account rate limits track the total number of requests the client integration makes to certain APIs or endpoints *across all restaurant locations*.
> Toast support reaches out directly to integration providers to discuss the need for an account rate limit before putting the rate limit in place. See [Account rate limits](apiRateLimiting.html#apiAccountRateLimits) for more information.


## How rate limiting works

This section provides an overview of Toast rate limiting functionality.

### Rate limiting is per restaurant or per IP address

When the `Toast-Restaurant-External-ID` header is included in the request, then rate limiting is applied per restaurant location.

If the `Toast-Restaurant-External-ID` header is absent, then rate limiting is applied per IP address. For example, the partners API does not require a restaurant context, and you do not provide restaurant context for requests for an authorization token.

When rate limits are applied per restaurant location, requests that your API client makes for one restaurant location do not affect the client's rate limits for any other restaurant. In other words, if Client A has reached its rate limit for Restaurant A, it can continue to make requests for Restaurant B until it exhausts its rate limit for Restaurant B.



> **Note**
> 
> An [API account](apiClientAccounts.html#apitypesOfToastApiAccounts) that integrates with many restaurant locations may have additional, account-specific rate limits that track the total number of requests the client integration makes *across all restaurant locations*. For these API accounts, the Toast platform tracks both the number of requests made per location, as described above, *and* the total number of requests made across locations. Requests made for a restaurant location may impact the ability to make requests at other restaurant locations if the client integration has exceeded its account rate limit.
> Toast support reaches out directly to integration providers to discuss the need for an account rate limit before putting the rate limit in place. See [Account rate limits](apiRateLimiting.html#apiAccountRateLimits) for more information.


### Rate limits are a collection of limits

A rate limit is a collection of limits. For example, 20 requests per second and 10,000 requests per fifteen minutes.

Toast APIs return header fields in response to each request that report on the specific limit within a rate limit that is the closest to being exceeded.

For more information, see [Rate limiting header fields](apiRateLimiting.html#apiRateLimitingHeaderFieldsV2).

### Rate limits use fixed time slices

Toast APIs use fixed time slices when they calculate whether the [individual limits within a rate limit](apiRateLimiting.html#apiRateLimitesAreACollectionOfLimits) were reached.

In this approach, each individual limit is associated with a time slice that has a fixed start and end time. For example, you are limited to 20 requests in the 09:00:00 to 09:00:01 time slice, and 10,000 requests in the 09:00:00 to 09:15:00 time slice.

The Toast APIs track the requests made within each time slice independently. When a time slice ends, the limits associated with that time slice are reset.

To illustrate this concept, consider the following example:

1. Requests allowed:

- 09:00:00 to 09:00:01 time slice: 20 requests


- 09:00:00 to 09:15:00 time slice: 10,000 requests




2. At 09:00:00, a request is made.

Requests remaining:

- 09:00:00 to 09:00:01 time slice: 19


- 09:00:00 to 09:15:00 time slice: 9999




3. At 09:00:01, the shorter time slice ends and a new one begins:

Requests remaining:

- 09:00:01 to 09:00:02 time slice: 20


- 09:00:00 to 09:15:00 time slice: 9999





With each response, the Toast APIs return a header field that tells you when the time slice for the limit that is closest to being exceeded will be reset.

For more information, see [Rate limiting header fields](apiRateLimiting.html#apiRateLimitingHeaderFieldsV2).

### Rate limit types and priority

Toast APIs use the following rate limit types:



****Global rate limit****
: This rate limit is applied to requests made across all Toast APIs collectively. For example, assuming a global rate limit of 20 requests/second, your API client can make a total of 20 requests per second, regardless of which API those requests are sent to. So, sending 15 requests to the orders API and 5 requests to the labor API in the same second is acceptable but sending 20 requests to the orders API and 20 requests to the labor API in the same second is not.



****API rate limits****
: API rate limits are applied to requests made against individual APIs, for example, the orders API or the labor API. Toast APIs have a default API rate limit.

There are currently no custom rate limits for individual Toast APIs.



****Endpoint rate limits****
: Endpoint rate limits apply to requests that are made to individual endpoints, such as requests to the `/orders/\{guid\}` endpoint of the orders API.





The global rate limit has the highest priority, followed by the API rate limit, and then the endpoint rate limit.

When a rate limit with a higher priority is reached, the client application is considered rate limited, even if rate limits with a lower priority have not been reached yet.

To better understand how rate limit priority works, consider the following example:

- **Global rate limit:** 20 requests/second, 10,000 requests/15 minutes


- **Orders API rate limit:** 10 requests/second


- **Time slice:** 09:00:00 - 09:00:01



At 09:00:00, ClientA makes a request to the orders API service for RestaurantA. After this request is made, the requests remaining on each rate limit are:

- **Global requests remaining:** 19 requests/second, 9,999 requests/15 minutes


- **Orders API requests remaining:** 9 requests/second



Between 09:00:00 and 09:00:01, ClientA makes an additional 19 requests for RestaurantA to services *other than the orders API*. After these requests are made, the requests remaining on each rate limit are:

- **Global requests remaining:** 0 requests/second, 9,980 requests/15 minutes


- **Orders API requests remaining:** 9 requests/second



Because the global rate limit has the highest priority and its rate limit has been reached, the client application is rate limited, even though orders API requests are still available. ClientA can no longer make requests until the next time slice starts at 09:00:01.



> **Note**
> 
> An [API account](apiClientAccounts.html#apitypesOfToastApiAccounts) that integrates with many restaurant locations may have additional, account-specific rate limits. These account rate limits track the total number of requests the client integration makes to certain APIs or endpoints *across all restaurant locations*.
> Toast support reaches out directly to integration providers to discuss the need for an account rate limit before putting the rate limit in place. See [Account rate limits](apiRateLimiting.html#apiAccountRateLimits) for more information.


### Rate limiting header fields

The following header fields are returned for every request to inform you of the rate limit that you are closest to exceeding. They are:



**`X-Toast-RateLimit-By`**
: The type of rate limit that the client application is closest to exceeding: `GLOBAL`, `API`, or `ENDPOINT`.

The other header fields describe a specific limit within this rate limit.

When this header field contains `API` or `ENDPOINT`, it may also contain `ACCOUNT` to indicate that an account rate limit on an API or endpoint is close to being exceeded. When `X-Toast-RateLimit-By` contains more than one value, the values are comma-separated. See [Account rate limits](apiRateLimiting.html#apiAccountRateLimits) for more information.



**`X-Toast-RateLimit-Remaining`**
: The number of requests left in the current time slice for the limit that is closest to being exceeded.



**`X-Toast-RateLimit-Reset`**
: A timestamp, in UNIX epoch format, for when the next time slice for this limit begins and the request count is reset.

This header field uses the UNIX epoch format because it is easiest to compare programmatically.





When a rate limit is exceeded, an additional header, `Retry-After`, is provided in the 429 HTTP response to help you to recover from the rate limited state. This header gives you the number of seconds until the request count is reset for the rate limit specified in `X-Toast-RateLimit-By`.

The header fields are in the context of the request. For example, consider a `GET` request to the `/orders/\{guid\}`endpoint:

- If the `X-Toast-RateLimit-By` header field returns `GLOBAL`, then the rate limit that is closest to being exceeded is the global rate limit.


- If the `X-Toast-RateLimit-By` header field returns `API`, then the rate limit that is closest to being exceeded is the orders API rate limit.


- If the `X-Toast-RateLimit-By` header field returns `ENDPOINT`, then the rate limit for the `/orders/\{guid\}` endpoint is closest to being exceeded.



The values in these header fields may change significantly as you make API requests. They reflect the rate limit type and the individual limit within that rate limit type that is closest to being exceeded. These values change as requests are made.



> **Note**
> 
> Rate limiting header fields are not included in authentication API responses. See [Authentication rate limit](apiAuthenticationRateLimit.html) for more information.


### Handling being rate limited

Toast APIs return a 429 HTTP response code when an API client that has been rate limited submits a request.

If your client receives a 429 response, it should stop making requests and inspect the `X-Toast-RateLimit-Reset` or `Retry-After` header field to determine when it can start making requests again.

## Programming a client for sustained time-sensitive requests

Toast API rate limits include both shorter and longer time slices to support bursts of requests (20 per second) as well as sustained requests over time (10,000 per 15 minutes). API clients that need to make sustained requests for time-sensitive data, such as order status updates, must be programmed to take both time slices into account so that they are not rate limited when attempting to make a request for that time-sensitive data.

To better understand why, consider the following example:

- A global rate limit of 20 requests/second and 10,000 requests per 15 minutes.


- All requests in the example are made within the same 15 minute time slice.



If an API client makes 20 requests per second, as allowed by the shorter time slice, then in 8 minutes and 20 seconds, it will have made 10,000 requests and any subsequent requests will exceed the limit for the 15-minute time slice. The client must wait 6 minutes and 40 seconds for the 15-minute time slice to reset before it can continue to make requests.

To avoid this long delay, the client application should throttle its requests so that it does not exceed either limit. Specifically, if the client makes 11 requests per second, it does not exceed either limit because this request frequency translates into 9,900 requests in 15 minutes (11 requests X 60 seconds X 15 minutes = 9,900).

## Account rate limits



> **Important**
> 
> The other rate limits described earlier in this chapter apply *to all client integrations*. Toast support applies the *account rate limits* described in this section to a small number of client integrations that make requests for a very large number of restaurants.
> Toast support reaches out directly to integration developers to discuss the need for an account rate limit before putting the rate limit in place. If Toast support has not reached out to you about an account rate limit, then you can ignore the account rate limit information in this section.


[API accounts](apiClientAccounts.html#apitypesOfToastApiAccounts) that integrates with many restaurant locations may have additional account-specific rate limits. Account rate limits are used to limit the total number of requests an integration can make to an API or an endpoint *across all restaurant locations* during a given time slice. For these accounts, the Toast platform tracks both the number of requests made per location and the total number of requests made across locations within each time slice.

### Account rate limit example

To understand how account rate limits work, consider the following example:

- The orders API uses the default API rate limit of 20 requests per second and 10,000 requests per 15 minutes (the client cannot exceed either limit).


- Account A has 10,000 locations.



With the standard rate limits that apply to all API accounts, it would be possible for Account A's integration to send 200,000 requests to the orders API in a single second (20 requests per second X 10,000 locations), potentially overwhelming the service.

To avoid this situation, Toast support assigns Account A an account rate limit of 20,000 requests per second for the orders API. This means that:

- Account A's integration can make no more than 20,000 requests to the orders API per second *across all 10,000 locations*.


- If Account A's integration makes 20 requests in a single second for 1,000 of its locations, as allowed by the standard rate limits, it will have used up its 20,000 requests in that second and it will be prevented from making requests for the other 9,000 locations during that same second.



### Account rate limits are per API or per endpoint

Account rate limits are applied per API or per endpoint. Requests that your integration client sends to one API or endpoint do not affect the client's rate limits for other APIs or endpoints. In other words, if Client A has reached its account rate limit for an API during a given time slice, it can still make requests to other Toast APIs during the same time slice. This also holds true for endpoint requests. If Client A has reached its account rate limit for an endpoint during a given time slice, it can still make requests to other endpoints.

### Account rate limit header field

The value `ACCOUNT` is added to the `X-Toast-RateLimit-By` header field when an account rate limit is the closest to being exceeded:

- This is the value of the `X-Toast-RateLimit-By`header field when the account rate limit for an API is closest to being exceeded:

`X-Toast-Ratelimit-By: API, ACCOUNT`


- This is the value of the `X-Toast-RateLimit-By`header field when the account rate limit for an endpoint is closest to being exceeded:

`X-Toast-Ratelimit-By: ENDPOINT, ACCOUNT`



### Additional locations may affect the account rate limit

If you are an integration provider with an account rate limit, and additional restaurant locations add your integration to their restaurant, those additional locations will contribute to the total number of requests your integration makes across all locations. This can potentially cause the integration to exceed the account rate limit. For this reason, as additional locations add your integration to their restaurant, you may need to adjust how your integration handles throttling to ensure it doesn't exceed its account rate limit.

