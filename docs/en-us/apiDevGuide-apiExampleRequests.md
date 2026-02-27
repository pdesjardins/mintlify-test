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
      <td className=""><div className=""><strong className="">1.1.</strong> </div></td>
      <td className=""><div className=""><strong className="">What is Postman, and where can I learn more about it?</strong> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Postman is a tool for making ad hoc API calls. To learn more about this tool and to download it, see <a href="https://www.getpostman.com/" className="">the Postman website</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><strong className="">1.2.</strong> </div></td>
      <td className=""><div className=""><strong className="">Where can I get the Postman collection?</strong> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""></div></td>
      <td className=""><div className="">The Postman API client collection for Toast APIs can be found <a href="../media/Toast_Postman_Collection.zip" className="">here</a>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><strong className="">1.3.</strong> </div></td>
      <td className=""><div className=""><strong className="">What initial setup should I do?</strong> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Unzip the collection file in the link above. To import the collection, in Postman go to File &gt; Import &gt; Import from File. <br/> Select each file from the unzipped collection file to import them. <br/> For more information about using the Postman API client, see <a href="https://learning.postman.com/" className="">the Postman documentation</a>. <br/> To set up your Postman collection:<ol className=""><li className="">Click the eye icon at the top right of your Postman window, then select the Sandbox environment.![Image](https://doc.toasttab.com/doc/media/postman_environments.png)</li><li className="">In the Current Value column, add the environment hostname, your API client credentials, and the desired restaurant GUID. Do not add this information to the Initial Value column.![Image](https://doc.toasttab.com/doc/media/postman_setup.png)</li><li className="">Open a request from an API you will use in your integration.  <br/> New integration partners often use the configuration API to run their first API test.  <br/> Submit an API request to ensure you receive data in return. <br/> The pre-request script in each Postman collection automatically requests a new authentication token.</li></ol> <br/> To obtain hostnames and authentication credentials, contact Toast support. <br/> If you are using a <a href="apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts" className="">partner API account</a>, the <a href="apiDevGuide-apiPartnersGettingAccessibleRestaurants" className="">partners endpoint</a> provides the list of restaurant GUIDs that you are able to poll.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><strong className="">1.4.</strong> </div></td>
      <td className=""><div className=""><strong className="">How do I make an API call?</strong> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""></div></td>
      <td className=""><div className="">After doing the initial collection setup above, open the desired API call on the left sidebar. <br/> Verify that variables such as parameters and JSON bodies are correct. <br/> To submit your API call and see the results, click send.</div></td>
    </tr>
  </tbody>
</table>
</div>

