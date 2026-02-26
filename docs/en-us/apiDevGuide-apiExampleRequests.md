---
title: "Example API requests"
id: apiExampleRequests
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiResponsesAndErrors.md
previousSectionTitle: "API responses and errors"
nextSectionFile: apiDevGuide-apiDeployment.md
nextSectionTitle: "Deployment best practices"
externalReferences: [https://www.getpostman.com/, https://learning.postman.com/]
excerpt: "Toast provides a Postman API client collection of API requests to help you test the APIs without writing any code."
keywords: ["Where can I get the Postman collection?", "What initial setup should I do?", "How do I make an API call?"]
procedures: 0
codeExamples: 0
---

Toast provides a Postman™ API client collection of API requests to help you test the APIs without writing any code.

| **1.1.** | **What is Postman, and where can I learn more about it?** | 
|  | Postman is a tool for making ad hoc API calls. To learn more about this tool and to download it, see [the Postman website](https://www.getpostman.com/). | 
| **1.2.** | **Where can I get the Postman collection?** | 
|  | The Postman API client collection for Toast APIs can be found [here](../media/Toast_Postman_Collection.zip). | 
| **1.3.** | **What initial setup should I do?** | 
|  | Unzip the collection file in the link above. To import the collection, in Postman go to File &gt; Import &gt; Import from File.Select each file from the unzipped collection file to import them.For more information about using the Postman API client, see [the Postman documentation](https://learning.postman.com/).To set up your Postman collection:1. Click the eye icon at the top right of your Postman window, then select the Sandbox environment.![Image](https://doc.toasttab.com/doc/media/postman_environments.png)


2. In the Current Value column, add the environment hostname, your API client credentials, and the desired restaurant GUID. Do not add this information to the Initial Value column.![Image](https://doc.toasttab.com/doc/media/postman_setup.png)


3. Open a request from an API you will use in your integration. New integration partners often use the configuration API to run their first API test. Submit an API request to ensure you receive data in return.The pre-request script in each Postman collection automatically requests a new authentication token.

To obtain hostnames and authentication credentials, contact Toast support.If you are using a [partner API account](docs/en-us/apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts), the [partners endpoint](docs/en-us/apiDevGuide-apiPartnersGettingAccessibleRestaurants) provides the list of restaurant GUIDs that you are able to poll. | 
| **1.4.** | **How do I make an API call?** | 
|  | After doing the initial collection setup above, open the desired API call on the left sidebar.Verify that variables such as parameters and JSON bodies are correct.To submit your API call and see the results, click send. | 

