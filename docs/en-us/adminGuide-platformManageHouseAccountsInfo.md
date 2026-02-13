---
title: "Managing house account information"
id: platformManageHouseAccountsInfo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
parentSectionTitle: "House accounts"
previousSectionFile: adminGuide-platformArchiveHouseAccount.md
previousSectionTitle: "Archiving a house account"
nextSectionFile: adminGuide-platformEnableHouseAccountsPaymentMethod.md
nextSectionTitle: "Enabling house accounts as a payment method"
externalReferences: [https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report]
excerpt: "You can view the details of a house account on the House account profile page in Toast Web. On the House account profile page, you can:"
keywords: ["managing", "house", "account", "information"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> You must have the 4.13 Customer Credits &
      Reports permission to view certain house account data sourced
      from the Guestbook feature. For more information, see [Access
      Your Guest Data With Guestbook](https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report).


You can view the details of a house account on the House
    account profile page in Toast Web. On the House
    account profile page, you can:

- Create an invoice


- Archive the house account


- View house account details


- View a list of activities on the house account


- View the contact information for the house account owner


- Adjust the outstanding balance



> **Note**
> 
> You can only add credit to reduce a house account's
          outstanding balance. You cannot increase the amount due on a house
          account.




The House account profile page has four tabs on
    the left navigation. You can select a tab to quickly navigate to the
    section.

- [Overview](adminGuide-platformManageHouseAccountsInfo#platformHouseAccountsProfileOverview)


- [Activity](adminGuide-platformManageHouseAccountsInfo#platformHouseAccountsActivity)


- [Invoices](adminGuide-platformManageHouseAccountsInfo#platformHouseAccountsInvoices)


- [Contact](adminGuide-platformManageHouseAccountsInfo#platformHouseAccountsContact)



## Overview

In the Overview section, you can:

- View house account details


- Adjust the house account's outstanding balance



> **Note**
> 
> If the outstanding balance is a positive amount, that is the
            balance owed on the account. A negative balance is credit on the
            account.



- View the year the house account was created


- View the frequency of guest visits to the location


- View lifetime spend



> **Note**
> 
> The lifetime spend is the amount the guest has spent at the
            location. Lifetime spend is linked to the guest phone number and
            not the house account.



- View the number of orders linked to the house account



### Editing house account owner information

In the Overview section, you can edit the
        house account owner’s information. To edit owner information, select
        the edit icon (pencil). This opens the Edit house
        account page. From the Edit house
        account page, you can edit:

- Guest name, email address, phone number, and customer
            number


- Guest address



### Adjusting a house account's outstanding balance



> **Note**
> 
> You can only add credit to reduce a house account's
          outstanding balance. You cannot increase the amount due on a house
          account.


In the Overview section, you can also
        adjust the outstanding balance of a house account. Select the
        Adjust balance link next to the outstanding
        balance to open the Adjust outstanding balance
        dialog. In the Adjust outstanding balance dialog,
        you can choose to either:

- Set a new outstanding balance


- Reduce the outstanding balance



Select your option and in the numerical field, enter the new
        outstanding balance or the amount to reduce the outstanding balance.
        The amount must be a positive number. The dialog displays the updated
        outstanding balance for you to confirm and save.

For example, if a house account has a balance of $397.00, you
        can adjust (reduce) the balance by $200. This creates an
        ADJUSTMENT activity and adjusts the house account
        outstanding balance to $197.00.



> **Note**
> 
> An invoice cannot be created for an
            ADJUSTMENT.


![The Adjust outstanding balance dialog.](https://doc.toasttab.com/doc/media/platform-house-accounts-adjust-balance.png)

## Activity

In the Activity section, you can:

- Search for activities using the date picker or the
          All activities filter


- View activities by date and time


- View activities by type. Activity types are:

- TRACKED SALE: An order linked and
              tracked to a house account, but not paid for with a house
              account. A TRACKED SALE does not affect the
              house account balance.


- CHARGE: An order was charged to the
              house account.


- PAYMENT: A payment was applied to the
              house account. Payments made to house accounts cannot be
              refunded.


- VOID CHARGE: A charge to the house
              account was voided.


- VOID PAYMENT: A payment to the house
              account was voided.


- ADJUSTMENT: A manual adjustment to
              the outstanding balance of the house account. The adjustment
              must be a positive amount. You can only manually reduce the
              outstanding balance, not increase the balance owed.


- INVOICE CREATED: An invoice was
              created.


- INVOICED VOIDED: An invoice was
              voided.


- INVOICE SENT: An invoice was sent to
              the email address on the house account.



![Shows the Account Activity section on the House account profile page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-account-activity.png)


- Download account activity

- Detailed report: A report of all
              charges, including transaction details for the date range
              specified. This report does not include house account
              payments.


- Activity table: A report of the
              activity on the account. This report is an export of the
              Account activity table.



![Shows the Downloads icon with the options emphasized in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-account-activity-downloads.png)



## Invoices

In the Invoices section, you can view the
      statuses of your invoices and other details:

- Creation date and time


- Due date


- Invoice amount


- Invoice number and link to the invoice


- Invoice status. Invoices have one of the following
          statuses:

- PAID: The invoice has been
              paid.


- OPEN: The invoice has been created
              and sent.


- DRAFT: The invoice has been created
              but not sent.





## Contact

In the Contact section, you can view the
      contact information for the owner of the house account.

