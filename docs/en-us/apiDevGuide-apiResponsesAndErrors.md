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
keywords: ["ErrorMessage"]
procedures: 0
codeExamples: 0
---

For successful requests, the HTTP response code is usually 200. The response body contains an API-specific object in JSON format. In certain cases, other HTTP response codes might be used to indicate success.

If a request cannot be processed successfully, a 4*`xx`* HTTP response code is usually returned. The response body is a serialized JSON `ErrorMessage` that contains information about the error. For more information, see [ErrorMessage information](apiDevGuide-apiResponsesAndErrors#apiErrorMessage).

Your Toast API integration client software must also be prepared to handle 5*`xx`* response codes, which indicate a potential problem in the Toast platform service.

Be aware that different APIs handle errors in different ways. If it makes sense for the API call and implementation, it is acceptable to flag a warning or even an error and continue processing a multi-step request to completion.

## Monitoring Toast API responses

Toast APIs return important information about the results of the REST requests that you send. The Toast APIs return standard HTTP responses, which include information about the result of the REST request and information about any errors that occurred. When you develop an integration with the Toast platform, your client software must monitor and respond to those HTTP responses.

The Toast platform performs restaurant functions and returns restaurant information in response to successful REST requests. The Toast platform does not monitor the status of individual integration clients or take any action when a client sends one or more unsuccessful requests. Your Toast platform integration client software must react to unsuccessful REST requests in a way that makes it possible for your organization to correct any problems.

To get help correcting problems that result in unsuccessful Toast API requests, contact Toast integration support.

## HTTP status codes

Toast APIs use [HTTP status codes](https://tools.ietf.org/html/rfc7231#section-6) to indicate the status of an API request. Toast APIs support the following HTTP status codes.

Almost all APIs support the HTTP codes below and no additional HTTP codes. If an API supports any HTTP codes other than the ones listed below, [the reference documentation for the API](https://doc.toasttab.com/openapi/) lists the additional supported codes.

### Success


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Status code</div></th>
      <th className=""><div className="">Name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">200</div></td>
      <td className=""><div className="">OK</div></td>
      <td className=""><div className="">Successful response. The Toast platform was able to process the API request as expected.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">204</div></td>
      <td className=""><div className="">No Content</div></td>
      <td className=""><div className="">The request was successful but there is no content to return.</div></td>
    </tr>
  </tbody>
</table>
</div>

### Client error


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Status code</div></th>
      <th className=""><div className="">Name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">400</div></td>
      <td className=""><div className="">Bad Request</div></td>
      <td className=""><div className="">The API request triggered a known error. <br/> A 400 status code often occurs when the syntax of the request is incorrect or the body of a <code className="">POST</code> request is not structured correctly. <br/> You are responsible for evaluating the <a href="apiDevGuide-apiResponsesAndErrors#apiErrorMessage" className="">error message</a> returned in the API error response in order for future API requests to avoid this error.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">401</div></td>
      <td className=""><div className="">Unauthorized</div></td>
      <td className=""><div className="">The authentication token you submitted is not a recognized Toast API <a href="apiDevGuide-authentication#getting-authentication-token" className="">authentication token</a>. <br/> It is possible that you are submitting an authentication token that has expired and you need to request a new token.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">403</div></td>
      <td className=""><div className="">Forbidden</div></td>
      <td className=""><div className="">You are not permitted to access the resource that you are attempting to access. <br/> This error often occurs when:<ul className=""><li className="">You try to access a restaurant that is not <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants" className="">connected to your integration</a> (if using a <a href="apiDevGuide-authentication#apiAuthenticationReturnDataPartner" className="">partner API client</a>).</li><li className="">You try to access a restaurant that is not <a href="apiDevGuide-apiRestaurantsInGroup" className="">within the management group you work with</a> (if using a <a href="apiDevGuide-authentication#apiAuthenticationReturnDataRestaurant" className="">restaurant management group client</a>).</li><li className="">Your API credentials do not have the proper authorization to use the API you are trying to use.</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">404</div></td>
      <td className=""><div className="">Not Found</div></td>
      <td className=""><div className="">You are attempting to access an unknown resource. This error often occurs if you send a request to an endpoint that does not exist.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">409</div></td>
      <td className=""><div className="">Conflict</div></td>
      <td className=""><div className="">Your API request conflicts with the current state of Toast product data. For example, you might send a <code className="">PUT</code> request to update an employee's wage override for one of their jobs, but an earlier request removed the job from the employee. <br/> This error is also returned if a restaurant publishes changes to its configuration while you are retrieving paginated data from that restaurant. See <a href="apiDevGuide-apiResponseDataPagination#apiPagination409HTTPErrors" className="">Managing 409 HTTP errors in paginated responses</a> for more information.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">422</div></td>
      <td className=""><div className="">Unprocessable Entity</div></td>
      <td className=""><div className="">Your API request contains something that the Toast platform cannot process. <br/> A 422 HTTP response often occurs when an external partner tries to authorize a credit card transaction with <code className="">amount</code> and <code className="">tipAmount</code> values that are both $0.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">429</div></td>
      <td className=""><div className="">Too Many Requests</div></td>
      <td className=""><div className="">You have exceeded your <a href="apiDevGuide-apiRateLimiting" className="">rate limit</a> and must wait before sending more Toast API requests.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">499</div></td>
      <td className=""><div className="">Client Closed Request</div></td>
      <td className=""><div className="">Your system closed the API request before the Toast platform was able to process the request.</div></td>
    </tr>
  </tbody>
</table>
</div>

### Server error


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Status code</div></th>
      <th className=""><div className="">Name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">500</div></td>
      <td className=""><div className="">Internal Server Error</div></td>
      <td className=""><div className="">The Toast platform was unable to complete the request due to an unexpected internal server error.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">502</div></td>
      <td className=""><div className="">Bad Gateway</div></td>
      <td className=""><div className="">The Toast platform experienced an internal gateway error when attempting to process the request.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">504</div></td>
      <td className=""><div className="">Gateway Timeout</div></td>
      <td className=""><div className="">The Toast platform was unable to process the request because internal services took too long to complete processing actions (timeout).</div></td>
    </tr>
  </tbody>
</table>
</div>

## ErrorMessage information

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

  
## Common errors


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Error</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className=""><code className="">ReadOnlyResource</code></div></td>
      <td className=""><div className="">The resource is currently marked READ-ONLY and cannot be updated. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">InvalidRestaurant</code></div></td>
      <td className=""><div className="">The specified restaurant is unknown or invalid. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">InvalidExternalIdentifier</code></div></td>
      <td className=""><div className="">The specified shift external identifier is invalid for this restaurant. For example, it has an incorrect format, length, or other issue. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">UnauthorizedOperation</code></div></td>
      <td className=""><div className="">The client is not authorized to perform this operation. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">VersionMismatch</code></div></td>
      <td className=""><div className="">The client has attempted to use stale versions to update one or more domain objects.</div></td>
    </tr>
  </tbody>
</table>
</div>

