---
title: "Using REST APIs"
id: apiUsingRestApis
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "General Toast API information"
nextSectionFile: apiDevGuide-portalHowToBuildAToastIntegration.md
nextSectionTitle: "How to build a Toast integration"
externalReferences: [https://developer.mozilla.org/en-US/docs/Glossary/REST, https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview, https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods, https://curl.se/, https://docs.oracle.com/en/java/javase/11/docs/api/java.net.http/java/net/http/HttpClient.html]
excerpt: "Many Toast APIs are Representational State Transfer (REST) APIs. You can use REST APIs to connect your software and information systems to the Toast platform. REST APIs can perform functions..."
keywords: [GET,POST,PUT,DELETE,HTTPClient]
procedures: 0
codeExamples: 0
---

### Using REST APIs

Many Toast APIs are [Representational State Transfer](https://developer.mozilla.org/en-US/docs/Glossary/REST) (REST) APIs. You can use REST APIs to connect your software and information systems to the Toast platform. REST APIs can perform functions including the following.

**REST APIs can:**

- Get information about business operations and product configuration from the Toast platform.


- Add new information about business operations to the Toast platform.


- Update existing Toast platform information about business operations and product configuration.


- Make information about business operations inactive, when you no longer need it.



REST APIs use [HyperText Transfer Protocol](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview) (HTTP) requests to perform functions. To use a REST API function, you send an HTTP request to the REST API server. The server sends you a response that tells you whether your request was successful and includes information about the result of the operation.

When you visit a web page in your web browser, you are sending an HTTP request to a server. The request you make is to get the contents of a resource you name. That resource is the web page. To use REST API functions, you make a request in the same way that your web browser does. In addition to getting resources (a `GET` request), you can create new resources using a `POST` request, update existing resources using a `PUT` request, or inactivate a resource using a `DELETE` request. The [HTTP standard defines the methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods) (`GET`, `POST`, `PUT`, `DELETE`, and others) that you can use.

An HTTP *client* sends requests to an HTTP *server*. For example, a web browser is an HTTP client that sends HTTP requests to a web server. You use an HTTP client to send requests to Toast REST APIs. You can choose any HTTP client software that suits your information technology environment and your goals for using Toast APIs. The following list includes examples of HTTP client software. 

**Example HTTP client software for REST API requests**

- The [curl command-line program](https://curl.se/). You can use curl to send HTTP requests to a REST API server. The examples in this documentation use the curl program. Using curl commands isn't a practical way to build a real API integration but it is an effective way to try requests and see what's in the communication between the client and the server.


- Open-source and commercial REST API client products. You can find many tools available for working with REST APIs on the web. You can install REST API client tools on a local computer or use online tools that run on the web. Find and use tools that meet your information technology requirements and meet your information technology security requirements.


- An HTTP library for the programming language you use to build an API integration with the Toast platform. Using a programming language is much more practical for building a real API integration. For example, the Java® programming language includes [an `HTTPClient` class](https://docs.oracle.com/en/java/javase/11/docs/api/java.net.http/java/net/http/HttpClient.html) you can use to make HTTP requests in your program. This documentation does not provide information about using specific programming languages to use Toast REST APIs.



