---
title: "Deprecated API functions"
id: apiDeprecatedApiFunctions
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiApiUpdatesMayRequirePublishes.md
previousSectionTitle: "API updates may require publishes"
nextSectionFile: apiDevGuide-portalChecklistsAndTestPlansOmitChunkFromSearchIndex.md
nextSectionTitle: "Checklists and test plans"
externalReferences: [https://curl.haxx.se/, https://central.toasttab.com/s/article/Automated-Nightly-Data-Export-1492723819691, https://stedolan.github.io/jq/]
excerpt: "This section includes information about Toast API functionality that is available but is expected to be removed or replaced."
procedures: 0
codeExamples: 0
---

### Deprecated API functions

This section includes information about Toast API functionality that is available but is expected to be removed or replaced.

#### Orders

This section includes information about Toast orders API functionality that is available but is expected to be removed or replaced.

##### Getting order identifiers for a time period (deprecated)

You can send a `GET` request to the `/orders` endpoint to get a list of the orders that were last modified during a period of time.

When you send a `GET` request to the `/orders` endpoint, you specify the period of time that you want to return orders for by using one of two query parameter options:

- You can select the orders that were last modified during a time period of up to one hour by specifying dates and times in the `startDate` and `endDate` query parameters. Note that modification includes creation; that is, these query parameters will return orders that were created or modified during the specified time period.


- You can select the orders that were created during a single restaurant business day by setting the `businessDate` query parameter. The restaurant's business day cutoff is determined by the `closeoutHour` value in the `General` object within the `RestaurantInfo` object in the restaurants API.



Toast support recommends that you use the `startDate` and `endDate` query parameters, because these parameters get order information using the order's *modification* timestamp. The `businessDate` query parameter gets the information using the order's *creation* date. This means, for example, that if you retrieve order GUIDs with the `businessDate` query parameter, you will not get orders that were modified on that date but created on an earlier date.

**Example 1.11. Request for orders last modified during a time period**

The following example shows the path for a `GET` request that will return orders last modified during a one-hour period. The values of the `startDate` and `endDate` query parameters must be URL encoded. For more information about date and time formats, see [Dates and timestamps](api_dates_and_timestamps.html).

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e9309EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \[(2)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e9509EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
"https://`[toast-api-hostname]`/orders/v2/orders?[(3)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e9709EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
startDate=2019-02-27T09%3A00%3A00.000-0500&
endDate=2019-02-27T09%3A59%3A00.000-0500"[(4)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e9909EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the GUID of the restaurant that created the orders. This must be an individual restaurant, not the GUID for a restaurant group.

(3) Send a GET request to the /orders endpoint of the orders API.

(4) Specify a period of time up to one hour by including dates and times in the startDate and endDate query parameters.

  
**Example 1.12. Request for orders created during one business day**

The following example **curl** command shows a request for all of the orders that were created during one restaurant business day. Specify the restaurant business day with the *`businessDate`* query parameter.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
"https://`[toast-api-hostname]`/orders/v2/orders?
businessDate=20190227"
```

  
**Example 1.13. Response data containing order GUIDs for one business day**

The following example shows the response data from the `/orders` endpoint using the *`businessDate`* query parameter. It contains the GUIDs of each order that was created at a restaurant during a business day. The response data from a request using the *`startDate`*and *`endDate`* query parameters will contain the GUIDs of orders that were modified or created during the specified time period.

```
[
  "017fdd94-4a30-4657-9475-b1a684758531",[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e11509EC9F64-B75D-413A-803D-C8F76FF3D18A-co)
  "a64ce8be-c3d0-44cb-a807-86b997847469",
  "bd1e031e-cb86-4ea5-baea-7a6d887d41d8",

  [contents omitted]

  "12acb0c5-27e1-4022-9ad3-2a58f389d590",
  "b89eb706-55ee-4fa2-915c-377568b831cd",
  "e5f91d49-1167-405d-a809-0e36ce260e3d"
]
```



(1) The /orders endpoint returns a JSON array of order GUIDs.

  
#### Authentication

This section includes information about Toast API authentication functionality that is available but is expected to be removed or replaced.

##### Legacy API authentication (deprecated)



> **Important**
> 
> The API authentication endpoint and procedure described in this section is deprecated. Implement authentication for your Toast API integration using the endpoint and procedure described in [Authentication and restaurant access](authentication.html).


You get an authentication token by sending a `POST` request to the `/usermgmt/v1/oauth/token` resource of the Toast user management API. The following example shows the URL of the user management token endpoint.

```
https://`[toast-api-hostname]`/usermgmt/v1/oauth/token
```

You must include your client identifier and client secret string in the message body of a `POST` request for an authentication token. When the user management API determines that the client identifier and client secret string are valid, it returns an authentication token along with a set of data describing the way you can use it. You receive a client identifier (*`client_id`*) and client secret string (*`client_secret`*) when you register to use Toast APIs. For more information, see [Toast API accounts](apiClientAccounts.html).

To create the message body of an authentication request, concatenate your client identifier, client secret string, and the grant type (which is always *`grant_type=client_credentials`*) using the syntax for a set of query parameters:

- The `grant_type` is always *`grant_type=client_credentials`*.


- Include the client identifier in the *`client_id`* parameter.


- Include the client secret string in the *`client_secret`* parameter.





> **Important**
> 
> You must URL encode the values of each parameter to replace special characters that interfere with processing the string of query parameters.


The following example shows a concatenated string of the *`grant_type`*, *`client_id`*, and *`client_secret`* parameters.

```
grant_type=client_credentials&client_id=my-identifier&client_secret=XwEW%3C%3CvR*k6%3B%23Fp8
```



> **Note**
> 
> You must use query parameter syntax for API client credentials, even though you submit them in the message body of a `POST` authentication request.


The following **curl** command requests an authentication token from the `usermgmt/v1/oauth/token` resource. For more information about the curl utility, see [https://curl.haxx.se/](https://curl.haxx.se/).

```
curl -X POST \
-H "Content-Type: application/x-www-form-urlencoded" \
-d "grant_type=client_credentials&client_id=my-identifier&client_secret=XwEW%3C%3CvR*k6%3B%23Fp8" \
https://`[toast-api-hostname]`/usermgmt/v1/oauth/token

```

The return data that you receive depends on the type of Toast API client you are using. Toast APIs support partner clients and restaurant management group clients. For more information about the types of Toast API clients, see [Toast API accounts](apiClientAccounts.html).

The following sections provide information about the return data provided for authentication requests for different Toast API client types.

- [Authentication return data for a partner API client](apiDeprecatedApiFunctions.html#apiAuthenticationReturnDataPartnerLegacy)


- [Authentication return data for a restaurant management group API client](apiDeprecatedApiFunctions.html#apiAuthenticationReturnDataRestaurantLegacy)



###### Authentication return data for a partner API client



> **Important**
> 
> The API authentication endpoint and procedure described in this section is deprecated. Implement authentication for your Toast API integration using the endpoint and procedure described in [Authentication and restaurant access](authentication.html).


The user management API returns the following information for a successful authentication request using a partner API client. For more information about partner API accounts, see [Toast API accounts](apiClientAccounts.html).

- access_token - an encoded string that contains an authentication token. You must present this string when you make requests to other, secure Toast API resources.


- token_type - the OAuth 2 authentication scheme used for the authentication token. Toast API authentication uses the bearer authentication scheme.


- expires_in - the number of seconds that the authentication token is valid. For example, an authentication token might be valid for 3600 seconds after the user management API issues it.


- scope - a space-delimited list of Toast APIs that will accept the authentication token.

The user management API does not return a complete list of the Toast APIs that your client is authorized to use.


- jti - an identifier for the authentication token. You do not need to use the information in this field.


- namingAuthority - the name of your organization.


- `partnerGuid` - the Toast POS system unique identifier for the integration partner organization.



The following example shows the JSON data that the user management API returns for a successful authentication request using a partner API client.

**Example 1.14. Authentication return data for a partner API client**

```
{
   "access_token":"eyJhbGciOiJSUzI1NiJ9.eyJhdWQiOlsidG9hc3Q
iXSwibmFtaW5nQXV0aG9yaXR5IjoiVE9BU1RXRUIiLCJzY29wZSI6WyJhY2
Nlc3MtYWxsLXJlc3RhdXJhbnRzIiwiY2FyZHMiLCJjY3Byb2Nlc3NpbmciL
CJjY3Rvb2xpbmciLCJjcm0iLCJjcm0taW50ZXJuYWwiLCJkZXZpY2VzIiwi
ZmVhdHVyZS1mbGFncyIsImJhbGchbC1kYXRhIiwibGFJhbGcLWludGVybmF
sIiwib2F1dGgtY2xpZW50OnJlYWQiLCJwdXJnZSIsInNoYXJkLWJyYWluIi
wic3ZjbWdtdCIsInVzZXJtZ210Il0sImV4cCI6MTUzMjYxNzg2MCwianRpI
joiMGFlYjc4NzctMjRkZS00ZWJlLTg5NTYJhbGcYWNmN2JhNzRlIiwiY2xp
ZWJhbGckIjoidG9hc3R3ZWIifQ.iZsmlBiLo2BnpFikmb9G4rwJ6t3s7y5E
Ht-0nYo7tPV-qwRZKNfJDsjjXqGxey4SjgY3I4_TM5UcDDj5U7hoBNlqwlU
zqUJaoFgNHF273x0-dbRdt5_sagwLl5O7ufrCYTBQky5GASJK7GqhnNAIXb
iNTlbPVwAvrFTbEWcmys0",
   "token_type":"bearer",
   "expires_in":3600,
   "scope":"labor orders usermgmt",
   "jti":"0aeb7877-24de-4ebe-8956-0d4acf7ba74e",
   "namingAuthority":"USEFULRESTAURANSERVICE",
   "partnerGuid": "46a8dba9-b204-38bf-bd76-fb26d74bc513"
}
```

  
###### Authentication return data for a restaurant management group API client



> **Important**
> 
> The API authentication endpoint and procedure described in this section is deprecated. Implement authentication for your Toast API integration using the endpoint and procedure described in [Authentication and restaurant access](authentication.html).


The user management API returns the following information for a successful authentication request using a restaurant management group API client. For more information about restaurant management group API accounts, see [Toast API accounts](apiClientAccounts.html).

- access_token - an encoded string that contains an authentication token. You can present this string when you make requests to other, secure Toast API resources.


- expires_in - the number of seconds that the authentication token is valid. For example, an authentication token might be valid for 3600 seconds after the user management API issues it.


- jti - an identifier for the authentication token. You do not need to use the information in this field.


- namingAuthority - the name of your organization.


- rsGuid - the globally unique identifier (GUID) of the top-level unit in your restaurant chain. For example, this identifier might be for the parent unit for multiple restaurants, or for a single, independent restaurant.


- scope - a space-delimited list of Toast APIs that will accept the authentication token.

The user management API does not return a complete list of the Toast APIs that your client is authorized to use.


- token_type - the OAuth 2 authentication scheme used for the authentication token. Toast API authentication uses the bearer authentication scheme.



The following example shows the JSON data that the user management API returns for a successful request using a restaurant management group client.

**Example 1.15. Authentication return data for a restaurant management group client**

```
{
    "access_token": "eyJhbGciOiJSUzI1NiJ9ciOiJSUzI.e5nQXV0aG
9yaXR5IjoiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjyJhdWQiOlsidG9hc3QiX
SwibmFtaWE4YzQ5YWJlLWFllIjpbImxhYm9yIiwib3JkZXJzIiwidXNlcm1n
bXQiXSwiZXhwIjoxNODItNGFlYy04NDM1LWJhYTRjMjVlYTY2MiIsInNjb3B
Dg0Mzg5ODUwLCJqdGkiOiJlMDxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW
1lIn0YzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZDA.X18_lryUNHaEv
JdWq45F9gdOw2o6VSYTyZwooAJiFMDmN_0y9HzjSg7sddrGatj0xJzts3GJ8
uakbZrtiGJL3txKL1L-K2j1Enoq8An8hEUdYwLzuLwLpCMQzX5pKYtOqDUz_
cetM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28Td2wAR60xczlCF5rna
98RMLN6zY4ffjmljKFZ6QV0KkVppWjEiJn7oSp3Ix3fObxbrvanocx9_OT8S
9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b9bz1FtgOvrClhELxCe8dJy7jiFH
iIylCX1sYzd241Y-gwo007AMgxjH9",
    "expires_in": 3600,
    "jti": "e063f2d3-c4f2-4bf2-82f6-51855c3d013f",
    "namingAuthority": "MYORGANIZATION",
    "rsGuid": "18c49abe-4aec-a2e8-8543-baa4c25ea662",
    "scope": "labor orders usermgmt",
    "token_type": "bearer"
}

```

  
#### Guests

This section includes information about Toast API guest functionality that is available but is expected to be removed or replaced.

##### Working with guests (deprecated)

This section provides information about working with restaurant guest records in Toast APIs. You can use the Toast CRM (customer relations management) API to perform operations that affect restaurant guest records.



> **Important**
> 
> The CRM API is deprecated and will be replaced by future Toast API functionality. Before beginning development work using the CRM API, contact the Toast technical partnership team to make sure your integration plans are coordinated with upcoming API changes.


For general information about the way the Toast POS handles guest records, see [Guest data overview](adminGuestDataOverview.html).

The Toast POS creates customer records when:

- The POS processes takeout, delivery, and other types of orders that require customer information.


- Restaurant employees give customer credits for future check payments.


- The POS issues or imports gift or loyalty cards that require customer information.


- Other restaurant and POS operations that include customer information.



The following sections provide more information about working with customers.

- [Searching for guest records](apiDeprecatedApiFunctions.html#apiSearchingForCustomerRecords)


- [Adding a guest record](apiDeprecatedApiFunctions.html#apiAddingCustomerRecords)


- [Adding guest credits](apiDeprecatedApiFunctions.html#apiAddingCustomerCredits)



###### Searching for guest records

To find existing customer records in the Toast POS you send a `POST` request to the `/crm/v1/customers/search` endpoint of the CRM API.

You must include A JSON `CustomerSearchRequest` object containing a `CustomerSearchQuery` object in a `POST` request to search for existing customer records. The `CustomerSearchQuery` object includes information about the customer you are searching for. For example, if you are searching for a customer record with a telephone number, you submit a `POST` request including a message body that consists of a `CustomerSearchRequest` object with a `query` value containing a `CustomerSearchQuery`object. The `CustomerSearchQuery` object contains a `phone` value with the telephone number that you want to match.

The following example shows the message body for a `POST` request to the `/crm/v1/customers/search` endpoint.

**Example 1.16. Guest search query message body**

```
{
  "query": {
    "phone": "9876543210"
  }
}
```

  
###### Adding a guest record

To add a customer record to a restaurant and its restaurant group you send a `POST` request to the `/crm/v1/customers` endpoint of the CRM API. The `POST` request to the customers endpoint creates a customer record and returns a JSON `Customer` object containing the new customer information.

Before you add a customer record, you must make sure that the Toast POS does not have an existing customer record for the customer. The customers endpoint will create a new customer record each time you submit a successful POST request. To avoid duplicate customer records for the same restaurant customer you must:

**Before creating a new guest record**

1. Search for an existing customer record for the restaurant customer. For more information, see [Searching for guest records](apiDeprecatedApiFunctions.html#apiSearchingForCustomerRecords).


2. If one or more customer records match your search criteria, add customer credit or perform other customer-related operations on the existing customer record.


3. If no existing customer records match your search criteria, create a new customer record by sending a `POST` request to the `/crm/v1/customers` endpoint of the CRM API.



To create a customer record, you must provide a unique identifier (UUID or GUID) for the customer. The `Customer` object in the message body of the `POST` request must include a `guid` value containing a unique UUID or GUID for the new customer record.

The following example shows the JSON message body content for a `POST` request to the `/crm/v1/customers` endpoint.

**Example 1.17. Message body content to add a guest**

```
{
  "guid": "743B0D5C-66E4-4A46-B3E2-6694031B180C",[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e1648E813524-E4E5-4A3C-A9B0-E4D395D37745-co)
  "firstName": "Josephine",[(2)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e1668E813524-E4E5-4A3C-A9B0-E4D395D37745-co)
  "lastName": "Banton",[(3)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e1688E813524-E4E5-4A3C-A9B0-E4D395D37745-co)
  "email": "jbanton@example.org"[(4)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e1708E813524-E4E5-4A3C-A9B0-E4D395D37745-co)
}
```



(1) Generate a unique identifier for the customer (UUID or GUID). Include the identifier in the guidvalue.

(2) Include a first name, or given name, for the customer.

(3) Include a last name, or family name, for the customer.

(4) You must include either an email address (shown) or a telephone number for the customer.

  
The following example shows the JSON response data for a `POST` request to the `/crm/v1/customers` endpoint.

**Example 1.18. Add guest response data**

```
{
  "guid": "743b0d5c-66e4-4a46-b3e2-6694031b180c",
  "entityType": "Customer",
  "firstName": "Josephine",
  "lastName": "Banton",
  "phone": null,
  "email": "jbanton@example.org"
}
```

  
###### Adding guest credits

To add customer credit value for a restaurant customer, you send a `POST` request to the `/crm/v1/`/customers/*`{customerId}`*/creditTransactions endpoint of the CRM API. Adding customer credit value creates a customer credit transaction.

To create a customer credit transaction, you must provide a unique identifier (UUID or GUID) for the transaction. The `CustomerCreditTransaction` object in the message body of the `POST` request must include a `guid`value containing a unique UUID or GUID for the new customer record.

The following example shows the JSON message body content for a `POST` request to the `/crm/v1/`/customers/*`{customerId}`*/creditTransactions endpoint.

**Example 1.19. Message body content to add guest credit value**

```
{
  "guid": "65F15E87-F985-4AE4-B970-04CF5F758C17",[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e305E3AAA573-E85E-49CD-80EE-85E18B5086BE-co)
  "transactionType": "ADD_VALUE",[(2)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e307E3AAA573-E85E-49CD-80EE-85E18B5086BE-co)
  "amount": 10.00,[(3)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e309E3AAA573-E85E-49CD-80EE-85E18B5086BE-co)
  "localCreatedDate": "2018-06-16T15:01:14.000+0000"[(4)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e311E3AAA573-E85E-49CD-80EE-85E18B5086BE-co)
}
```



(1) Generate a unique identifier for the customer credit transaction (UUID or GUID). Include the identifier in the guid value.

(2) Include the ADD_VALUE value when you add customer credit value in a transaction.

(3) Include the currency amount of the customer credit transaction in the amount value.

(4) Include the date and time that you added customer credits in the localCreatedDate value.

  
The following example shows the JSON response data for a `POST` request to the `/crm/v1/`/customers/*`{customerId}`*/creditTransactions endpoint.

**Example 1.20. Add guest credit transaction response data**

```
{
  "guid": "65f15e87-f985-4ae4-b970-04cf5f758c17",
  "entityType": "CustomerCreditTransaction",
  "approver": null,
  "note": null,
  "server": null,
  "amount": 10.01,
  "restaurant": {
    "guid": "76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf",
    "entityType": "Restaurant"
  },
  "transactionDate": "2018-06-16T19:01:14.488+0000",
  "transactionType": "ADD_VALUE",
  "familyGuid": null,
  "localCreatedDate": "2018-06-16T15:01:14.000+0000",
  "device": null,
  "expirationDate": "2018-09-15T06:00:00.000+0000",
  "customer": {
    "guid": "f7111e82-5979-4579-a86b-e91d10ee6d3a",
    "entityType": "Customer"
  }
}
```

  
#### Menus

This section includes information about Toast API menu functionality that is available but is expected to be removed or replaced.

##### Getting menu information from the menu data export (deprecated)



> **Important**
> 
> The menus API has replaced the the menu data export as the preferred mechanism for retrieving menu data for a restaurant. It is described in the [Menus API overview](apiGettingMenuInformationFromTheMenusAPI.html) section. This section remains for customers who have not yet transitioned to using the menus API for menu data retrieval, however, the export functionality will be deprecated at some point in the future and this section will be removed.


You can get detailed information about the menus configured for your restaurant from the menu data export file. The Toast POS system generates data export files once a day and makes them available for downloading. This section provides information about downloading data export files and understanding the values in menu data export files.

###### Downloading data export files

The Toast platform stores data export files for seven days, and then they are deleted. When data exports are enabled for your restaurant, the following items are needed to retrieve your files: 

- SFTP User name: This is provided by Toast support.


- SSH key: For more information about generating an SSH key, and where to enter this in Toast Web, see [SSH keys](adminSshKeys.html).


- Server URL: To locate the appropriate Server URL, navigate to Reports > Settings > SSH Keys from the Toast Web. Locate your SFTP username and find the Server URL.



Export IDs can also be obtained from Toast Web. Navigate to Reports > Settings > Data Exports and click the link in the banner at the top of the screen, view restaurant # mapping to export a file that includes an Export ID column which includes the ID for each restaurant.

![Image](https://doc.toasttab.com/doc/media/export_ids_data_export.png)



Prior to downloading data export files, ensure that you have [added an SSH key](adminSshKeys.html) to Toast Web. The following examples describe how to connect to your SFTP directory for use with the macOS™ terminal and Windows™ command prompt. For information about how to export files using a third party FTP solution see this [Toast Central article.](https://central.toasttab.com/s/article/Automated-Nightly-Data-Export-1492723819691)

###### Accessing your SFTP directory using macOS terminal

1. **Connect to your SFTP directory**

To access your restaurant's SFTP directory using terminal use the following command:

```
sftp \ 
      -i ~/`{SSH_key_filepath}` \
      -r `{sftp_username}`@s-9b0f88558b264dfda.server.transfer.us-east-1.amazonaws.com:`{export_id}`/`{YYYYMMDD}`/*
```

Replace the *`{sftp_username}`* and *`{export_id}`* placeholders with the details you received from Toast support. Change *`{YYYYMMDD}`* to the business date of the desired export within the last seven days and the *`{SSH_key_filepath}`* to the location of your SSH key on your machine.



> **Note**
> 
> The *`{filepath}`* used will be the export directory for your restaurant files.



2. **Exporting files using terminal**

Once you are connected to the SFTP directory use the **ls** command and press Return to display all files.

Export all files using the **get *** command or use **get *`{fileName}`*** to export a specific file.



###### Accessing your SFTP directory using Windows command prompt

1. **Connect to your SFTP directory**

To access your restaurant's SFTP directory using command prompt use the following command:

```
sftp -i `{SSH_key_filepath}` -r `{sftp_username}`@s-9b0f88558b264dfda.server.transfer.us-east-1.amazonaws.com
```

Replace *`{SSH_key_filepath}`* with the location of your SSH key on your machine. Replace *`{export_username}`* with the export user name you received from Toast support.


2. **Exporting files using command prompt**

Once you are connected to the SFTP directory, use the **ls** command and press Enter to display all files.

To export a file for a specific location and date, use the following command:

```
get /`{export_id}`/`{YYYYMMDD}` `{download_location}`
```

Replace *`{export_id}`* with the export ID you received from Toast support. Change *`{YYYYMMDD}`* to the business date of the desired export within the last seven days. Replace *`{download_location}`* with the location on the local file system where you want the downloaded files to be stored.

To export all files, use the following command:

```
get * `{download_location}`
```



###### Menu Data Export Values

The menu data export includes two types of information:

- Information about each menu item at your restaurant.


- Information about the premodifiers and postmodifiers created at your restaurant.



The file name of the menu data export is `MenuExport_`[export file
  identifier]`.json`. The menu data export is in JavaScript Object Notation (JSON) format. For information about downloading data export files, see [Downloading data export files](apiDeprecatedApiFunctions.html#downloading-data-export-files).



> **Note**
> 
> The JSON format of the menu data export is significantly different than the spreadsheet formats of other Toast POS data exports. JSON is optimized for use by software and the menu data export is intended to assist in integration with Toast POS API clients.


###### Menus

This section describes information about each menu entity at your restaurant.

###### Menu

The following table shows the information about each menu at your restaurant from from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu object is `Menu`. | String | 
| name | A descriptive identifier for the menu. For example, `Food` or `Drinks`. | String | 
| guid | The unique identifier for the menu, assigned by the Toast POS. | String | 
| description | A written description of the menu. | String | 
| groups | A JSON array of [MenuGroup](apiDeprecatedApiFunctions.html#menuExportMenugroup) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| orderableOnline | Indicates whether the menu is available for online ordering. Valid values are `true` and `false`. This field is a Boolean version of the orderableOnlineStatus field. | Boolean | 
| orderableOnlineStatus | Indicates whether the menu is available for online ordering. Valid values are `YES` and `NO`. This field is a string version of the orderableOnline field. | String | 
| visibility | Indicates where the menu is displayed and who can see it. Values are:- `ALL` - The menu is visible to everyone. For example, the menu is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu is hidden from everyone.

 | String | 
| startTime | The time of day when a time-based menu becomes available. The value is in milliseconds (for example, `41400000`) since the start of the restaurant's day (the day starts at `0`). When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field. | Int | 
| endTime | The time of day when a time-based menu stops being available. The value is in milliseconds (for example, `57600000`) since the start of the restaurant's day (the day starts at `0`). When converted to 24-hour clock time, the result should be the same as the endTimeHHmm field. | Int | 
| startTimeHHmm | The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, `15:45`). This value is a conversion of the startTime field to a more readable format (the day starts at `00:00`). | String | 
| endTimeHHmm | The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, `19:35`). This value is a conversion of the endTime field to a more readable format (the day starts at `00:00`). | String | 
| startTimeLocalStandardTime | The time of day when a time-based menu becomes available. The value is in milliseconds since the start of the restaurant's day (the day starts at `0`). The value adds the restaurant timezone's offset (for example, -5 hours in a `23400000` value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field. | Int | 
| endTimeLocalStandardTime | The time of day when a time-based menu stops being available. The value is in milliseconds since the start of the restaurant's day (the day starts at `0`). The value adds the restaurant timezone's offset (for example, -5 hours in a `36900000` value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeLocalStandardTime field. | Int | 
| startTimeHHmmLocalStandardTime | The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, `15:45`). This value is a conversion of the startTimeLocalStandardTime field to a more readable format (the day starts at `00:00`). | String | 
| endTimeHHmmLocalStandardTime | The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, `19:35`). This value is a conversion of the endTimeLocalStandardTime field to a more readable format (the day starts at `00:00`). | String | 
| availableAllTimes | Indicates whether the menu is available at all times of the day. If the value is `false`, then the startTime* fields and the endTime* fields list when this time-based menu is available. | Boolean | 
| availableAllDays | Indicates whether the menu is available each day of the week. | Boolean | 
| daysAvailableString | A JSON array of strings that lists the days of the week when the menu is available. The days are listed in an abbreviated format, such as `Sun` or `Thurs`.In this example, the menu is available on all days except for Sunday and Saturday:```
"daysAvailableString": [
   "Mon",
   "Tues",
   "Wed",
   "Thurs",
   "Fri"
]
```

 | JSON array | 
| daysAvailableBits | This field is a numeric version of the daysAvailableString field and is for Toast internal use only. | Int | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 

###### MenuGroup

The following table shows the information about each menu group at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu object is `MenuGroup`. | String | 
| name | A descriptive identifier for the menu group. For example, `Appetizers` or `Entrees`. | String | 
| guid | The unique identifier for the menu group, assigned by the Toast POS. | String | 
| description | A written description of the menu group. | String | 
| subgroups | An array of other `MenuGroup` objects. For example, `Red Wine` is the menu group and it has the subgroups `By the Glass` and `By the
              Bottle`. | JSON array | 
| items | An array of [MenuItem](apiDeprecatedApiFunctions.html#menuExportMenuitem) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 
| orderableOnline | Indicates whether the menu group is available for online ordering. | Boolean | 
| visibility | Indicates where the menu group is displayed and who can see it. Values are:- `ALL` - The menu group is visible to everyone. For example, the menu group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu group is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu group is hidden from everyone.

 | String | 

###### MenuItem

The following table shows the information about each menu item at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu item object is `MenuItem`. | String | 
| name | A descriptive identifier for the menu item. For example, `Caesar Salad` or `Lemonade`. | String | 
| guid | The unique identifier for the menu item, assigned by the Toast POS. | String | 
| description | A written description of the menu item. | String | 
| sku | The stock keeping unit (SKU) identifier for the item. | String | 
| plu | The price lookup (PLU) code for the item. | String | 
| maxSelections | This value only applies to items in a [MenuOptionGroup](apiDeprecatedApiFunctions.html#menuExportMenuoptiongroup)object. | Integer | 
| price | The amount of money that the item costs, expressed in U.S. dollars. All currency in Toast is treated the same and uses the dollar symbol $. There is no conversion between currency. | Currency | 
| prices | An array of menu-specific prices for the item. If an item is included in more than one menu, it can have different prices on each menu. For example, if you have a Lunch menu and a Dinner menu, a menu item can belong to both menus and have one price for the Lunch menu and a higher price for the Dinner menu. | JSON array | 
| isDefault | Whether or not the item is selected unless a customer chooses to decline it. | Boolean | 
| optionGroups | An array of [MenuOptionGroup](apiDeprecatedApiFunctions.html#menuExportMenuoptiongroup) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| itemGroupGuid | The unique identifier of the menu group to which this menu item belongs. | String | 
| calories | The caloric value for this menu item. The value can be any positive or negative integer, or zero. | Integer | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 
| orderableOnline | Indicates whether the menu item is available for online ordering. | Boolean | 
| visibility | Indicates where the menu item is displayed and who can see it. Values are:- `ALL` - The menu item is visible to everyone. For example, the menu item is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu item is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu item is hidden from everyone.

 | String | 

###### MenuOptionGroup

The following table shows the information about each menu option group, or modifier group, at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu option group object is `MenuOptionGroup`. | String | 
| name | A descriptive identifier for the menu option group. For example, `Substitutions` or `Extras`. | String | 
| guid | The unique identifier for the menu option group, assigned by the Toast POS. | String | 
| minSelections | The minimum number of options that a customer can choose from the menu option group. If a server must make a selection from the menu option group, the value is `1`. For example, a menu item might require that a customer choose an option from a menu option group that specifies the level of doneness. | Integer | 
| maxSelections | The maximum number of options that a customer can choose from the menu option group. If a customer can choose an unlimited number of options from a menu option group, the value is `null`.As an example of a menu option group with a maximum greater than one, assume this configuration:```
Group: Cheese
Items: ( Cheddar, American, Swiss )
maxSelections: 2
minSelections: 1
```

This means:- You can select AT MOST two different cheeses from this group to apply on the item (the `maxSelections` value).
- You must select AT LEAST one cheese from this group to apply on the item (the `minSelections`value).

 | Integer or null | 
| pricingMode | Indicates how the options in the menu option group affect the price of the menu items they are applied to. Values are:- `ADJUSTS_PRICE` - Choosing an option from the menu option group affects the price of the menu item it applies to. The amount of the adjustment depends on the price of the option applied.
- `FIXED_PRICE` - Choosing an item from the menu option group affects the price of the item it applies to. The amount of the adjustment is set at the menu option group level and applies to all options in the group. Note that this does not necessarily mean that all options in the group have an identical price. It means that all options in the group are treated the same way with respect to pricing. For example, if the menu option group uses sequence pricing, and the first two options are free while the third is $1, the specific modifier that costs $1 is arbitrary. Fixed refers to the fact that the pricing is fixed at the modifier group level, not that the price of each option in the group is constant.
- `INCLUDED` - Choosing an option from the menu option group does not affect the price of the menu item it applies to (because the price of the option is included in the price of the menu item it applies to).

 | String | 
| pricingStrategy | Indicates the way prices are set for the options in this menu option group. Values are:- `NONE` - Indicates that no pricing strategy is defined for this menu option group. `pricingStrategy` is set to `NONE`if the [pricingMode](apiDeprecatedApiFunctions.html#adminDataExportPricingModeModifierGroup)is set to `ADJUSTS_PRICE` (prices are set on individual items in the menu option group, not on the menu option group itself, so there is no pricing strategy for the menu option group as a whole) or `INCLUDED`(no additional cost is charged for the options in the menu option group).
- `BASE_PRICE` - The pricing strategy for the menu option group is a constant price that does not change based on other conditions (such as size, sequence of ordering, and so on). For example, all of the options in the menu option group cost $1 at all times.
- `SEQUENCE_PRICE` - The pricing strategy for the menu option group is Sequence Price. With sequence pricing, the order in which options are specified determines the cost of each option, for example, the first option costs $1.00, the second costs $1.50, and the third costs $1.75.
- `UNSUPPORTED_STRATEGY` - The pricing strategy for the menu option group is one that, while it is supported internally in the Toast POS system, it is not yet supported for use via API. Currently, two pricing strategies are unsupported by the API, Size Price and Size/Sequence Price.

 | String | 
| pricingStrategyRules | An [object](apiDeprecatedApiFunctions.html#menuExportPricingStrategyRules) that contains the pricing rules for the chosen [pricingStrategy](apiDeprecatedApiFunctions.html#adminDataExportPricingStrategyModOptionGroup). If the pricing strategy is `NONE` or `UNSUPPORTED_STRATEGY`, this object is set to `NONE`. | JSON object | 
| defaultOptionsChargePrice | Indicates whether the prices associated with the menu option group's default options are added to the cost of the menu items they modify. Values are:- `NO` - The option price is ignored. No change is made to the cost of the menu item.
- `YES` - The option price is added to the cost of the menu item.

 | String | 
| defaultOptionsSubstitutionPricing | Indicates whether substitution pricing is enabled for the menu options group. Values are:- `NO` - Substitution pricing is not enabled. Removing a default option from a menu item has no impact on the price of the menu item.
- `YES` - Substitution pricing is enabled. Substitution pricing allows a guest to remove one or more default options from a menu item and apply the value of those options toward the purchase of one or more different options. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the chicken. The price of the chicken option is $7. The price of the salmon option is $9. In this case, the Toast POS system calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).

There are two scenarios that can occur with substitution pricing:- If the substitution options cost the same as or less than the default options, then no price adjustments occur. The menu item costs the same as it does with the default options.
- If the substitution options cost more than the default options, then the Toast POS system calculates the difference in price and reprices the substitution options accordingly. For example, if you remove a default option that costs $10 and replace it with two options that cost $8 and $7, then the cost of the replacement options is $5 ($8 + $7 - $10 = $5).

 | String | 
| items | An array of the objects that represent the options in the menu option group. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| visibility | Indicates where the menu option group is displayed and who can see it. Values are:- `ALL` - The menu option group is visible to everyone. For example, the menu option group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu option group is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu option group is hidden from everyone.

 | String | 

###### PricingStrategyRules

The following table shows the information about the pricing strategy for the modifier groups at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| basePrice | Used when the [pricingStrategy](apiDeprecatedApiFunctions.html#adminDataExportPricingStrategyModOptionGroup)is set to `BASE_PRICE`. Defines a constant price for all of the options in the menu options group. For example:```
"optionGroups": [ 
{
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy":"BASE_PRICE",
  "pricingStategyRules": {
    "basePrice": 1.00
    }
  ...
}
```

 | Number | 
| numberOfLevels | Used when the [pricingStrategy](apiDeprecatedApiFunctions.html#adminDataExportPricingStrategyModOptionGroup)is set to `SEQUENCE_PRICE`. Defines the number of levels for the sequence price. For example, if you have three levels, you can set a price for the first option added to the order, the second option added to the order, and all options added from the third option on. Used in conjunction with the [sequencePrices](apiDeprecatedApiFunctions.html#adminDataExportSequencePrices)array. | Number | 
| sequencePrices | Sets the price for each level defined in the [numberOfLevels](apiDeprecatedApiFunctions.html#adminDataExportNumberOfLevels)value. For example:```
"optionGroups": [ 
{
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy": "SEQUENCE_PRICE",
  "pricingStrategyRules": {
    "numberOfLevels": 3,
    "sequencePrices": [
      0.50,
      0.75,
      1.00,
    ]
  }
  ...
}
```

 | JSON array | 

###### Premodifiers and postmodifiers

This section describes:

- `premodifierGroup` objects. Each premodifier group contains a group of `premodifier` objects.


- `premodifier` objects. Each premodifier can be a premodifier or postmodifier item.



###### premodifierGroups

The following table shows the information about the premodifier groups at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| name | A descriptive identifier for a `premodifierGroup` object. | String | 
| guid | The unique identifier for the premodifier group, assigned by the Toast POS. | String | 
| isDefault | Whether or not the item is selected unless a customer chooses to decline it. | Boolean | 
| premodifiers | An array of [premodifiers](apiDeprecatedApiFunctions.html#menuExportPremodifier) objects. | JSON array | 

###### premodifiers

The following table shows the information about the premodifiers or postmodifiers at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| name | A descriptive identifier for a specific premodifier or postmodifier in a `premodifiers` object. For example, `ADD` or `ON
              SIDE`. | String | 
| guid | The unique identifier for the premodifier or postmodifier, assigned by the Toast POS. | String | 
| basePrice | If `scalePrice` is `false`, this amount is added to the price. Note that the amount can be 0.00 (so that the price remains the same) and it can also be a negative value (which will reduce the price). | Currency | 
| scalePrice | Determines how the price is scaled. Values are:- `true` - multiplies the price by the `scaleFactor` value.
- `false` - does not multiply the price but instead adds the `basePrice` value to the item.

 | Boolean | 
| scaleFactor | If `scalePrice` is `true`, the item price is multiplied by this factor. | Number | 
| displayMode | Determines the modifier type. Values are:- `PREFIX` - specifies a premodifier. This means the name of this premodifier is displayed as a prefix before the name of the modifier. For example, if the modifier is named `Bacon` and the premodifer is named `ADD`, the full display will be `ADD Bacon`.
- `SUFFIX` - specifies a postmodifier. This means the name of this premodifier is displayed as a suffix after the name of the modifier. For example, if the modifier is named `Bacon` and the postmodifer is named `ON SIDE`, the full display will be `Bacon ON SIDE`.

 | String | 

###### Finding the default modifiers for a menu item

When you create an order using the orders API, you must include all of the default modifiers for each menu item selection. If you omit a default modifier, the orders API will not apply it to the menu item. You can find the default modifiers for a menu item in the menu data export file for your restaurant. For general information about the menu data export file, see [Getting menu information from the menu data export (deprecated)](apiDeprecatedApiFunctions.html#apiMenuInformationMenuDataExport).

The menu data export file contains a JSON representation of the menus configured for your restaurant. The nested hierarchical structure of the JSON matches the structure of your menus. For example, a menu JSON object contains menu group objects, which contain menu item objects. The `optionGroups` value for a menu item includes `MenuOptionGroup` objects for the types of modifier that you can apply to the item. The `MenuItem` objects in the items value of the `MenuOptionGroup` object are the modifier menu items that you can apply. For example, a salad menu item might have a toppings menu option group that contains menu items such as tomatoes or onions that you can apply as modifiers. The `MenuItem` objects in a `MenuOptionGroup` include an `isDefault` value to indicate whether or not the modifier item is a default modifier for the menu item.

The following example shows a menu, menu group, menu item, and modifier menu items in the JSON menu data export file.

**Example 1.21. Menu hierarchy in the menu data export file**

```
{
  "entityType": "Menu",
  "name": "Dinner",
  "guid": "7d9e0d3d-b844-4133-943a-4b8d0c160786",
  "groups": [
    {
      "entityType": "MenuGroup",
      "name": "Salads",
      "guid": "bd56a9b4-89c4-4105-bd8e-cdd5d95a1e3c",
      "items": [
        {
          "entityType": "MenuItem",
          "name": "Garden Salad",
          "guid": "ca6c1271-6efb-470e-aa95-da4380d6bf62",[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e465A2FDFF6-1785-406C-970F-4C5331B7DDF8-co)

          [contents omitted]

          "optionGroups": [[(2)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e485A2FDFF6-1785-406C-970F-4C5331B7DDF8-co)
            {
              "entityType": "MenuOptionGroup",
              "name": "Toppings",
              "guid": "be8ff99e-8cfe-4641-88ef-6f4f32d00535",[(3)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e505A2FDFF6-1785-406C-970F-4C5331B7DDF8-co)

              [contents omitted]

              "items": [
                {
                  "entityType": "MenuItem",
                  "name": "Banana peppers",
                  "guid": "3ad58e65-6daf-4c51-90ef-1af45bc33ac3",

                  [contents omitted]

                  "isDefault": false,[(4)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e525A2FDFF6-1785-406C-970F-4C5331B7DDF8-co)
                },
                {
                  "entityType": "MenuItem",
                  "name": "Tomatoes",
                  "guid": "c95060c2-5aa6-44b2-a9d2-b2c1f01468ac",

                  [contents omitted]

                  "isDefault": true,[(5)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e545A2FDFF6-1785-406C-970F-4C5331B7DDF8-co)
                },
          
    [contents omitted]
               
```



(1) The GUID of a menu item.

(2) The optionGroups value contains information about the groups of items that you can apply as modifiers.

(3) The GUID of one group of modifier menu items.

(4) This item is not a default modifier for the menu item.

(5) This item is a default modifier for the menu item.

  
The following example shell script uses a **jq**command to select the default modifiers for a menu item from the menu data export file for a restaurant. For more information about the **jq** utility, see the [jq web site](https://stedolan.github.io/jq/).

**Example 1.22. Using the jq utility to find the default modifiers for a menu item**

```
#!/bin/bash

MENU_EXPORT_FILE="MenuExport_5c2dad3f-1b13-5be3-bc52-d132244153c5.json"[(1)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e31A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)

MENU_GUID="315267d2-80fd-4aef-95aa-62adf41bdb7a"[(2)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e33A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)
MENU_GROUP_GUID="974c43f7-a357-4bef-92aa-00a1238e22e1"[(3)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e35A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)
MENU_ITEM_GUID="dc426c22-e132-4adf-4adf-d82b1fe512b3"[(4)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e37A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)

jq --arg MENU_GUID ${MENU_GUID} \[(5)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e39A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)
--arg MENU_GROUP_GUID ${MENU_GROUP_GUID} \
--arg MENU_ITEM_GUID ${MENU_ITEM_GUID} \
'.[] | select(.guid==$MENU_GUID) | .groups[] | select(.guid==$MENU_GROUP_GUID)
| .items[] | select(.guid==$MENU_ITEM_GUID) | .optionGroups[].items[] 
| select(.isDefault==true)' \[(6)](apiDevGuide-apiDeprecatedApiFunctions.html#d1e42A5DAB7DB-524E-4BD7-B772-27EB69622FF0-co)
${MENU_EXPORT_FILE}
```



(1) The menu data export file contains a JSON representation of the menus configured for your restaurant. For general information about the menu data export file, see Getting menu information from the menu data export (deprecated).

(2) To find the default modifiers for a menu item, you locate the item in the menu and menu group that contain that contain it. This variable stores the GUID of the menu that contains the item.

(3) This variable stores the GUID of the menu group that contains the item.

(4) This variable stores the GUID of the menu item that this example script finds the default modifiers for.

(5) This jq command filters the JSON contents of the menu data export file. For more information about the jq utility command syntax, see the jq web site.

(6) These jq command filters select one menu item from its menu and menu group. It then selects each menu item in the optionGroup array for that menu item if the isDefault value for the optionGroup is true.

  
The following example shows menu items that are the default modifiers for a menu item. These menu item objects were filtered from the menu data export file for a restaurant using the jq command shown in [Example 1.22, “Using the jq utility to find the default modifiers for a menu item”](apiDeprecatedApiFunctions.html#apiUsingJqToFindDefaultModifiers).

**Example 1.23. Default modifiers for a menu item**

```
{
  "entityType": "MenuItem",
  "name": "Cucumber",
  "guid": "e47b25f2-2c13-4428-b344-34b3214515d1",
  "description": "",
  "sku": null,
  "plu": null,
  "maxSelections": null,
  "price": 0,
  "isDefault": true,
  "optionGroups": [],
  "idString": null
}
{
  "entityType": "MenuItem",
  "name": "Green Peppers",
  "guid": "f9ec9a05-5c60-42dc-ad17-db0fb6be93c7",
  "description": "",
  "sku": null,
  "plu": null,
  "maxSelections": null,
  "price": 0,
  "isDefault": true,
  "optionGroups": [],
  "idString": null
}
{
  "entityType": "MenuItem",
  "name": "Onions",
  "guid": "ececb63f-0491-4955-9331-4ad2cd685e60",
  "description": "",
  "sku": null,
  "plu": null,
  "maxSelections": null,
  "price": 0,
  "isDefault": true,
  "optionGroups": [],
  "idString": null
}
{
  "entityType": "MenuItem",
  "name": "Tomato",
  "guid": "cb5dc6ee-2c25-4fcc-aff8-8452c9bf19e1",
  "description": "",
  "sku": null,
  "plu": null,
  "maxSelections": null,
  "price": 0,
  "isDefault": true,
  "optionGroups": [],
  "idString": null
}
{
  "entityType": "MenuItem",
  "name": "Garlic Croutons",
  "guid": "17831034-c2bc-4cca-b845-c52f441955be",
  "description": "",
  "sku": null,
  "plu": null,
  "maxSelections": null,
  "price": 0,
  "isDefault": true,
  "optionGroups": [],
  "idString": null
}
```

  
##### Menu entity visibility enhancements (rolled out)

The following sections describe changes to the visibility settings for menu entities (menus, menu groups, menu items, modifier groups, modifier options and their underlying item references). Visibility settings control where a menu entity is visible and, by extension, available for ordering. For example, visibility settings control whether an entity can be ordered on a Toast POS device, on a Toast Kiosk, via a restaurant's Toast online ordering website, or via a restaurant's integration with another online ordering system.

Previously, a menu entity's visibility was controlled by several, separate settings in Toast Web. The visibility changes described in this release note:

- Make the settings easier to understand and more intuitive to use by combining them into one cohesive set of configuration options with better labeling.


- Allow a restaurant to specify which menu entities are visible on a restaurant's Toast Online Ordering website, which are visible on online ordering websites that integrate with the Toast POS system using the orders API, and which are visible on both.


- Allow a restaurant to specify that a menu entity is visible on a restaurant's Toast Online Ordering website but not on a Toast POS device. Previously, in order for an entity to be available on Toast online ordering, it had to also be available on Toast POS devices.



To support the new visibility functionality, user interface changes have been made to the menu entity details pages in Toast Web and a set of corresponding changes have been made to the menus and configuration APIs. More information is provided about these UI and API changes in the [Understanding the new visibility behavior](apiDeprecatedApiFunctions.html#apiUnderstandingTheNewVisibilityBehavior) section.

If you are an online ordering partner, the visibility changes require that you:

- Use the `visibility` array available in the menus API for each menu entity to determine if the menu entity should be visible on your ordering web site. See [Understanding the new visibility behavior](apiDeprecatedApiFunctions.html#apiUnderstandingTheNewVisibilityBehavior) for details.


- Stop using the `visibility` and `orderableOnline` values on the `Menu`, `MenuGroup`, and `MenuItem` objects in the configuration API. While these values will continue to exist for a short period so that integrations do not break, they will be populated differently after 2020-05-25 and integrations that use them will potentially see unexpected behavior after this date.



To allow you to develop against the new `visibility` array, the sandbox environment now includes both Toast Web configuration options and the API changes, while the production environment includes the API updates only. This will allow you to set the configuration options in sandbox and develop and test against them, and then move your code to production in preparation for when restaurants will begin using the new configuration options. On 2020-05-25, the new visibility configuration options will become available to restaurants in the production environment. This is the date after which your partner restaurants may start using them and your integration must be able to handle the new API in the production environment.



> **Note**
> 
> To conserve the use of system resources, the menus API service only generates the JSON that it returns when a menu-related change has been made and published. This means that, when a restaurant makes changes to its menu visibility settings in Toast Web after 2020-05-25, they will have to publish those changes before the menus API can return them to your integration.


- [Understanding the new visibility behavior](apiDeprecatedApiFunctions.html#apiUnderstandingTheNewVisibilityBehavior)


- [Understanding the Grubhub enumeration](apiDeprecatedApiFunctions.html#apiUnderstandingTheGrubhubEnumeration)



###### Understanding the new visibility behavior

To understand the visibility changes, it is helpful to understand the old behavior. Previously, menu entities in the Toast POS system had several configuration options in Toast Web for controlling where an entity was visible and available for ordering. On the menu entity details pages, those settings look liked this:

![Image](https://doc.toasttab.com/doc/media/original-visibility-settings.png)

And this:

![Image](https://doc.toasttab.com/doc/media/show-on-kiosk.png)



> **Note**
> 
> The Grubhub setting was only visible at Toast POS system restaurants that used a legacy Grubhub integration, so not all restaurants would have seen this option.


These original settings were represented in the menus API by a `visibility` array that was included for each menu entity. A menu entity's `visibility` array would contain various combinations of the following enums, depending on how the menu entity was configured:

- `POS`: The menu entity is visible in the Toast POS app.


- `TOAST_ONLINE_ORDERING`: The menu entity is visible on the Toast Online Ordering site for this restaurant.


- `KIOSK`: The menu entity is visible on a Toast Kiosk device.


- `GRUBHUB`: The menu entity is included during a menu sync to Grubhub and will be visible on the Grubhub online ordering service after a menu sync has completed.



Grubhub was the only online ordering integration that the menus API's `visibility` array explicitly identified. In other words, you could tell if a menu entity should be visible on the Grubhub online ordering site by using the `GRUBHUB` enum, but no equivalent indicator existed for other online ordering integrations.

The configuration API is older and it treats orderable online and visibility as two separate concepts. In the configuration API, the original menu visibility settings were represented by:

- An `orderableOnline` value on the `Menu`, `MenuGroup`, and `MenuItem` objects that could be set to `Yes` or `No`. Some integrations used this value to determine whether a menu entity should be included in an online ordering integration.


- A `visibility` value on the `Menu`, `MenuGroup`, and `MenuItem` objects. All of the values in this array, however, were related to the visibility of a menu entity on a Toast POS device and had no bearing on whether an entity could be ordered online or not.



The Grubhub and Show on Kiosk configuration options were not represented in the configuration API.

As stated earlier, the menu visibility enhancements combine the original visibility settings into one cohesive set of options with better, more intuitive labeling. The following illustration shows the new combined settings, which all reside in the Visible Toconfiguration option on a menu entity's details page:

![Image](https://doc.toasttab.com/doc/media/visible-to-config-options.png)

These configuration options have a one-to-one relationship with an enum in the `visibility` array that the menus API returns for each menu entity. The table below describes the behavior of each option and defines the enum used to represent it in the `visibility`array:

| Configuration option | Menus API Visibility Array Enum | Description | 
| --- | --- | --- |
| In-store orders: POS | `POS` | The menu entity is visible on a Toast POS device. | 
| In-store orders: Kiosk | `KIOSK` | The menu entity is visible on a Toast Kiosk device. | 
| Online orders: Toast | `TOAST_ONLINE_ORDERING` | The menu entity is visible on a restaurant's Toast online ordering site. | 
| Online orders: Ordering partners | `ORDERING_PARTNERS` | The restaurant wants the menu entity to be visible on online ordering sites that integrate with the Toast POS system using the orders API. | 

To sum up, the effect of these changes for online ordering partners are as follows:

- Ordering partner integrations should no longer use the `orderableOnline` value in the configuration API to determine if a menu entity should be visible on their online ordering site. Instead, an online ordering integration should inspect the `visibility` array that the menus API returns for all menu entities for the existence of the `ORDERING_PARTNERS` enum and only display menu entities where that enum exists. The Toast technical integrations team also recommends that partners discontinue using the configuration API for retrieving any menu-related data and use the menus API instead.


- If your ordering partner integration used the `TOAST_ONLINE_ORDERING` enum in the menus API `visibility` array to determine if a menu entity should be available on your ordering site, you must switch to using the `ORDERING_PARTNERS` enum instead. The `TOAST_ONLINE_ORDERING` enum is now used exclusively to indicate a menu entity's availability on a restaurant's Toast online ordering site. Only menu entities whose `visibility` array includes the `ORDERING_PARTNERS` enum should be shown on ordering partner web sites.





> **Note**
> 
> For historical reasons, modifier groups currently do not have the Online orders: Toast option in the Visible To settings in Toast Web. This omission does not affect partner implementations because the Online orders: Toast option only impacts whether a menu entity is available on a restaurant's Toast Online Ordering site. In other words, the omission of this setting has no bearing on whether the modifier group is visible to a partner integration's online ordering site. The Online orders: Toast option will be added to modifier groups in a future release. Also, the `TOAST_ONLINE_ORDERING` enum is included in the `visibility` array for all modifier groups, regardless of the Visible To settings. This is a temporary condition that will be fixed soon. It should not impede the ability for partners to use, test, and code against the new Visible Tosettings because the `TOAST_ONLINE_ORDERING` enum is intended for the use of Toast Online Ordering only.


###### Understanding the Grubhub enumeration

Conceptually, the Grubhub setting has been replaced by the more general Online orders: Ordering partners setting and restaurants that used the Grubhub setting will automatically be migrated to the new Ordering partners setting. This means that any menu entity that had the Grubhub setting set to Yes will now have the Online orders: Ordering partners option enabled and, in the menus API `visibility` array, the `ORDERING_PARTNERS` enum will be present. In the short term, however, the `visibility`array will continue to contain the `GRUBHUB` enum for backwards compatibility. In the future, the `GRUBHUB` enum will be removed.



> **Note**
> 
> The Grubhub setting was only visible at Toast POS system restaurants that used a legacy Grubhub integration, so not all restaurants would have seen this option.


