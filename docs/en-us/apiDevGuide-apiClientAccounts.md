---
title: "Toast API accounts"
id: apiClientAccounts
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiUpdatesEmailDistributionList.md
previousSectionTitle: "API status and updates"
nextSectionFile: apiDevGuide-apiRateLimiting.md
nextSectionTitle: "Rate limiting"
excerpt: "As part of the API registration process for an API environment, the Toast integrations team:"
procedures: 0
codeExamples: 0
---

### Toast API accounts

As part of the API registration process for an API environment, the Toast integrations team:

- Creates API access accounts.


- Assigns client credentials.


- Grants access to services for restaurants.



#### Client identifier and secret

API users must register with the Toast integrations team for each environment to obtain the client credentials to use with that environment. In this context, *client* refers to the software that you use to exchange information with Toast APIs.

API client credentials include:

- **Client identifier -** A unique application identifier that the service API uses to identify the partner application. A client identifier is comparable to an account name.


- **Client secret -** A private string assigned by Toast used to verify the identity of the partner application to the service API when the application makes requests to Toast services. This secret must be kept private between the partner and the Toast integrations team.

The client secret is similar to a password. Do not use email to send or receive a Toast API client secret.



#### Types of Toast API accounts

A Toast API account is one of the following types:

- **Partner API account -** Used by integration partners who perform Toast API operations on multiple restaurants that are not part of the same restaurant management group.

Individual restaurants choose to give API access to specific integration partners.


- **Restaurant management group API accounts -** Used by internal or contracted API client software developers to perform Toast API operations on restaurants that are part of a single restaurant management group.

An example of a restaurant management group is a restaurant chain, with multiple restaurant locations.



##### Partner API accounts

Partner API accounts give an API client access to multiple Toast platform restaurants that may be part of different restaurant management groups. Typically, a partner API client account is used by a restaurant service provider. An individual Toast platform restaurant that uses the services that you provide can choose to give your API account access to the restaurant.

You can use a partner API account to perform Toast API operations for any of the restaurants that you have access to. When you authenticate with a partner API account, you use the same authentication token at any of the restaurants.

The following diagram shows a partner API client using a partner authentication token to perform API operations at any restaurant location that chooses to give that partner access.

![Diagram that shows the authentication process for a partner API client](https://doc.toasttab.com/doc/media/partner-api-client-authentication.png)

For information about finding the restaurants that your partner API account has access to, see [Location access](apiPartnersGettingAccessibleRestaurants.html).

##### Restaurant management group API accounts

Restaurant management group API accounts give an API client access to all of the Toast platform restaurants in one restaurant management group. A restaurant management group might represent a restaurant chain or it might represent the ownership of a single restaurant location.

You can use a restaurant management group API account to perform Toast API operations for any of the restaurants that are part of that restaurant management group.

The following diagram shows a restaurant management group API client using a management group authentication token to perform API operations at any restaurant location that is a part of that restaurant management group. It does not matter which partners a location has chosen to connect to.

![Diagram that shows the authentication process for a restaurant management group API client](https://doc.toasttab.com/doc/media/management-group-api-client-authentication.png)

