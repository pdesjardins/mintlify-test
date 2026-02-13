---
title: "Configuring your shift review"
id: platformConfiguringShiftReview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformShiftReviewPermissions.md
previousSectionTitle: "Permissions"
nextSectionFile: adminGuide-platformAccessingShiftReview.md
nextSectionTitle: "Accessing shift review"
externalReferences: [https://central.toasttab.com/s/article/Customizing-Shift-Review-Settings#Require, https://central.toasttab.com/s/article/Manager-Activities-Cash-Management-1493049150424, https://central.toasttab.com/s/article/Adjusting-Your-Starting-Cash-Drawer-Balance]
excerpt: "You configure your shift review settings in Toast Web ."
keywords: ["configuring", "shift", "review"]
procedures: 0
codeExamples: 0
---

You configure your shift review settings in [Toast Web
    ](adminGuide-adminAccessToastAdminBackend).

## Requiring shift review

Certain job roles may require employees to complete shift review
      before clocking out. On the Shift review page, you
      can customize your Require shift review setting to
      require employees to complete shift review before clocking out. For more
      information about requiring employees to complete shift review before
      clocking out, see [Customizing
      Shift Review Settings](https://central.toasttab.com/s/article/Customizing-Shift-Review-Settings#Require).

**Procedure 6.105. To require employees to complete shift review before clocking
        out**

1. [Access Toast
          Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Employees > Shift review > Shift review
          setup to open the Shift review setup
          page.


3. On the Require shift review page, select
          if shift review is required or optional for employees:

- Shift review is required: Employees
              who are hourly and have the following permissions are required
              to complete shift review:

- Table Service Mode


- Payment Terminal Mode


- Quick Order Mode


- Delivery Mode (if applicable)





> **Note**
> 
> If you try to clock out without completing your shift
                review, an error appears with the following message: `You must close your shift before clocking out`.



- Shift review is optional: Employees
              are not required to complete shift review before clocking
              out.





The Toast platform automatically saves your changes. Select the
      Publish all changes button to publish your
      changes.

## Configuring your cash drawer and cash balance

You can configure and assign a cash drawer to an employee to use
      during their shift. If an employee is assigned a cash drawer, then they
      must complete the additional step of closing the cash drawer for shift
      review. For more information about how to use cash drawers, see [Using
      Cash Drawers During Your Shift](https://central.toasttab.com/s/article/Manager-Activities-Cash-Management-1493049150424).

From Toast Web, you can configure, adjust, and choose how to reset
      the starting balance in your cash drawer. To configure, adjust, or
      choose how to reset your starting cash drawer balance, choose
      Payments > Payment methods > Cash overview > Cash
      drawers > View cash drawers to open the Cash
      drawers page.

For more information about cash drawers, see [Adjusting
      Your Starting Cash Drawer Balance](https://central.toasttab.com/s/article/Adjusting-Your-Starting-Cash-Drawer-Balance).

## Configuring your shift review report

You can configure the information that appears on your shift
      review report. The shift review report is a summary of activity
      completed during your shift. You can configure your shift review report
      in Toast Web.



> **Note**
> 
> You can change the order the sections appear in the shift review
        report. To move a section, select and drag the grid icon next to the
        section up or down.


**Procedure 6.106. To configure your shift review report**

1. [Access Toast
          Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Employees > POS report configurations >
          Shift review report to open the Shift review
          report page.


3. On the Shift review report page, select
          the sections you want to enable:

- Tips & Fees Earned


- My Guest Report


- Employee Account


- Credit Tip Audit


- Tip Sharing


- Delivery


- Sales & Taxes Summary


- Cash/Credit Per Sales Category


- Revenue Centers


- Total Voids


- Total Removals


- Total Discounts


- Total Payments


- Credit Card Breakdown


- Other Breakdown


- Employee Signature


- Pay Outs





The Toast platform automatically saves your changes. Select the
      Publish all changes button to publish your changes.
      For more information on shift review report configurations, see [Shift review
      / closeout](adminGuide-adminUiOptionsReference).

## Shift review report configurations

The sections included in your shift review report reflect your
      selections in the Shift review report section on
      the Shift review page. Each shift review report
      section contains rows that display the activity completed during your
      shift.

The following table lists the shift review report row, a
      description of the row, and any permissions or settings required to
      display the row.

| Shift review report row | Description | Required permissions and settings | 
| --- | --- | --- |
| Employee Account
              heading | 
| Cash in hand (collected cash sales)  | Total amount of cash payments taken by an employee
              that is kept separately in their own cash bank.  | Apply Cash Payments
              permission. | 
| Cash in drawer | Total amount of cash payments taken by an employee
              and placed into a cash drawer.  | Shift Review Sales Data
              permission. **In the Toast POS app **- Setup > Device Setup > Open Cash
                        Drawer > Yes
- Setup > Device Setup > Receipt
                        Printer 

 | 
| Driver bank  | Starting cash balance for drivers to use during
              their shift.  | **In Toast Web **- Takeout & delivery >
                        Availability > Takeout / delivery > Driver cash
                        management > Assign driver bank > Yes, assign
                        driver bank for reporting

 | 
| Total gratuity and fees  | Total gratuity and fees to be paid out to the
              employee.  | **In Toast Web **- Employees > Shift review >
                        Payout options 

 | 
| Non-cash tips (%)  | Total amount of non-cash tips to be paid out to the
              employee.  | **In Toast Web **- Employees > Shift review >
                        Payout options 

 | 
| Tips withheld (%)  | Total amount of tips withheld by the restaurant to
              cover the cost of credit card processing fees.  | **In Toast Web **- Employees > Shift review >
                        Payout options 
- Employees > Payroll management >
                        Tip withholding > Enable house tip
                        withholding

 | 
| Driver reimbursement  | Total amount a driver is reimbursed for wear and
              tear of their personal vehicle used for delivery.
               | Requires a Driver job.
              **In Toast Web **- Takeout & delivery >
                        Availability > Takeout / delivery > Driver
                        reimbursement > Reimburse drivers > Yes,
                        reimburse drivers for each delivery order
                        completed

 | 
| Employee owes restaurant or restaurant owes
              Employee | Total amount that the employee owes the restaurant
              or is owed by the restaurant to the employee.  |  | 
| Tips & Fees
              Earned heading | 
| Cash tips (declared)(%)  | Total cash tips. | Requires a Tipped job.
              **In Toast Web **- Employees > Shift review > Shift
                        review setup > Declare cash tips 

 | 
| Total tips & fees | Total tips and fees are calculated as:
              Non-cash tips (ex: credit card
              payment tips) +Non-cash
              gratuity and cash automatic
              gratuity (ex: service charges)
              +Total driver reimbursements
              +Declared cash tips (ex: cash
              tips declared during shift review) -House
              tip share (ex: tip withholding reclaims a portion of
              employee credit card tips to cover processing
              fees) |   | 
| My Guest Report
              heading | 
| Total guests served  | Total guests served.  |  | 
| Average spend per guest  | Average spend per guest.  |  | 
| Credit Tip Audit
              heading | 
| Credit tip audit  | Displays total credit card tips amount. Fields
              include: - Check number
- Last four digits of the credit card
- Subtotal
- Tip (if applicable)
- Order total

 |  | 
| Tip Sharing
              heading | 
| Sales category (%)  | Total tip amount per sales category.
               | **In Toast Web **- Employees > Shift review > Shift
                        review report > Tip sharing

 | 
| Total  | Total tip sharing amount.  |   | 
| Delivery
              heading | 
| Fees to the driver  | Delivery driver fees.  | **In Toast Web **- A service charge must be configured.
- Payments > Checks & receipt
                        setup > Service charges 

 | 
| Fees  | Applicable driver fee per check. Includes check
              number and gross sales.  |  | 
| Reimbursement  | Applicable driver reimbursement per check. Includes
              check number and gross sales.  |  | 
| Sales & Tax
              Summary heading | 
| Sales category  | Total number of items and net sales per sales
              category.  | **In Toast Web **- A sales category must be configured.
- Menus > Settings > Sales
                        categories

 | 
| Non-grat svc charges  | Total non-gratuity collected by the restaurant and
              added to the restaurant’s net sales amount. | **In Toast Web **- A service charge must be configured.
- Payments > Checks & receipt
                        setup > Service charges 

 | 
| Deferred amount  | Total amount that is excluded from the restaurant’s
              net sales. | **In Toast Web **- Menus > Bulk management >
                        Advanced properties > Select your item >
                        Reporting > Defer Revenue >
                        Yes

 | 
| Total net sales  | Total paid by guests for menu item selections and
              services charges. |  | 
| Tax  | Applicable tax amount.  |  | 
| Gross sales  | Total amount of (non-gratuity) services and items
              sold before deductions are taken. |  | 
| Total amount  | Total amount of Gross sales +
              Total gratuity and fees +
              Non-cash tips.  |  | 
| Paid in total  | Total amount of payments for future orders
              completed within the date range. |  | 
| Cash/Credit Per
              Sales Category heading | 
| Cash sales by sales category | Total number of items and cash sales per sales
              category.  |  | 
| Non-cash sales by sales category | Total number items and non-cash sales per sales
              category.  |  | 
| Revenue Centers
              heading | 
| Revenue center  | Total amount of revenue center sales. The total
              amount does not include taxes.  | **In Toast Web **- A revenue center must be configured.
- Front of house > Tables &
                        sections > Revenue centers 

 | 
| Total Voids
              heading | 
| Void amount  | Total void amount.  |  | 
| Void order count  | Total number of voided orders. |  | 
| Void item count  | Total number of voided items.  |  | 
| Void percent  | Percentage of total orders voided.  |  | 
| Total Removals
              heading | 
| Removal amount  | Total amount removed from checks.  | **In Toast Web **- Employees > Shift review > Shift
                        review report > Total removals 

 | 
| Removed item count  | Total number of items removed from
              checks. | **In Toast Web **- Employees > Shift review > Shift
                        review report > Total removals 

 | 
| Total Discounts
              heading | 
| Discount name  | Total number of discounts applied and discount
              amount.  | **In Toast Web **- A discount must be configured.
- Payments > Comps and promos >
                        Discounts and promo codes 

 | 
| Total Payments
              heading | 
| Amount (number of checks)  | Total number of checks and credit and cash
              payments.  |  | 
| Tips (%)  | Total percentage and amount of credit and cash
              tips.  |  | 
| Gratuity  | Total amount of credit and cash gratuities.
               |  | 
| Total  | Total amount of payments, tips, and gratuities.
               |  | 
| Deposit sales collected  | Total amount of payments for future orders
              completed within the date range. |  | 
| Credit Card
              Breakdown heading: A section is created for each
              credit card type used during shift review | 
| Credit card name  | Amount paid with that credit card type.
               |  | 
| Other Breakdown
              heading: A section is created for each alternate
              payment type used during shift review | 
| Alternate payment name  | Amount paid with that alternate payment type.
               |  | 
| Pay Outs
              heading | 
| Name of pay out  | Total cash amount removed from a cash drawer per
              pay out. |  | 
| Total pay outs | Total pay out amount.  |  | 
| Employee Account
              heading | 
| Total guests served  | Total number of guests served during your shift.
               |  | 
| Average spend per guest | Total average spend per guest per check.
               |  | 
| Employee
              Signature heading | 
| Employee x  | Employee signature line.  |  | 
| Cash received by | Employee receiving cash deposits signature line.
               |  | 

