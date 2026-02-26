---
title: "Permissions"
id: platformShiftReviewPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformShiftReviewOverview.md
previousSectionTitle: "Overview"
nextSectionFile: adminGuide-platformConfiguringShiftReview.md
nextSectionTitle: "Configuring your shift review"
excerpt: "Certain..."
keywords: ["permissions"]
procedures: 0
codeExamples: 0
---

Certain permissions can affect shift review. To view and edit permissions from Toast Web, choose Employees &gt; Employee management &gt; Jobs to open the Jobspage. Select the job title to edit the permissions.

Below is a list of permissions required to complete shift review or review your employees' shifts.


<table>
  <thead>
    <tr>
      <th>Access permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Table Service Mode</td>
      <td>**Gives access to**<ul><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li></ul>**Assign to**<ul><li>Employees</li></ul></td>
    </tr>
    <tr>
      <td>Quick Order Mode</td>
      <td>**Gives access to**<ul><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li></ul>**Assign to**<ul><li>Employees</li></ul></td>
    </tr>
    <tr>
      <td>Payment Terminal Mode</td>
      <td>**Gives access to**<ul><li>The Payment Terminal screen. Often assigned with Cash Drawer Access.</li><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li></ul>**Assign to**<ul><li>Employees</li></ul></td>
    </tr>
    <tr>
      <td>Delivery Mode (only required for drivers who need to complete shift review) </td>
      <td>**Gives access to**<ul><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li></ul>**Assign to**<ul><li>Delivery drivers</li></ul></td>
    </tr>
    <tr>
      <td>Shift Review </td>
      <td>**Gives access to**<ul><li>Employee's shift review report.</li><li>On the Toast POS home screen, gives access to Manager Activities > Shift Review and Manager Activities > Time Cards.</li></ul>**Assign to**<ul><li>Managers</li></ul></td>
    </tr>
    <tr>
      <td>Shift Review Sales Data </td>
      <td>**Gives access to**<ul><li>Detailed sales and payment data for shift review. Often assigned with the manager-level Shift Review permission, which provides access to restaurant-wide shift review.</li></ul>**Assign to**<ul><li>Employees and managers</li></ul></td>
    </tr>
  </tbody>
</table>

Below is a list of some commonly enabled permissions that can affect how your shift review behaves:


<table>
  <thead>
    <tr>
      <th>Access permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Cash Drawer Access </td>
      <td>**Gives access to**<ul><li>Cash drawers to complete cash payments. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.</li></ul></td>
    </tr>
    <tr>
      <td>Cash Drawers (Blind) </td>
      <td>**Gives access to**<ul><li>Manager Activities > Cash Drawers on the Toast POS home screen without reporting the expected cash amount. Must be assigned with Cash Drawer Access.</li></ul>This access is typically assigned to cashiers and others who need to close out and replace cash drawers at the end of their shift. </td>
    </tr>
    <tr>
      <td>Cash Drawers (Full) </td>
      <td>**Gives access to**<ul><li>Manager Activities > Cash Drawers on the Toast POS home screen including the starting balance and expected cash amounts. Must be assigned with Cash Drawer Access.</li></ul>This access is typically assigned to managers and others who need to close out and replace cash drawers at the end of their shift.  <br/> If you have both Cash Drawers (Blind) and Cash Drawer (Full) permission, the Cash Drawer (Full) permission overrides the Cash Drawer (Blind) permission. </td>
    </tr>
    <tr>
      <td>Close Out Day </td>
      <td>**Gives access to**<ul><li>The "Z report" sales summary for the current day, an optional report of check status and employee activity. Often assigned with Shift Review.</li><li>On the Toast POS home screen, gives access to Manager Activities > Close Out Day. When assigned with Sales Reports, the Full Sales Report option becomes functional for employees who have credentials for Toast Web.</li></ul></td>
    </tr>
  </tbody>
</table>

