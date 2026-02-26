---
title: "Paginating response data"
id: apiResponseDataPagination
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiToastApisAndTheEnterpriseModule.md
previousSectionTitle: "Toast APIs and the enterprise module"
nextSectionFile: apiDevGuide-apiScopes.md
nextSectionTitle: "Scopes"
externalReferences: [https://tools.ietf.org/html/rfc5988]
excerpt: "Some Toast API endpoints paginate response data to limit the number of data objects they return, to make the size of the endpoint response data more practical for your integration. You can make..."
procedures: 0
codeExamples: 0
---

[Some Toast API endpoints](apiDevGuide-apiResponseDataPagination#apiResponsePaginationTypes)paginate response data to limit the number of data objects they return, to make the size of the endpoint response data more practical for your integration. You can make additional requests to these endpoints to get data objects that were excluded from the response to your first request.

For example, a restaurant might have a large number of discounts. An endpoint that returns discount data objects might limit the number of objects in a single response to ensure that the data size of the response does not become too large.

If an endpoint paginates response data, the number of objects that it returns in a single response is based on the data size of those objects. An endpoint might return more or fewer objects in a single request depending on the amount of data in each object.

## Page token pagination



> **Important**
> 
> The page token response data pagination described here is new Toast API functionality and replaces the previous response pagination parameters in the configuration API. The previous pagination query parameters for configuration API endpoints (`pageSize` and `page`) are deprecated and are removed from the configuration API endpoints.


An endpoint that paginates response data provides an identifier string for *the next set* of response data objects in an HTTP response header field. The endpoint accepts that identifier string as an optional query parameter in the following requests that you make and returns the next set of response data objects.

### Paginated response header field and query parameter

When you interact with an endpoint that has paginated results, you use the following header field and query parameter:



**`Toast-Next-Page-Token`**
: A response header field that identifies the following set of objects that the endpoint will return. This value is a string that you use in the `pageToken` query parameter in a following request.



**`pageToken`**
: A query parameter that controls the first object that the endpoint returns in its response data. You get the string value of this parameter from the `Toast-Next-Page-Token` header field in the response to a previous request.





Some Toast API endpoints paginate responses in a way that returns a fixed number of result data objects in each page. If the endpoint you are using includes the `pageSize` and `page` query parameters, the endpoint uses fixed-size response data pagination. For more information, see [Fixed-size paginated responses](apiDevGuide-apiResponseDataPagination#apiResponseDataPaginationFixedPageSize).

### How to use paginated Toast API responses

The following procedure explains how to use paginated Toast API responses.

**Procedure 1.22. Using paginated Toast API responses**

1. Send a REST API request that returns a large number of data objects in its response. For example, `GET` requests to endpoints in the configuration API might return a large number of data objects for some restaurant configuration components.


2. Get the token string for the next set of response objects from the `Toast-Next-Page-Token` header field in the response.

If the response does not include a `Toast-Next-Page-Token` field, there are no more data objects in the response for your endpoint request and there is no next page to return.

The following example shows the `Toast-Next-Page-Token` field in the header of a Toast API response.


```
Date: Tue, 31 Aug 2021 21:16:09 GMT
Content-Type: application/json
Transfer-Encoding: chunked
Connection: keep-alive
X-Toast-RateLimit-By: API
X-Toast-RateLimit-Remaining: 19
X-Toast-RateLimit-Reset: 1630444570
toast-next-page-token: Yzp7Imxhc3RUeXBlIjoiTWVudUl0ZW0iLCJsYXN0RXZhbHVhdGVkS2V5
  Ijp7IkFjdGl2ZVZlcnNpb25QSyI6eyJzIjoiUFVCTElTSCM3NmNiMWIwNS1jYjFlLTRhZGYtODYzY
  S1iMmE5NGE1ZWNkY2YjTWVudUl0ZW0iLCJuIjpudWxsLCJiIjpudWxsLCJtIjpudWxsLCJsIjpudW
  xsLCJicyI6bnVsbCwibnVsbCI6bnVsbCwiYm9vbCI6bnVsbCwic3MiOm51bGwsIm5zIjpudWxsfSw
  iU0siOnsicyI6Ik1lbnVJdGVtI2MxOTdmNTE3LWFjZTQtNDZjOC1hYWU2LTJlZDBkN2QwNjUyYiIs
  Im4iOm51bGwsImIiOm51bGwsIm0iOm51bGwsImwiOm51bGwsImJzIjpudWxsLCJudWxsIjpudWxsL
  CJib29sIjpudWxsLCJzcyI6bnVsbCwibnMiOm51bGx9LCJBY3RpdmVWZXJzaW9uMiI6eyJzIjoiYz
  E5N2Y1MTctYWNlNC00NmM4LWFhZTYtMmVkMGQ3ZDA2NTJiIiwibiI6bnVsbCwiYiI6bnVsbCwibSI
  6bnVsbCwibCI6bnVsbCwiYnMiOm51bGwsIm51bGwiOm51bGwsImJvb2wiOm51bGwsInNzIjpudWxs
  LCJucyI6bnVsbH0sIlBLIjp7InMiOiJQVUJMSVNIIzc2Y2IxYjA1LWNiMWUtNGFkZi04NjNhLWIyY
  Tk0YTVlY2RjZiNGVUxMIzU5NyIsIm4iOm51bGwsImIiOm51bGwsIm0iOm51bGwsImwiOm51bGwsIm
  JzIjpudWxsLCJudWxsIjpudWxsLCJib29sIjpudWxsLCJzcyI6bnVsbCwibnMiOm51bGx9fSwiYWN
  0aXZlVmVyc2lvbkluZGV4IjoiQUNUSVZFX1ZFUlNJT05fMiIsInZlcnNpb24iOiJ2MSJ9
vary: Accept-Encoding
content-encoding: gzip
Strict-Transport-Security: max-age=31536000; includeSubDomains
CF-Cache-Status: DYNAMIC
Expect-CT: max-age=604800, 
  report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
Server: cloudflare
CF-RAY: 6879473d0d6f1851-EWR
```


3. Include the token string in the `pageToken` query parameter of another request to the endpoint.

The following example shows the `pageToken` query parameter with a token string value.


```
https://`[toast-api-hostname]`/config/v2/discounts?pageToken=Yzp7Imxhc3RUeXBlIjoiT
  WVudUl0ZW0iLCJsYXN0RXZhbHVhdGVkS2V5Ijp7IkFjdGl2ZVZlcnNpb25QSyI6eyJzIjoiUFVCTEl
  TSCM3NmNiMWIwNS1jYjFlLTRhZGYtODYzYS1iMmE5NGE1ZWNkY2YjTWVudUl0ZW0iLCJuIjpudWxsL
  CJiIjpudWxsLCJtIjpudWxsLCJsIjpudWxsLCJzcyI6bnVsbCwibnMiOm51bGwsImJzIjpudWxsLCJ
  udWxsIjpudWxsLCJib29sIjpudWxsfSwiU0siOnsicyI6Ik1lbnVJdGVtIzhhYzViNGU1LTRkOWMtN
  GNmNy1hZDE4LTBjZDg0ZmI3ZjhjZSIsIm4iOm51bGwsImIiOm51bGwsIm0iOm51bGwsImwiOm51bGw
  sInNzIjpudWxsLCJucyI6bnVsbCwiYnMiOm51bGwsIm51bGwiOm51bGwsImJvb2wiOm51bGx9LCJBY
  3RpdmVWZXJzaW9uMiI6eyJzIjoiOGFjNWI0ZTUtNGQ5Yy00Y2Y3LWFkMTgtMGNkODRmYjdmOGNlIiw
  ibiI6bnVsbCwiYiI6bnVsbCwibSI6bnVsbCwibCI6bnVsbCwic3MiOm51bGwsIm5zIjpudWxsLCJic
  yI6bnVsbCwibnVsbCI6bnVsbCwiYm9vbCI6bnVsbH0sIlBLIjp7InMiOiJQVUJMSVNIIzc2Y2IxYjA
  1LWNiMWUtNGFkZi04NjNhLWIyYTk0YTVlY2RjZiNGVUxMIzU5NSIsIm4iOm51bGwsImIiOm51bGwsI
  m0iOm51bGwsImwiOm51bGwsInNzIjpudWxsLCJucyI6bnVsbCwiYnMiOm51bGwsIm51bGwiOm51bGw
  sImJvb2wiOm51bGx9fSwiYWN0aXZlVmVyc2lvbkluZGV4IjoiQUNUSVZFX1ZFUlNJT05fMiIsInZlc
  nNpb24iOiJ2MSJ9
```


4. Repeat [Step 2](apiDevGuide-apiResponseDataPagination#apiPaginationGetPageTokenStep) and [Step 3](apiDevGuide-apiResponseDataPagination#apiPaginationPageTokenStep)until the response you receive does not include a `Toast-Next-Page-Token` header field.

When the response does not include the `Toast-Next-Page-Token` header field, you have received all the data objects in the endpoint response.



### Managing 409 HTTP errors in paginated responses

A restaurant might change its configuration while your integration client is retrieving paginated data for that restaurant. If a restaurant that your client is retrieving paginated data for publishes any changes to its configuration during the data retrieval, the Toast platform sends a 409 HTTP error.

If your integration client receives a 409 error, it should re-submit the request it is making, without the `pageToken`query parameter, so that the response restarts from the first page.

## Fixed-size paginated responses

[Some Toast API endpoints](apiDevGuide-apiResponseDataPagination#apiResponsePaginationTypes)allow your client to control the number of objects in the response data. In a Toast API endpoint that uses fixed page size response data pagination, you specify:

- The number of objects in the response data.


- The first object that the endpoint will return.





> **Note**
> 
> Most Toast APIs *do not* paginate responses using fixed page sizes. If the Toast API endpoint that you are using does not accept the `pageSize` and `page` query parameters, that endpoint uses the pagination functionality explained in [Page token pagination](apiDevGuide-apiResponseDataPagination#apiPaginationPageToken).


### Query parameters for fixed page size pagination

For fixed page size pagination, you use the following query parameters:



**`pageSize`**
: The maximum number of objects that a Toast API endpoint will return in the response data for a single request.



**`page`**
: The sequence number of the first set of objects that a Toast API endpoint will return in response data.





### How to use a fixed page size paginated response

To use the paginated response of a Toast API endpoint that uses a fixed page size, make a `GET` request to the endpoint. Inspect the `Toast-Total-Result-Count` HTTP header field in the response to determine the total number of objects the endpoint will return.



> **Note**
> 
> Currently, the `/ordersBulk` endpoint does not include the `Toast-Total-Result-Count` HTTP header field in its response. The Toast integrations team will announce when it becomes available in the API release notes. To sign up to receive API release note notifications, see [API status and updates](apiDevGuide-apiUpdatesEmailDistributionList).


In subsequent requests, use the `pageSize` and `page` query parameters to specify the number of objects to return per page and the sequence number of the page to return, respectively.

Toast API endpoints that paginate responses to control the size of response data also return URLs for the first, adjacent, and last sets of objects in the `Link` HTTP header fields, as described in the [proposed Internet Engineering Task Force (IETF) web linking standard](https://tools.ietf.org/html/rfc5988). The value of the *`rel`* parameter in the `Link` field indicates the relationship of the URL to the current set of objects.

The following example shows `Link` header fields in a Toast API response.

**Example 1.9. Link header fields with pagination information**


```
Link: \<https://`[toast-api-hostname]`/config/v2/menus?pageSize=1\>; rel="first"
Link: \<https://`[toast-api-hostname]`/config/v2/menus?pageSize=1&page=5\>; rel="self"
Link: \<https://`[toast-api-hostname]`/config/v2/menus?pageSize=1&page=4\>; rel="prev"
Link: \<https://`[toast-api-hostname]`/config/v2/menus?pageSize=1&page=6\>; rel="next"
Link: \<https://`[toast-api-hostname]`/config/v2/menus?pageSize=1&page=10\>; rel="last"
```



    <tr>
      <td>[(1)](#co-d1e46DF66837F-C33C-4DCD-9FF7-6D9DA64EC0D9)</td>
      <td>The URL and query parameters that will return the first set of objects available from the API endpoint.</td>
    </tr>
    <tr>
      <td>[(2)](#co-d1e48DF66837F-C33C-4DCD-9FF7-6D9DA64EC0D9)</td>
      <td>The URL and query parameters that will return the current set of objects from the API endpoint.</td>
    </tr>
    <tr>
      <td>[(3)](#co-d1e50DF66837F-C33C-4DCD-9FF7-6D9DA64EC0D9)</td>
      <td>The URL and query parameters that will return the set of objects immediately preceding the current set from the API endpoint.</td>
    </tr>
    <tr>
      <td>[(4)](#co-d1e52DF66837F-C33C-4DCD-9FF7-6D9DA64EC0D9)</td>
      <td>The URL and query parameters that will return the first set of objects immediately after the current set from the API endpoint.</td>
    </tr>
    <tr>
      <td>[(5)](#co-d1e54DF66837F-C33C-4DCD-9FF7-6D9DA64EC0D9)</td>
      <td>The URL and query parameters that will return the last set of objects available from the API endpoint.</td>
    </tr>
  
## Response pagination types used by Toast APIs

The following table identifies the pagination functionality used by Toast API endpoints.


<table>
  <thead>
    <tr>
      <th>API and endpoint</th>
      <th>Response pagination used</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Configuration API</td>
      <td>All endpoints that return paginated response data use <em>page token pagination</em> . For more information, see [Page token pagination](apiDevGuide-apiResponseDataPagination#apiPaginationPageToken). <blockquote><strong>Note</strong> Configuration API endpoints previously used fixed-size pagination for response data. The parameters for using fixed-size pagination are still supported, but fixed-size pagination is deprecated <em>for configuration API endpoints</em> . As of 2021-12-06, configuration API endpoints no longer support fixed-size pagination and only support page token pagination.</blockquote> </td>
    </tr>
    <tr>
      <td>Kitchen API</td>
      <td>All endpoints that return paginated response data use <em>page token pagination</em>  for response data. <br/> For more information, see [Page token pagination](apiDevGuide-apiResponseDataPagination#apiPaginationPageToken).</td>
    </tr>
    <tr>
      <td>Orders API `/ordersBulk` endpoint</td>
      <td>The orders API `/ordersBulk` endpoint uses <em>fixed-size pagination</em> . <br/> For more information, see [Fixed-size paginated responses](apiDevGuide-apiResponseDataPagination#apiResponseDataPaginationFixedPageSize).</td>
    </tr>
  </tbody>
</table>

