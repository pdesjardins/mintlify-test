---
title: "Enabling and configuring text alerts"
id: enablingAndConfiguringTextAlerts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTextAlertsOmitChunkFromSearchIndex.md
parentSectionTitle: "Text alerts"
previousSectionFile: adminGuide-platformTextAlertsOverview.md
previousSectionTitle: "Text alerts overview"
nextSectionFile: adminGuide-sendingAndReceivingTextAlerts.md
nextSectionTitle: "Sending and receiving text alerts"
excerpt: "To enable text alerts Access Toast Web. Select Front of house > Employee SOS > Text alert setup. Under the Enable Text Alerts option, select Yes."
keywords: ["enabling", "configuring", "text", "alerts"]
procedures: 1
codeExamples: 0
---

**Procedure 4.13. To enable text alerts**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Select Front of house \> Employee SOS \> Text alert setup.


3. Under the Enable Text Alerts option, select Yes.



You see the SMS Messages, Who can receive SMS alerts, and Who can send SMS alerts configuration options. You can save and publish your changes with the default configuration.



> **Note**
> 
> If your restaurant is part of a multi-location restaurant group, enabling text alerts for the [session restaurant](sessionRestaurant.html) enables it for all restaurants in the group.


## Configuring preset text messages

The text alert feature comes with four preset text (SMS) messages that restaurant employees can send from Toast POS devices. The messages are listed in Toast Web in the order in which they appear on a POS device. From the Front of house \> Employee SOS \> Text alert setup page in Toast Web you can edit, delete, or reorder existing messages as well as add new messages to the list.

**Procedure 4.14. To edit an existing text message**

1. Under the SMS Messages option, click the message you want to edit.


2. Edit the message.


3. Use the tab key to leave the text field and save the edited message.


4. Save and publish your changes.



**Procedure 4.15. To add a new text message**

1. Under the SMS Messages option, click the + Add Message button to add a new entry.


2. Enter a new message in the language of your choice.


3. Use the tab key to leave the text field and save the new message.


4. Save and publish your changes.



**Procedure 4.16. To reorder existing text messages**

1. Under the SMS Messages option, click and drag the reordering icon (![Image](https://doc.toasttab.com/doc/media/reorder_icon.png)

 ) corresponding to the message(s) you want to move up or down the list.


2. Save and publish your changes.



**Procedure 4.17. To delete an existing text message**

1. Under the SMS Messages option, click the trash icon for the message you want to delete.


2. Save and publish your changes.



## Configuring text alert recipients

Text alert recipients are grouped by job roles. When you select a job role to receive text alerts, all employees in that role who have provided a phone number for their personal profile receive text alerts.

The Who can receive SMS alerts option displays a list of all job roles defined for your restaurant. Job roles that are more likely to be able to provide assistance in critical situations such as "Manager," "Owner," "Shift Manager," and "GM" are displayed at the top of the list for easy configuration. No jobs roles will receive text alerts unless you select them from the list.

If you want a custom set of employees in different job roles to receive text alerts, you can create a new job role for these employees and select that role to receive text alerts. For example, you can create a job role called "Text Alert Responders," assign this role to a custom list of employees and select this job role to receive text alerts.



> **Note**
> 
> An individual employee cannot opt out of receiving text alerts if you selected their job role to receive text alerts.


**Procedure 4.18. To select text alert recipients**

1. On the Text alert setup page in Toast Web, access the Who can receive SMS alertsoption.


2. Select the check box for each job role that should receive text alerts.


3. Click the Save button. Under the Who can receive SMS alerts option the page now displays a list of employees who can receive text alerts.

![The Text Alert Setup page with the General Manager and Server checkboxes checked.](https://doc.toasttab.com/doc/media/employees-text-alerts.png)


4. Save and publish your changes.



## Configuring who can send text alerts

You can allow all employees in certain job roles to send preset text alerts from Toast POS devices.

The Who can send SMS alerts option displays a list of all job roles defined for your restaurant. By default, all job roles are allowed to send text alerts. 

**Procedure 4.19. To select who can send text alerts**

1. On the Text alert setup page in the Toast Web, access the Who can send SMS alertsoption.


2. Select the check box for each job role that can send text alerts. Clear the check boxes for job roles that cannot send text alerts.


3. Save and publish your changes.



