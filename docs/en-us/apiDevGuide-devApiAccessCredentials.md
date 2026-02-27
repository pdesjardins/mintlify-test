---
title: "Standard API access credentials"
id: devApiAccessCredentials
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAStandardApiAccessDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a standard API access developer"
previousSectionFile: apiDevGuide-devApiAccessResources.md
previousSectionTitle: "Standard API access resources"
nextSectionFile: apiDevGuide-devApiAccessWebhookSubscriptions.md
nextSectionTitle: "Standard API access webhook subscriptions"
externalReferences: [https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Essentials, https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast]
excerpt: "As a standard API access user, you can create and manage..."
procedures: 2
codeExamples: 0
---

As a standard API access user, you can create and manage credentials for a Toast location or locations in a management group. The level of access you have to edit and view standard API access credentials depends on whether:

- You created the credentials or another Toast user did.


- You have the 8.4 Manage Integrationspermission to all of the locations associated with a set of credentials or only some of them.



There are three levels of access:

- Full access (no icon)


- Read-only access (warning icon)


- Locked access (lock icon)




<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Permission</div></th>
      <th className=""><div className="">Ownership</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">8.4 Manage Integrations permission</div></td>
      <td className="px-4 py-4"><div className="space-y-4">You created the credentials.</div></td>
      <td className="px-4 py-4"><div className="space-y-4">You did not create the credentials.</div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">You have the 8.4 Manage Integrations permission enabled at every location linked to the credentials in the management group.</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Full access </p> <p className="text-base leading-relaxed">Allows for editing and reading of credentials.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Full access</p> <p className="text-base leading-relaxed">Allows for editing and reading of credentials.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4">You do <em className="">not</em>  have the 8.4 Manage Integrations permission enabled at every location linked to the credentials in the management group.</div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Read-only</p> <p className="text-base leading-relaxed">Allows for reading of credentials.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Locked</p> <p className="text-base leading-relaxed">Does not allow for editing or reading of credentials.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

On the Manage credentials page, a warning icon next to a credential’s name indicates you have read-only access, a lock icon indicates that you cannot edit or view the credential, and no icon indicates you have full access to the credential.

