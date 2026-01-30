---
title: "API responses and errors"
id: apiResponsesAndErrors
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiScopes.md
previousSectionTitle: "Scopes"
nextSectionFile: apiDevGuide-apiExampleRequests.md
nextSectionTitle: "Example API requests"
externalReferences: [https://tools.ietf.org/html/rfc7231#section-6, https://doc.toasttab.com/openapi/]
excerpt: "For..."
keywords: [ErrorMessage]
procedures: 0
codeExamples: 0
---

### API responses and errors

For successful requests, the HTTP response code is usually 200. The response body contains an API-specific object in JSON format. In certain cases, other HTTP response codes might be used to indicate success.

If a request cannot be processed successfully, a 4*`xx`* HTTP response code is usually returned. The response body is a serialized JSON `ErrorMessage` that contains information about the error. For more information, see [ErrorMessage information](apiResponsesAndErrors.html#apiErrorMessage).

Your Toast API integration client software must also be prepared to handle 5*`xx`* response codes, which indicate a potential problem in the Toast platform service.

Be aware that different APIs handle errors in different ways. If it makes sense for the API call and implementation, it is acceptable to flag a warning or even an error and continue processing a multi-step request to completion.

#### Monitoring Toast API responses

Toast APIs return important information about the results of the REST requests that you send. The Toast APIs return standard HTTP responses, which include information about the result of the REST request and information about any errors that occurred. When you develop an integration with the Toast platform, your client software must monitor and respond to those HTTP responses.

The Toast platform performs restaurant functions and returns restaurant information in response to successful REST requests. The Toast platform does not monitor the status of individual integration clients or take any action when a client sends one or more unsuccessful requests. Your Toast platform integration client software must react to unsuccessful REST requests in a way that makes it possible for your organization to correct any problems.

To get help correcting problems that result in unsuccessful Toast API requests, contact Toast integration support.

#### HTTP status codes

Toast APIs use [HTTP status codes](https://tools.ietf.org/html/rfc7231#section-6) to indicate the status of an API request. Toast APIs support the following HTTP status codes.

Almost all APIs support the HTTP codes below and no additional HTTP codes. If an API supports any HTTP codes other than the ones listed below, [the reference documentation for the API](https://doc.toasttab.com/openapi/) lists the additional supported codes.

##### Success

| Status code | Name | Description | 
| --- | --- | --- |
| 200 | OK | Successful response. The Toast platform was able to process the API request as expected. | 
| 204 | No Content | The request was successful but there is no content to return. | 

##### Client error

| Status code | Name | Description | 
| --- | --- | --- |
| 400 | Bad Request | The API request triggered a known error.A 400 status code often occurs when the syntax of the request is incorrect or the body of a `POST` request is not structured correctly.You are responsible for evaluating the [error message](apiResponsesAndErrors.html#apiErrorMessage) returned in the API error response in order for future API requests to avoid this error. | 
| 401 | Unauthorized | The authentication token you submitted is not a recognized Toast API [authentication token](authenticationOmitChunkFromSearchIndex.html#getting-authentication-token).It is possible that you are submitting an authentication token that has expired and you need to request a new token. | 
| 403 | Forbidden | You are not permitted to access the resource that you are attempting to access.This error often occurs when:- You try to access a restaurant that is not [connected to your integration](apiPartnersGettingAccessibleRestaurants.html) (if using a [partner API client](authenticationOmitChunkFromSearchIndex.html#apiAuthenticationReturnDataPartner)).
- You try to access a restaurant that is not [within the management group you work with](apiGettingRestaurantInfoOmitChunkFromSearchIndex.html#apiRestaurantsInGroup) (if using a [restaurant management group client](authenticationOmitChunkFromSearchIndex.html#apiAuthenticationReturnDataRestaurant)).
- Your API credentials do not have the proper authorization to use the API you are trying to use.

 | 
| 404 | Not Found | You are attempting to access an unknown resource. This error often occurs if you send a request to an endpoint that does not exist. | 
| 409 | Conflict | Your API request conflicts with the current state of Toast product data. For example, you might send a `PUT` request to update an employee's wage override for one of their jobs, but an earlier request removed the job from the employee.This error is also returned if a restaurant publishes changes to its configuration while you are retrieving paginated data from that restaurant. See [Managing 409 HTTP errors in paginated responses](apiResponseDataPagination.html#apiPagination409HTTPErrors) for more information. | 
| 422 | Unprocessable Entity | Your API request contains something that the Toast platform cannot process.A 422 HTTP response often occurs when an external partner tries to authorize a credit card transaction with `amount` and `tipAmount`values that are both $0. | 
| 429 | Too Many Requests | You have exceeded your [rate limit](apiRateLimiting.html) and must wait before sending more Toast API requests. | 
| 499 | Client Closed Request | Your system closed the API request before the Toast platform was able to process the request. | 

##### Server error

| Status code | Name | Description | 
| --- | --- | --- |
| 500 | Internal Server Error | The Toast platform was unable to complete the request due to an unexpected internal server error. | 
| 502 | Bad Gateway | The Toast platform experienced an internal gateway error when attempting to process the request. | 
| 504 | Gateway Timeout | The Toast platform was unable to process the request because internal services took too long to complete processing actions (timeout). | 

#### ErrorMessage information

Toast APIs return a JSON `ErrorMessage` object in the HTTP response to an unsuccessful REST request. The `ErrorMessage` object includes information that describes one or more errors encountered during the processing of a request.

It contains the following values:



**`status`**
: The HTTP status code.



**`code`**
: Service-specific result code. For example, 10003.



**`message`**
: A brief, user-friendly message that describes the error.



**`messageKey`**
: This value is not used. It is included for future use.



**`fieldName`**
: This value is not used. It is included for future use.



**`link`**
: The URL of a Toast page that provides more information about the error.



**`requestId`**
: The identifier of the HTTP request that generated the error.



**`developerMessage`**
: Optional technical information that might be useful for a developer who is debugging the cause of the error.



**`errors`**
: A list of JSON `ErrorMessage` objects.



**`canRetry`**
: This value is not used. It is included for future use.





The following example shows the `ErrorMessage` object for an unsuccessful Toast API REST request.

**Example 1.10. ErrorMessage object**

```
{
  "status": 400,
  "code": 10025,
  "message": "Payment amount cannot be empty",
  "messageKey": null,
  "fieldName": null,
  "link": null,
  "requestId": "2ea769e2-7fcb-4148-ba75-8de77a248h21",
  "developerMessage": null,
  "errors": [],
  "canRetry": null
}
```

  
#### Common errors

| Error | Description | 
| --- | --- |
| `ReadOnlyResource` | The resource is currently marked READ-ONLY and cannot be updated.  | 
| `InvalidRestaurant` | The specified restaurant is unknown or invalid.  | 
| `InvalidExternalIdentifier` | The specified shift external identifier is invalid for this restaurant. For example, it has an incorrect format, length, or other issue.  | 
| `UnauthorizedOperation` | The client is not authorized to perform this operation.  | 
| `VersionMismatch` | The client has attempted to use stale versions to update one or more domain objects. | 

