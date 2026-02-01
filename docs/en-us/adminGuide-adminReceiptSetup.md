---
title: "Configuring customer printed receipts"
id: adminReceiptSetup
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPaymentsAndMoneyOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 6. Payments and money"
previousSectionFile: adminGuide-adminMarketplaceFacilitatorTaxPayments.md
previousSectionTitle: "Marketplace facilitator tax payments"
nextSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
nextSectionTitle: "Offline support"
excerpt: "The Receipt Setup page allows you to set the configuration of printed customer receipts. These receipts include: Initial check (payment screen > Print) Cash payment receipt Credit card receipt, both..."
procedures: 1
codeExamples: 0
---

The Receipt Setup page allows you to set the configuration of printed customer receipts. These receipts include:

- Initial check (payment screen > Print)


- Cash payment receipt


- Credit card receipt, both merchant copy and customer copy


- Gift card receipt


- Alternative payment type receipt


- House account receipt


- Voided payment receipt



The configuration you create will apply to all receipt printers; that is, you cannot create individual custom configurations for different printers.



> **Note**
> 
> The receipts described in this section are intended for customer use, such as a credit card receipt that the customer will fill out and sign. Kitchen tickets (used by the kitchen staff for fulfilling orders) are configured on the Kitchen > Printers, tickets, & KDS devices > [Kitchen](adminKitchenDiningRoomReference.html#adminKitchenSetupReference) page, and are not discussed here.


Before you configure your receipts, make sure that you have performed these tasks:

- Configure your printers by using the Printers and Cash Drawers page (choose the Payments > Checks & receipt setup > Printers and cash drawersmenu).


- Configure your Toast POS devices to access the networks on which the printers are located.


- Configure the receipt printer on your Toast POS devices by tapping Setup > Device Setup > Receipt Printer and choosing a receipt printer.



By configuring your Toast POS device, you can test your receipt setup changes and adjust them as needed.

To configure receipts, you need Restaurant Admin > POS Setup permission to access the Receipt Setup Toast Web page. For more information, see the [Access Permission Reference](adminPermissions.html#adminRestaurantAdminAccessPermissions).

**Procedure 6.126. To configure customer printed receipts**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Select Payments > Checks & receipt setup > Guest receipt setup to open the Receipt Setup page.


3. If configuring for a multi-location restaurant, select the name of the receipt you want to edit. 


4. Enter the Basic configuration of the receipt:

- Header: Enter the text that will be printed at the top of the receipt. Each row of the receipt header can have a maximum of 42 characters.


- Footer: Enter the text that will be printed at the bottom of the receipt. Each row of the receipt footer can have a maximum of 42 characters.


- Logo: To add an image at the top of the receipt, click Choose Image, and navigate to the image file (which should be a JPEG or PNG format), and open it. The logo should be a 360-pixel square image. Note that an image that is too large will be re-sized to fit.




5. Enter the Advancedconfiguration:

- Free Modifiers: Select whether free modifiers should be listed on Dine-In receipts. Free modifiers do not have a listed price and thus are free of charge to guests. Selecting Don't Show results in a less-cluttered receipt, as the modifiers that do not contribute to the check price are not listed.


- Service Charges Font: Select the font size for the service charges printed on the receipt. The Normal font prints the same size as the other items on the receipt, whereas the Large font prints the service charge at a larger size than the other items.


- Print Payments: Select whether the receipt should show all the completed payments on the customer's full check, from the Order screen.

Note that if you select Don't Show, other payment types handled as discounts will still print on the receipt. To configure these discounted other payment types, choose Payments > Payment methods > Other payment options, select the payment option name, and select Yes for the Treat as Discount option.


- Itemize Quick Order Receipts: Specify whether receipts printed from Quick Order mode are always itemized. Note that this field does not affect receipts printed from Table Service mode.

Quick Order itemized receipts are useful for credit card payments, because the receipt is not printed prior to swiping the credit card. Therefore, you need the itemized list of items on the signed copies (receipt and the signing is combined).


- Hide Modifier Prices: Select Yes to omit the prices of modifiers (the modifier prices are included in the price of the main item) or No to print the individual modifier prices.


- Display Tip Line: Specify whether to print a tip line on credit card receipts. If enabled, a tip line (labelled + Tip) is printed below the check amount and a total line (labelled = Total) is also printed, so that the customer can add the pre-tip check amount and the tip amount for the total payment.


- Tip Line with Gratuities: Specify the label used on guest checks that include a gratuity. You can select either "Additional Tip" or "Tip".


- Combine items on receipt: Select Yes to combine multiple identically-named items under one name and also combine their price under one amount, or No to list each item separately by name and by price. For example, if the table has ordered two servings of Crab Cakes at $8.99 each, then a setting of Yes will print "2 Crab Cakes" once with an amount of $17.98, whereas a setting of Nowill print "Crab Cakes" twice, each with an amount of $8.99.


- Display Tip Percentages on Customer Receipts: Specify whether suggested tip amounts are printed on the merchant copy of credit card, cash, or itemized receipts. If enabled, the tip heading is labelled Suggested Tip (if a gratuity service charge is not applied) or Suggested Additional Tip(if a gratuity service charge is applied). The suggested tip percentages are set in the Customized Tip Percentages field (on the Front of house > Order screen setup > UI options page). Note that if you enable this field, you should also enable the Display Tip Line field.


- Display Charity Tip Line: Select Yes to include a tip line for a charity donation or No to omit the line on printed credit card receipts. Selecting Yes displays the Charity Tip Line Message field, which lets you enter a label (of 12 or fewer characters) for the charity line. The setting for this option has no effect on digital receipts.


- Closed Check Receipt: Specify whether the receipt is printed automatically after closing the check or printed only on demand.




6. When you have finished, click Save.

If saved successfully, you should see the message: Receipt Setup saved successfully. Publish Now.


7. Click the Publish Now link.



