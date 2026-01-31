---
title: "Permissions"
id: platformShiftReviewPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
previousSectionTitle: "Shift review"
nextSectionFile: adminGuide-platformConfiguringShiftReview.md
nextSectionTitle: "Configuring your shift review"
excerpt: "Certain..."
keywords: [permissions]
procedures: 0
codeExamples: 0
---

### Permissions

Certain permissions can affect shift review. To view and edit permissions from Toast Web, choose Employees > Employee management > Jobs to open the Jobspage. Select the job title to edit the permissions.

Below is a list of permissions required to complete shift review or review your employees' shifts.

| Access permission | Description | 
| --- | --- |
| Table Service Mode | **Gives access to**- On the Toast POS home screen, gives access to My Account > Shift Review.

**Assign to**- Employees

 | 
| Quick Order Mode | **Gives access to**- On the Toast POS home screen, gives access to My Account > Shift Review.

**Assign to**- Employees

 | 
| Payment Terminal Mode | **Gives access to**- The Payment Terminal screen. Often assigned with Cash Drawer Access.
- On the Toast POS home screen, gives access to My Account > Shift Review.

**Assign to**- Employees

 | 
| Delivery Mode (only required for drivers who need to complete shift review)  | **Gives access to**- On the Toast POS home screen, gives access to My Account > Shift Review.

**Assign to**- Delivery drivers

 | 
| Shift Review  | **Gives access to**- Employee's shift review report.
- On the Toast POS home screen, gives access to Manager Activities > Shift Reviewand Manager Activities > Time Cards.

**Assign to**- Managers

 | 
| Shift Review Sales Data  | **Gives access to**- Detailed sales and payment data for shift review. Often assigned with the manager-level Shift Review permission, which provides access to restaurant-wide shift review.

**Assign to**- Employees and managers

 | 

Below is a list of some commonly enabled permissions that can affect how your shift review behaves:

| Access permission | Description | 
| --- | --- |
| Cash Drawer Access  | **Gives access to**- Cash drawers to complete cash payments. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.

 | 
| Cash Drawers (Blind)  | **Gives access to**- Manager Activities > Cash Drawers on the Toast POS home screen without reporting the expected cash amount. Must be assigned with Cash Drawer Access.

This access is typically assigned to cashiers and others who need to close out and replace cash drawers at the end of their shift.  | 
| Cash Drawers (Full)  | **Gives access to**- Manager Activities > Cash Drawers on the Toast POS home screen including the starting balance and expected cash amounts. Must be assigned with Cash Drawer Access.

This access is typically assigned to managers and others who need to close out and replace cash drawers at the end of their shift. If you have both Cash Drawers (Blind) and Cash Drawer (Full) permission, the Cash Drawer (Full) permission overrides the Cash Drawer (Blind) permission.  | 
| Close Out Day  | **Gives access to**- The "Z report" sales summary for the current day, an optional report of check status and employee activity. Often assigned with Shift Review.
- On the Toast POS home screen, gives access to Manager Activities > Close Out Day. When assigned with Sales Reports, the Full Sales Report option becomes functional for employees who have credentials for Toast Web.

 | 

