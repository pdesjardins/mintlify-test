---
title: "User permissions for cash management"
id: adminUserPermissionsCashMgmt
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDeposits.md
previousSectionTitle: "Cash deposits"
nextSectionFile: adminGuide-platformDeprecatedCashManagement.md
nextSectionTitle: "Deprecated cash management"
excerpt: "When assigning permissions, the best practice is to use job-based permissions..."
keywords: ["user", "permissions", "cash", "management"]
procedures: 0
codeExamples: 0
---

When assigning permissions, the best practice is to use job-based permissions instead of employee-based permissions. That is, you assign permissions to a job and then assign employees to that job, instead of assigning individual permissions

The following table lists the permissions that are required for specific cash management tasks.


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>Cash Management Task</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Open the cash drawer in order to provide change and finalize cash transactions.</td>
      <td>POS Access &gt; Cash Drawer Access</td>
    </tr>
    <tr>
      <td>Accept a cash payment against a check with an open balance due. In addition to this permission, the employee's Toast POS device must have the Allow Cash Payments device setting enabled.</td>
      <td>POS Access &gt; Apply Cash Payments</td>
    </tr>
    <tr>
      <td><a href="adminGuide-adminUndoingOperations">Undo cash entries</a> in a cash drawer. Also allows the No Sale button to be displayed on the Order screen while in Quick Order mode. Use the No Sale button to open the cash drawer without having to complete a transaction. This permission also allows employees to do their own shift reviews.</td>
      <td>POS Access &gt; No Sale</td>
    </tr>
    <tr>
      <td>Full Access permits the employee to view the expected cash amounts in cash drawers during and at the end of shifts. This permission also allows the employee to open the cash drawer as well as close out and replace cash drawers at the end of shifts. <br/> For an employee to access the Reports &gt; Cash and loss management &gt; Drawer history and Cash activity audit reports on a POS device, must have the Restaurant Admin &gt; 4.1 Sales Reports permission assigned.</td>
      <td>Manager &gt; Cash Drawers (Full)</td>
    </tr>
    <tr>
      <td>Blind Access does not allow the employee to view the expected cash amounts in cash drawers during and at the end of shifts. This permission, however, does allow the employee to open the cash drawer as well as close out and replace cash drawers at the end of shifts. <br/> Recommended for a cashier who closes a shift by counting cash in the drawer without knowing what the expected amount should be, while also being able to do other cash adjustments.</td>
      <td>Manager &gt; Cash Drawers (Blind)</td>
    </tr>
    <tr>
      <td>Take payments and put money in cash drawers that are locked to other users. This permission also allows the employee to close any cash drawer and (if they also have the Manager &gt; 3.22 Pay Out permission) to authorize pay outs from any cash drawer.</td>
      <td>Manager &gt; Cash Drawer Lockdown (Override)</td>
    </tr>
    <tr>
      <td>Input or approve a large cash over/under amount while closing out a cash drawer. The threshold for this amount is set on the Payments &gt; Payment methods &gt; Cash overview &gt; Cash drawer variance &gt; Cash drawer variance screen. </td>
      <td>Manager &gt; Large Cash Over/Under</td>
    </tr>
    <tr>
      <td>Adjust the starting balance of a cash drawer.</td>
      <td>Manager &gt; Adjust Cash Drawer Start Balance</td>
    </tr>
    <tr>
      <td>Take a cash payment from the restaurant (house) or any cash drawer that is not locked to a different employee.</td>
      <td>Manager &gt; Pay Out</td>
    </tr>
    <tr>
      <td>Access the Reports &gt; Sales &gt; Sales summary report and use the Sales Summary, Orders, Order Details, Payments, Shifts, Cash Activity Audit, and Cash Drawer History report tabs for order details, transaction details, shifts, and cash information. <br/> For an employee to access the Cash Drawer History and Cash Activity Audit reports on a POS device, must have the the 3.18 Cash Drawers (Full) permission assigned.</td>
      <td>Restaurant Admin &gt; Sales Reports</td>
    </tr>
  </tbody>
</table>
</div>

