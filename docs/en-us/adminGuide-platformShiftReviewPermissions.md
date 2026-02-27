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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Access permission</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Table Service Mode</div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">On the Toast POS home screen, gives access to My Account &gt; Shift Review.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Employees</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Quick Order Mode</div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">On the Toast POS home screen, gives access to My Account &gt; Shift Review.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Employees</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payment Terminal Mode</div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">The Payment Terminal screen. Often assigned with Cash Drawer Access.</li><li className="">On the Toast POS home screen, gives access to My Account &gt; Shift Review.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Employees</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Delivery Mode (only required for drivers who need to complete shift review) </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">On the Toast POS home screen, gives access to My Account &gt; Shift Review.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Delivery drivers</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Shift Review </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">Employee's shift review report.</li><li className="">On the Toast POS home screen, gives access to Manager Activities &gt; Shift Review and Manager Activities &gt; Time Cards.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Managers</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Shift Review Sales Data </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">Detailed sales and payment data for shift review. Often assigned with the manager-level Shift Review permission, which provides access to restaurant-wide shift review.</li></ul><strong className="">Assign to</strong> <ul className=""><li className="">Employees and managers</li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

Below is a list of some commonly enabled permissions that can affect how your shift review behaves:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Access permission</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Cash Drawer Access </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">Cash drawers to complete cash payments. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash Drawers (Blind) </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">Manager Activities &gt; Cash Drawers on the Toast POS home screen without reporting the expected cash amount. Must be assigned with Cash Drawer Access.</li></ul>This access is typically assigned to cashiers and others who need to close out and replace cash drawers at the end of their shift. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash Drawers (Full) </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">Manager Activities &gt; Cash Drawers on the Toast POS home screen including the starting balance and expected cash amounts. Must be assigned with Cash Drawer Access.</li></ul>This access is typically assigned to managers and others who need to close out and replace cash drawers at the end of their shift.  <br/> If you have both Cash Drawers (Blind) and Cash Drawer (Full) permission, the Cash Drawer (Full) permission overrides the Cash Drawer (Blind) permission. </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Close Out Day </div></td>
      <td className=""><div className=""><strong className="">Gives access to</strong> <ul className=""><li className="">The "Z report" sales summary for the current day, an optional report of check status and employee activity. Often assigned with Shift Review.</li><li className="">On the Toast POS home screen, gives access to Manager Activities &gt; Close Out Day. When assigned with Sales Reports, the Full Sales Report option becomes functional for employees who have credentials for Toast Web.</li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

