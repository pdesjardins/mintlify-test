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


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">1.1.</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">What is Postman, and where can I learn more about it?</strong> </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Postman is a tool for making ad hoc API calls. To learn more about this tool and to download it, see <a href="https://www.getpostman.com/" className="">the Postman website</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">1.2.</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Where can I get the Postman collection?</strong> </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Postman API client collection for Toast APIs can be found <a href="../media/Toast_Postman_Collection.zip" className="">here</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">1.3.</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">What initial setup should I do?</strong> </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unzip the collection file in the link above. To import the collection, in Postman go to **File &gt; Import &gt; Import from File**.</p> <p className="text-base leading-relaxed">Select each file from the unzipped collection file to import them.</p> <p className="text-base leading-relaxed">For more information about using the Postman API client, see <a href="https://learning.postman.com/" className="">the Postman documentation</a>.</p> <p className="text-base leading-relaxed">To set up your Postman collection:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Click the eye icon at the top right of your Postman window, then select the Sandbox environment.</p>![Image](https://doc.toasttab.com/doc/media/postman_environments.png)</li><li className=""><p className="text-base leading-relaxed">In the **Current Value** column, add the environment hostname, your API client credentials, and the desired restaurant GUID. Do not add this information to the **Initial Value** column.</p>![Image](https://doc.toasttab.com/doc/media/postman_setup.png)</li><li className=""><p className="text-base leading-relaxed">Open a request from an API you will use in your integration. </p> <p className="text-base leading-relaxed">New integration partners often use the configuration API to run their first API test. </p> <p className="text-base leading-relaxed">Submit an API request to ensure you receive data in return.</p> <p className="text-base leading-relaxed">The pre-request script in each Postman collection automatically requests a new authentication token.</p></li></ol> <p className="text-base leading-relaxed">To obtain hostnames and authentication credentials, contact Toast support.</p> <p className="text-base leading-relaxed">If you are using a <a href="apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts" className="">partner API account</a>, the <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants" className="">partners endpoint</a> provides the list of restaurant GUIDs that you are able to poll.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">1.4.</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">How do I make an API call?</strong> </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">After doing the initial collection setup above, open the desired API call on the left sidebar.</p> <p className="text-base leading-relaxed">Verify that variables such as parameters and JSON bodies are correct.</p> <p className="text-base leading-relaxed">To submit your API call and see the results, click **send**.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

