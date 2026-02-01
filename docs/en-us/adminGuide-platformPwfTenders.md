---
title: "Payment workflows"
id: platformPwfTenders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPwfOmitChunkFromSearchIndex.md
parentSectionTitle: "Payment workflows"
previousSectionFile: adminGuide-platformPwfAdjustments.md
previousSectionTitle: "Adjustments"
nextSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
nextSectionTitle: "Credit card payments"
externalReferences: [https://central.toasttab.com/s/article/Guest-Pay-and-Dual-Reader-Functionality-with-Toast-Tap, https://central.toasttab.com/s/article/Card-Pre-Authorization-Configuration-Device-Setup, https://central.toasttab.com/s/article/House-Accounts-1492809352564, https://central.toasttab.com/s/article/Setting-Up-Other-Payment-Options]
excerpt: "The following sections describe how to conduct cash, card, and other payments on your Toast POS application."
keywords: ["payment", "workflows"]
procedures: 0
codeExamples: 0
---

### Payment workflows

The following sections describe how to conduct cash, card, and other payments on your Toast POS application.

#### Cash

The following procedure describes the steps in the Toast POS system payment workflow when a guest uses cash to make a payment.

**Procedure 6.4. To pay a guest check with the Cash payment option**

1. Select Pay ($).


2. Enter a cash amount and select Cash. If you want to pay the check with the exact amount due, select a blue Fast Cash button or the Cash button without entering a transaction amount. Entering a total higher than the check amount displays the change due.

Fast Cash buttons close a transaction to the nearest currency amount, in increments of the next full currency amount, next five and next ten currency amounts. For example, if a transaction total is $12.98, the POS offers the option to submit either a $13.00, $15.00, or $20.00 payment.


3. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If Digital Receipts are not enabled, and a printer is configured, a Merchant Copy and a Customer Copy of the receipt are printed. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).


4. Payment is complete.


5. If your restaurant has a loyalty rewards program and digital receipts enabled, The guest-facing display asks the guest to sign up or enter their details to claim their points. You can skip this step.



#### Credit

The following procedure describes the steps in the Toast POS system payment workflow when a guest uses a credit or debit card to make a payment.

**Procedure 6.5. To pay a guest check with the Creditpayment option**

1. Select Pay ($).


2. Select Credit to process a card payment with an exact amount due.



> **Note**
> 
> You cannot enter a payment amount greater than the amount due, but you can enter an amount less than what is due to split payments.



3. Swipe, insert, or key in the guest's card details. If you select Key in card number, the Enter credit card number screen displays, and you can type in the guest's card number, card expiration date, card CVV, or security, code and zip code. Select Cancel payment to return to the previous screen.


4. The Toast POS device prompts the guest to select or enter a tip amount, and authorize the transaction with their signature.


5. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If Digital Receipts are not enabled, and a printer is configured, a Merchant Copy and a Customer Copy of the receipt are printed. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).


6. Payment is complete.


7. If your restaurant has a loyalty rewards program and digital receipts enabled, The guest-facing display asks the guest to sign up or enter their details to claim their points. You can skip this step.



If the Toast platform is unable to authorize the card payment for the transaction amount, the Toast POS app and guest-facing display show the Unable to process payment screen. You can select Cancel payment or Try another card.

#### Guest pay

Guest Pay puts the guest in control of completing their payment, and is supported for restaurants using dual card readers. Dual card reader capability is supported on Toast POS devices with multiple screens, such as the Toast Flex, where one screen faces the cashier, and another faces the guest. Guest Pay asks the guest to swipe, insert or tap their card. Card taps are supported with the Toast Tap device only. For more information on Guest Pay and dual reader functionality, see [Guest Pay and Dual Reader Functionality](https://central.toasttab.com/s/article/Guest-Pay-and-Dual-Reader-Functionality-with-Toast-Tap).

The following procedure describes the steps in the Toast POS system payment workflow when using guest pay to make a payment.

**Procedure 6.6. To pay a guest check with the Guest Paypayment option**

1. Select Pay ($).


2. Enter a transaction amount and select Guest Pay. If you want to pay the check with the exact amount due, select Guest Pay without entering a transaction amount.



> **Note**
> 
> You cannot enter a payment amount greater than the amount due, but you can enter an amount less than what is due to split payments.



3. The guest-facing display asks the guest to swipe, insert, or tap their card.


4. The guest-facing display asks the guest to select or enter a tip amount, and authorize the transaction with their signature. The cashier can also select Continue without tip or signature.


5. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If Digital Receipts are not enabled, and a printer is configured, a Merchant Copy and a Customer Copy of the receipt are printed. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).



If the Toast platform is unable to authorize the card payment for the transaction amount, the Toast POS app and guest-facing display show the Unable to process payment screen. You can select Cancel payment or Try another card.

#### Pre-authorizations

