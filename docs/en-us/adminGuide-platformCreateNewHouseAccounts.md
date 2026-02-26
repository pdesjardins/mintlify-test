---
title: "Creating a house account"
id: platformCreateNewHouseAccounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
parentSectionTitle: "House accounts"
previousSectionFile: adminGuide-platformViewHouseAccounts.md
previousSectionTitle: "Viewing house accounts"
nextSectionFile: adminGuide-platformArchiveHouseAccount.md
nextSectionTitle: "Archiving a house account"
externalReferences: [https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report]
excerpt: "You..."
keywords: ["creating", "house", "account"]
procedures: 3
codeExamples: 0
---

You can create a single or multiple house accounts on the Accounts page in Toast Web. Each house account must have a unique email address, but can share other information such as guest first and last name, address, and phone number.

**Procedure 6.92. To create a single house account**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Go to Payments &gt; Payment methods &gt; House accounts to open the Accountspage.


3. On the Accounts page, select the Create account dropdown.


4. Select the Single account button. This opens the New house account page. On the New house account page, enter the following information:

- Guest first name


- Guest last name


- Guest email address


- Guest phone number


- Customer number (optional alphanumeric number used to associate the house account with the guest)


- Guest address





> **Note**
> 
> Toast support recommends that you enter a delivery address if the house account will place delivery orders.



5. Select the Save button to create the house account. The new house account appears on the Accounts page under the Active tab.



**Procedure 6.93. To create multiple house accounts**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Go to Payments &gt; Payment methods &gt; House accounts to open the Accountspage.


3. On the Accounts page, select the Create account dropdown.


4. Select the Multiple accounts button. This opens the Create multiple accounts page. On the Create multiple accounts page, complete the following:

1. Download the import template.



> **Note**
> 
> A Google account is required to access and download the import template.



2. Make a copy of the import template and fill out the required fields.


3. Export the completed template as a .CSV file.


4. Upload the .CSV file using the Upload file button or by dragging and dropping the .CSV file into the upload box.




5. On the Create multiple accounts page, confirm your upload and check the confirmation checkbox.



> **Note**
> 
> The creation of multiple house accounts is permanent and cannot be undone. You can always choose to archive a house account at any time. For more information, see [Archiving a house account](adminGuide-platformArchiveHouseAccount).


![The Create multiple accounts confirmation dialog in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-bulk-create-accounts-confirmation.png)


6. Select the Submit button to submit your file.

- If the import was unsuccessful, an error message appears. This means the Toast platform could not import all the house account details from the file. Download the attached file to review the errors in the file. Edit the original import file to fix the errors and try to upload again.



> **Note**
> 
> An email is also sent with details of the import failure and instructions on how to re-upload the file.



- If the import was successful, the new house accounts appear on the Accounts page under the Active tab.

![New house accounts on the Accounts page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-new-account.png)

A new Guestbook account is created on the Guestbook page in Toast Web. For more information, see [Access Your Guest Data With Guestbook](https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report).

![New house accounts on the Guestbook page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-guestbook-accounts.png)

Once a house account is created, your guest can start charging transactions to their house account and making payments. The Toast platform keeps track of the outstanding house account balance or credit.





