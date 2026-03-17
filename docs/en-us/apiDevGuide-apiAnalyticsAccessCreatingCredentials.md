---
title: "Creating analytics API access credentials"
id: apiAnalyticsAccessCreatingCredentials
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAnAnalyticsApiDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're an analytics API developer"
previousSectionFile: apiDevGuide-apiAnalyticsAccessOverview.md
previousSectionTitle: "Analytics API access overview"
nextSectionFile: apiDevGuide-apiOverviewOmitChunkFromSearchIndex.md
nextSectionTitle: "API overview"
excerpt: "The following procedure describes how to create analytics API access credentials in Toast Web."
procedures: 1
codeExamples: 0
---

The following procedure describes how to create analytics API access credentials in Toast Web.



> **Note**
> 
> You can configure configure only one set of analytics API access credentials per management group in Toast Web.


**Procedure 1.20. To create Analytics API credentials**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose** Integrations &gt; Toast API access &gt; Manage credentials** to open the **Manage credentials** page.



> **Note**
> 
> An active subscription to Toast Restaurant Management Suite Pro or higher is required.



3. On the **Manage credentials** page, navigate to the **Create new credentials** button.


4. Select the down arrow and select **Analytics API**. This opens the **New Credentials**page.

![Shows the Manage credentials page with the Analytics API button emphasized.](https://doc.toasttab.com/doc/media/api-analytics-access-manage-credentials-page.png)


5. On the **New Credentials** page, you can:

- View a list of the reporting data that you will have read-only access to.


- View links to documentation.


- Enter a credential name. Toast support recommends this be a name that you can easily reference.


- View the management group you are creating credentials for and the number of locations included.

![Shows the credential name, API scopes, and locations fields on the New Credentials page.](https://doc.toasttab.com/doc/media/api-analytics-access-new-credentials-page.png)




6. Select the** Create credentials** button. This navigates you to the **Credentials** page.

![Shows the Credentials page for the credentials just created.](https://doc.toasttab.com/doc/media/api-analytics-access-credentials-page.png)

On the **Credentials** page, you can:

- View and edit the credential set name


- View the management group used for the credentials set and the number of locations included


- View links to the analytics API documentation and standard API access documentation


- View and copy the API access URL


- View and copy the API access type


- View and copy the Client ID


- View the Client secret



> **Note**
> 
> You can only view the client secret once.



- Delete credentials





## Viewing analytics API access credentials in JSON format

You can choose to view your credentials in JSON format. JSON is short for JavaScript Object Notation. You can choose to copy your credentials and include them in the [request for an authentication token](apiDevGuide-authentication#apiAuthGetTokenRequest).

![Shows credentials in JSON format.](https://doc.toasttab.com/doc/media/api-analytics-access-credentials-json.png)

## Rotating client secret



> **Note**
> 
> Active authentication tokens generated using your credentials will continue to be valid until they expire or are replaced with new authentication tokens.


A client secret is a private string assigned by Toast to verify the identity of the partner application to the service API when the application makes requests to Toast services. It is good security practice to rotate your client secret to minimize the impact of potential breaches and to reduce the possibility of compromised credentials. For more information, see [Credential storage guidelines](apiDevGuide-authentication#apiAuthTokenStorage).



> **Note**
> 
> Rotating your client secret may cause disruptions to any integrations using the same credentials.


**Procedure 1.21. To rotate your client secret:**

1. On the **Credentials** page, navigate to the **Client secret** information.


2. Select **Rotate secret**. The **Ready to rotate the client secret?** dialog opens.


3. To confirm, type **ROTATE SECRET** in the text field.


4. Select the **Continue** button. The **View the client secret** dialog opens.


5. Select **View secret**. Your new client secret appears. Toast support recommends you copy and store your client secret in a secure location, such as a password manager. For more information, see [Credential storage guidelines](apiDevGuide-authentication#apiAuthTokenStorage).


6. Select the **I have copied and saved the client secret** checkbox.


7. Select the **Finish** button to finish rotating the client secret.



## Deleting analytics API access credentials



> **Note**
> 
> Deleting analytics API access credentials is permanent. You cannot restore deleted credentials.


To delete your analytics API access credentials, select the **Delete credentials** button on the **Credentials** page. This opens a confirmation dialog. In the dialog, type **DELETE SECRET** in the text field to confirm deletion of the credentials, and select the **Delete** button to finish deleting the credentials.