Pre-authorizations allow restaurant employees to save a guest’s card on a check and create a tab. You must configure the Toast platform settings for your restaurant to allow credit card preauthorization. See [this Toast Central article](https://central.toasttab.com/s/article/Card-Pre-Authorization-Configuration-Device-Setup) for more information on enabling pre-authorizations.



##### Pre-authorizing a card

Swipe the guest’s card directly on the order screen of a check that has not been paid for or otherwise closed. You can only pre-authorize a card that is swiped. Once a card is swiped, a green Pre-Authorized banner displays on the check. The following diagram shows a check with the pre-authorized banner.

![Diagram showing the pre-authorization banner on a check that has been pre-authorized.](https://doc.toasttab.com/doc/media/pre_auth_banner.png)

If a check does not contain the green Pre-Authorized indicator, then that check does not contain a pre-authorization.

##### Pre-authorization amounts

When you pre-authorize a card, you either authorize the current check total, or a configured minimum pre-authorization amount. You can set the minimum pre-authorization amount in Toast Web. The following table explains each pre-authorization use case.

| Pre-authorization use | Description | 
| --- | --- |
| No menu items on check | The guest's account is pre-authorized for the Minimum Pre-Authorization Amount found in Toast Web at Payments \> Payment methods \> Payment options. | 
| Menu items on check | The guest's account is pre-authorized in the amount of the current transaction subtotal. | 
| Menu items on check, but the check subtotal is not equal to or greater than the Minimum Pre-Authorization Amount | The guest's account is authorized for the Minimum Pre-authorization Amount. | 

##### Using a saved card

When you pre-authorize a guest’s card for an order, the Toast POS saves their credit card information for future use, as long as the order has not been closed.

After swiping a card on the order, select Pay ($) and you’ll see Saved CC on the payment screen. You can use the Saved CC function to apply a previously authorized credit card to an open order.

![Image](https://doc.toasttab.com/doc/media/pwfSavedCC.png)

**Procedure 6.7. To pay a guest check with the Saved CCpayment option**

1. Enter a transaction amount and select Saved CC. If you want to pay the check with the exact amount due, select Saved CC without entering a transaction amount.


2. Select Saved CC without entering an amount prior to charge the remaining amount due.



> **Note**
> 
> You cannot enter a payment amount greater than the amount due, but you can enter an amount less than what is due to split payments.



3. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If your restaurant has enabled digital receipts and you have configured a printer, the Toast POS device will print a Merchant Copy and a Customer Copy of the receipt. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).


4. If your restaurant has a loyalty rewards program and digital receipts enabled, The guest-facing display asks the guest to sign up or enter their details to claim their points. You can skip this step.



#### House accounts

House accounts allow restaurant guests to make purchases and receive an invoice for payment later. You can create, manage, and edit house accounts in Toast Web from Payments\> Payment methods \> House accounts. For more information on creating, managing, and using house accounts, see [House accounts](https://central.toasttab.com/s/article/House-Accounts-1492809352564).

**Procedure 6.8. To pay a guest check with the House Acctpayment option**

1. Select Pay ($).


2. Enter a transaction amount and select House acct. Select House acct without entering a transaction amount to tender the exact amount due. You cannot enter a payment amount greater than the amount due, but you can enter an amount less than the amount due to split payments. Selecting House acct displays the Enter Account Number screen.


3. Enter the guest's account number and select Done or select Lookup to [locate the guest account](platformPwfTenders.html#platformLookUpHouseAccount).


4. Confirm you want to charge the account you located by selecting Invoice. The Toast POS asks the guest to select a tip amount.


5. The guest-facing display asks the guest to select a tip amount.


6. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If Digital Receipts are not enabled, and a printer is configured, a Merchant Copy and a Customer Copy of the receipt are printed. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).



**Procedure 6.9. How to look up a house account**

If the Toast platform does not have a record for the guest, you must create a guest record from Toast Web.

1. Select House acct from the payment or order screen.



> **Note**
> 
> Selecting House Accounts from the order screen allows you to locate and pay the balance of an account.



2. Enter the guest's name, email address, guest number, or phone number and select Done.


3. Select the account to invoice and select Done.


4. Confirm the account to invoice by selecting Invoice.



#### Pay at a distance

Pay at a distance allows your guests to pay a check by receiving a text message with a payment link.

**Procedure 6.10. To pay a guest check with the Pay at a distance payment option**

1. Select Pay ($).


2. Enter a transaction amount and select Pay at a distance. If you select Pay at a distance without entering a transaction amount, you can pay the current amount due. Selecting Pay at a distance displays the PAY AT A SAFE DISTANCE screen.



> **Note**
> 
> You cannot enter a payment amount greater than the amount due, but you can enter an amount less than what is due to split payments.



3. You can select Send Payment Link to send a payment link via SMS (text) to the guest.


4. The guest is directed to pay their check via their mobile browser and must enter their email address where they'd like to receive their receipt.


5. Once paid, the guest is directed to a confirmation page on their mobile device.



#### Other payment workflows

The Other menu includes less commonly used, or custom, payment methods. You can configure other payment methods from Payments \> Other Payment Options in Toast Web.

Occasionally, you may create a custom payment method that is only intended for use with Toast's APIs that you want to hide from the Toast POS app. You can control other payment methods' visibility by selecting Yes or No for the Show on POS setting in Toast Web at Payments \> Other payment options. Select your payment method and scroll to find Show on POS.

![Image](https://doc.toasttab.com/doc/media/pwfOtherPaymentsShowOnPos.png)

##### Room charge



> **Note**
> 
> The room charge payment option is only available if your restaurant has a hotel integration.


The room charge payment option allows restaurant employees to search for a hotel guest and post restaurant charges to the guest's folio, or list of charges. The following procedure describes how a hotel integrated restaurant can use the room charge payment option.



> **Note**
> 
> For the purpose of this example, the room charge payment option is titled Room charge. Your restaurant's room charge payment option may be titled differently.


**Procedure 6.11. To charge a hotel guest using a room charge payment**

1. Select Tab name to give your guest's order an identity. Selecting Tab namedisplays the Enter Tab Name screen.

![The location of the Tab name button on the order screen.](https://doc.toasttab.com/doc/media/pwfHotelTabButton.png)


2. Enter the guest's room number, name, or both and select Set Tab Name.

![The location of the Set tab name button on the Enter tab name (or swipe card) dialog.](https://doc.toasttab.com/doc/media/pwfHotelEnterTabName.png)


3. Select Other payments on the check's payment screen. Selecting Other paymentsdisplays the Select alternate payment type screen.

![The location of the Other payments button on the payment screen.](https://doc.toasttab.com/doc/media/pwfOtherPaymentsButton.png)


4. Select Room charge. Selecting the room charge payment option opens the Lookup Hotel Guest screen.

![The Room Charge payment option on the Select alternate payment type dialog.](https://doc.toasttab.com/doc/media/pwfRoomChargeButton.png)


5. Enter your guest search criteria and select Submit. All records for guests that are currently checked into the hotel, matching your search criteria either completely or partially, are displayed. For example, if you search for room 123, and rooms 123 and 1234 are checked in, your results will display both rooms. To display all records select Submit with no search criteria.

![The Lookup Hotel Guest screen with search criteria.](https://doc.toasttab.com/doc/media/pwfHotelSubmitSearch.png)


6. Select the appropriate room to charge.



##### Customer credits

Customer credits allow your management to award guests with a credited balance redeemable at your restaurant. 



> **Note**
> 
> Customer Credits must be enabled in Toast Web from Payments \> Payment methods \> Customer credits.


**Procedure 6.12. To pay a guest check with the Customer credits payment option**

1. From the payment screen, select Other \> Customer Credits.


2. Enter the guest's phone number and select their account.



> **Note**
> 
> You can add guest information on a Toast POS device from Manager Activities \> Lookup customer.



3. Enter the amount of credits to redeem and select Redeem. If the guest would like to use all of their available credits, you can select APPLY ALL. If the guest's credit balance is more than their check, using the APPLY ALL button auto-fills the Amount Applied field with the current balance due.


4. Continue accepting payment for the remaining balance.



##### Custom payments

You can create custom payment options to fit your business. On Toast Web, navigate to Payments \> Payment methods \> Other payment options. For more information about creating other payment types see [Setting up other payment options](https://central.toasttab.com/s/article/Setting-Up-Other-Payment-Options). The following sections details custom payment options that are often created by restaurant operators.

###### Gift certificate (paper)

**Procedure 6.13. To pay a guest check with a custom gift certificate (paper) payment option**

1. Enter the amount of the gift certificate and select Other.


2. Select Gift Certificate (Paper). If you select Gift Certificate (Paper) without entering a transaction amount, the Toast POS app automatically enters the entire balance due as the gift certificate payment amount.


3. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If your restaurant has enabled digital receipts and you have configured a printer, the Toast POS device will print a Merchant Copy and a Customer Copy of the receipt. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).



###### Check

**Procedure 6.14. To pay a guest check with a custom check payment option**

1. Enter the amount of the check and select Other.


2. Select Check. If you select Check without entering a transaction amount, the Toast POS app automatically enters the entire balance due as the check payment amount.


3. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If your restaurant has enabled digital receipts and you have configured a printer, the Toast POS device will print a Merchant Copy and a Customer Copy of the receipt. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).



###### Non-integrated third party payments

Restaurants can create a custom payment option for a non-integrated third party takeout or delivery service. This may be useful if your restaurant's takeout or delivery service transactions are managed outside of your Toast POS platform.



> **Note**
> 
> Creating a custom payment option does not create or enable an integration with a third-party service. Orders closed this way will not satisfy any requirements for closing orders from your delivery or takeout partner.


**Procedure 6.15. To pay a guest check with a custom takeout or delivery service payment option**

1. Enter the amount of the check and select Other.


2. Select the tender option for the delivery or takeout platform that you configured for your restaurant. If you select the delivery option tender without entering a transaction amount, the POS assumes the check is valid for the entire balance due.


3. The guest-facing display asks the guest to select one of the following receipt options if digital receipts are enabled:

- Print


- Text


- Email


- No receipt



If your restaurant has enabled digital receipts and you have configured a printer, the Toast POS device will print a Merchant Copy and a Customer Copy of the receipt. For more information about Digital Receipts see [Digital receipts and printed receipts](platformPwfDigitalReceipts.html).