![Shows the various types of credentials access on the Manage credentials page.](https://doc.toasttab.com/doc/media/dev-api-access-credentials-page.png)

If you want to update your locked or read-only credentials to full access, follow the procedures below. Each procedure is different depending on if you have locked access or read-only access. 



> **Note**
> 
> Only a Toast user or restaurant operator with full-access credentials can enable the 8.4 Manage Integrationspermission for other employees.


**Procedure 1.15. To update an employee’s locked access to full access**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. A Toast employee or restaurant operator with full-access goes to Employees &gt; Employee management &gt; Employeesto open the Employees page. 


3. The Toast employee or restaurant operator selects the employee’s name to open the Permissions page. 


4. The Toast employee or restaurant operator selects the Jobs & Permissions tab.


5. Scroll down to the Permissions section. The Permissions section lists all the locations in the management group.


6. Confirm that the 8.4 Manage Integrationspermission is enabled for each location linked to the credentials. Repeat this step for every location linked to the credentials. 



**Procedure 1.16. To update your read-only access to full access**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Go to Integrations &gt; Toast API access &gt; Manage credentials to open the Manage credentials page. 


3. On the Manage credentials page, select the credentials with the warning icon. This opens the Credentials page. 


4. Select the link in the banner to open a dialog. The dialog displays a list of Toast locations you no longer have access to. 


5. Ask a Toast employee or restaurant operator with full-access to go to Employees &gt; Employee management &gt; Employees to open the Employees page. 


6. The Toast employee or restaurant operator selects the employee’s name to open the Permissions page.


7. The Toast employee or restaurant operator selects the Jobs & Permissions tab.


8. Scroll down to the Permissions section. The Permissions section lists all the locations in the management group.


9. Confirm that the 8.4 Manage Integrationspermission is enabled for each location linked to the credentials. Repeat this step for every location linked to the credentials. 



Once you have the 8.4 Manage Integrationspermission at every location associated with the credentials you want to edit, you will be able to edit those credentials as needed.

## Creating standard API access credentials

The following procedure describes how to create standard API access credentials in Toast Web.



> **Note**
> 
> You can configure up to 100 sets of unique standard API access credentials per management group in Toast Web.


**Procedure 1.17. To create Standard API credentials**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Go to Integrations &gt; Toast API access &gt; Manage credentials to open the Manage credentials page.



> **Note**
> 
> An active subscription to [Toast Restaurant Management Suite Essentials](https://www.toasttab.com/customers/shop/software-services/restaurant-management-suite?tier=Essentials) or higher is required for every location you want standard API access for.



3. On the Manage credentials page, navigate to the Create new credentials button.


4. Select the down arrow and select Standard API. This opens the New Credentialspage.

![Shows the Manage credentials page with the Standard API button emphasized.](https://doc.toasttab.com/doc/media/dev-api-access-manage-credentials-page.png)


5. On the New Credentials page, you can:

- View a list of the APIs that you will have read-only access to.


- View links to documentation.


- Enter a credential name. Toast support recommends this be a name that you can easily reference.


- Select the scopes for the actions you want your Toast API client to be allowed to perform. For more information, see [Standard API access scopes](apiDevGuide-devApiAccessScopes).


- Select the location(s) that you want read-only API access to. You can choose to select all the locations in your management group or use the dropdown menu to select individual locations. Select the Apply button to select your location(s).

![Shows the credential name, API scopes, and locations fields on the New Credentials page.](https://doc.toasttab.com/doc/media/dev-api-access-new-credentials-page.png)



> **Note**
> 
> If a location displays a locked icon and is grayed out, this indicates that the location does not have access to Toast Restaurant Management Suite Essentials or higher. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast).





6. Select the Confirm button. This navigates you to the Credentials page. You can view your new credentials on the Credentials table on the Manage Credentials page.

![Shows new credentials on the Manage credentials page.](https://doc.toasttab.com/doc/media/dev-api-access-new-credentials.png)

An email is sent confirming that standard API access has been activated for your selected location(s). The email also includes the names and GUIDs of the location(s) you have standard API access credentials for and a link to view your credentials in Toast Web.



> **Note**
> 
> You use the GUID to make Toast API requests. GUIDs are also referred to as the `Toast-Restaurant-External-ID` or `restaurantGuid`. You can retrieve GUIDs using the Partners API.




## Viewing standard API access credentials

You can view your standard API access credentials on the Manage credentials page in Toast Web. The Manage credentials page displays the following information:

- Link to create new credentials


- Table of Toast API credentials with the following information:

- Credential name


- API access type


- Number of locations with the API access type


- Date and time the credentials were last updated


- The email of the Toast user who last updated the credentials


- Edit icon (pencil)




- Links to documentation



## Managing standard API access credentials

You can manage your standard API access credentials on the Manage credentials page in Toast Web. To view and edit your credentials, select the edit icon (pencil) next to the credential name to open the Credentials page. On the Credentials page, you can view information and complete various actions. From the Credentialspage, you can:

- View the credential name


- View the number of locations included in the credentials set


- View the number of scopes included in the credentials set


- Edit credentials


- Delete credentials


- Edit group or location IDs


- View credentials in JSON format


- Copy API Access URL


- Copy Client ID


- Copy user access type


- Rotate client secret



![Shows credential details on the Credentials page.](https://doc.toasttab.com/doc/media/dev-api-access-manage-credentials.png)

### Editing standard API access credentials

To edit your standard API access credentials, select the Edit credentials button to open the Edit credentials page. On the Edit credentials page, you can edit your credential name and change the location(s) the credentials have access to. Select the Confirm button to confirm and save your changes.

### Editing group or location IDs

Group and location IDs are account numbers that you can use to map restaurants in your integration. After populating a group or location ID for the location, you can retrieve this value using the restaurants API. For more information, see [Using location and group identifiers](apiDevGuide-apiPartnersGettingAccessibleRestaurants#apiPartnersLocationGroupIDs).

![Shows edit group or location ID dialog.](https://doc.toasttab.com/doc/media/dev-api-access-edit-ids.png)

### Viewing standard API access credentials in JSON format

You can choose to view your credentials in JSON format. JSON is short for JavaScript Object Notation. You can choose to copy your credentials and include them in the header of your API requests.

![Shows credentials in JSON format.](https://doc.toasttab.com/doc/media/dev-api-access-credentials-json.png)

### Copying credentials and other information

You can choose to copy the following information to your clipboard for easy reference. You can copy:

- API Access URL


- User access type


- Client ID



Select the Copy icon to copy the information.

### Rotating client secret



> **Note**
> 
> Active authentication tokens generated using your credentials will continue to be valid until they expire or are replaced with new authentication tokens.


A client secret is a private string assigned by Toast to verify the identity of the partner application to the service API when the application makes requests to Toast services. It is good security practice to rotate your client secret to minimize the impact of potential breaches and to reduce the possibility of compromised credentials. For more information, see [Credential storage guidelines](apiDevGuide-authentication#apiAuthTokenStorage).



> **Note**
> 
> Rotating your client secret may cause disruptions to any integrations using the same credentials.


**Procedure 1.18. To rotate your client secret**

1. On the Credentials page, select the Rotate button. This opens the Ready to rotate the client secret dialog.


2. In the Ready to rotate the client secret dialog, confirm you want the existing client secret to expire and want to create a new client secret. To confirm, type ROTATE SECRET in the text field.


3. Select the Continue button. Your new client secret appears. Toast support recommends you copy and store your client secret in a secure location, such as a password manager. For more information, see [Credential storage guidelines](apiDevGuide-authentication#apiAuthTokenStorage).


4. Select the I have copied and saved the client secret checkbox to finish rotating your client secret. The Credentials page displays the date and time your new client secret was created.

An email is sent notifying you that your client secret has been rotated with the name of the Toast user who rotated the secret.



### Deleting standard API access credentials



> **Note**
> 
> Deleting standard API access credentials is permanent. You cannot restore deleted credentials.


To delete your standard API access credentials, select the Delete credentials button on the Credentials page. This opens a confirmation dialog. In the dialog, type DELETE SECRET in the text field to confirm deletion of the credentials.

### Securely sharing credentials

When sharing standard API access credentials with your development team, always use a password manager or secure secret management service. Never share credentials via email or messaging applications. Limit access to team members who need it, and rotate your client secret when team members change. For complete security requirements, see [Credential storage guidelines](apiDevGuide-authentication#apiAuthTokenStorage).

