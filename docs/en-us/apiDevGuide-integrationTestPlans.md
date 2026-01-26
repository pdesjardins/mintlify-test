---
title: "Integration test plans"
id: integrationTestPlans
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalChecklistsAndTestPlansOmitChunkFromSearchIndex.md
parentSectionTitle: "Checklists and test plans"
previousSectionFile: apiDevGuide-checklistsforSpecificIntegrationFunctionality.md
previousSectionTitle: "Checklists for specific integration functionality"
nextSectionFile: apiDevGuide-apiOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 2. Orders"
excerpt: "You can use these test plans to validate your integrations."
procedures: 0
codeExamples: 0
---

### Integration test plans

You can use these test plans to validate your integrations.

#### Gift card integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiGiftCardIntegrationAuthentication.html)the JSON objects you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-giftcard.csv).

| Case number | Card type | Test case name | Steps | Expected results | 
| --- | --- | --- | --- | --- |
| 1 | Non-Existent Card | Add Value | From the Toast POS app > New Order.Tap Gift Cards> Add Value ($).Enter any value, and click Next.Swipe or enter a number not associated with a gift card at that restaurant. | Gift card cannot be founderror message appears. | 
| 2 | Non-Existent Card | Balance Inquiry | From the Toast POS app > New Order.Tap Gift Cards> Balance Inquiry.Swipe or enter a number not associated with a gift card at that restaurant. | Gift card cannot be founderror message appears. | 
| 3 | Non-Existent Card | Redeem | From the Toast POS app > New Order.Add items to your order.Click Pay.Click Gift Card.Swipe or enter a number not associated with a gift card at that restaurant. | Gift card cannot be founderror message appears. | 
| 4 | Non-Existent Card | Sell Card | From the Toast POS app > New Order.Tap Gift Cards> Sell Card.Enter any value, and click `Next`.Swipe or enter a number not associated with a gift card at the restaurant. | Gift card cannot be founderror message appears. | 
| 5 | Inactive Card | Add Value | From the Toast POS app > New Order.Tap Gift Cards> Add Value ($).Enter any value, and click Next.Swipe an inactive gift card. | The gift card is inactiveerror message appears. | 
| 6 | Inactive Card | Balance Inquiry | From the Toast POS app > New Order.Tap Gift Cards> Balance Inquiry.Swipe an inactive gift card. | The gift card is inactiveerror message appears. | 
| 7 | Inactive Card | Redeem | From the Toast POS app > New Order.Add items to your order.Click Pay.Click Gift Card.Swipe an inactive gift card. | The gift card is inactiveerror message appears. | 
| 8 | Inactive Card | Sell Card | From the Toast POS app > New Order.Tap Gift Cards> Sell Card.Enter any value, and click Next.Swipe inactive gift card. | The gift card should display as an item selection on the check, for the amount for which you sold it. | 
| 9 | Inactive Card | Sell Card | Pay cash for the check you created in case 8, which contains the gift card. | You should be able to sell and pay for the gift card successfully. | 
| 10 | Inactive Card | Sell Card | From the Toast POS app > New Order.Tap Gift Cards> Balance Inquiry.Swipe the gift card. | The gift card's balance should be the amount for which you sold it. | 
| 11 | Inactive Card | Reverse Sell Card | Follow the steps from case 8.From the Toast POS app, navigate to the Closed Orderstab.Locate the check from your card sale.Click Update, then Pay, then Void. Confirm the void operation.In the overflow menu, click Void Order. Confirm the void operation.Create a new order.Click Gift Card.Click Balance Inquiry.Enter in the card number for the gift card you originally sold.Click Done. | The gift card is inactiveerror message appears. | 
| 12 | Active Card | Balance Inquiry | From the Toast POS app > New Order.Tap Gift Cards> Balance Inquiry.Swipe active gift card. | The balance should be the correct and expected balance on the card. | 
| 13 | Active Card | Redeem Full Order | From the Toast POS app > New Order.Add items to your order.Ensure that the total amount due is less than the amount on the gift card.Click Pay.Click Gift Card.Swipe an active gift card. | The order should go to the Paid Checkstab on the POS, and it should have a gift card payment for the full order amount. | 
| 14 | Active Card | Redeem Full Order | Run a balance inquiry on the card used in case 13. | The balance should be decremented by the amount of the previous order. | 
| 15 | Active Card | Redeem Partial Order | From the Toast POS app > New Order.Add items to your order.Ensure the total amount due is more than the amount on the gift card.Click Pay.Click Gift Card.Swipe an active gift card. | The Paymentsscreen will open.Verify that there is a gift card payment for the full amount of the gift card in the payments list.Verify that there is a balance due. | 
| 16 | Active Card | Redeem Partial Order | Complete the order from case 15 with a second payment. | The order should appear on the Paid Checkstab. | 
| 17 | Active Card | Redeem Partial Order | Run a balance inquiry on the card used in case 16. | The card balance should be $0. | 
| 18 | Active Card | Reverse Redeem | On the Paid Checkstab, locate one of the orders created and paid for in one of the previous two tests.Click Pay ($).Note the card number you use to pay for this order, and the amount of money for which you redeem it.Click each payment and press Remove/ Void.In the overflow menu, clock Void Order.Create a new order.Run a balance inquiry on the gift card for which you voided the payment. | The card balance should be incremented by the amount of the voided payment. | 
| 19 | Active Card | Tip Without Digital Receipts | On the the Toast POS app home screen, navigate to the Setupsection and click Device Setup.Turn off digital receipts.From the home screen, in the Mode section, click Payment Terminal.Create an order worth less than the value of an active gift card.Click Pay.Click Gift Card.On the Paid Checkstab, locate the previous check and click Pay ($).Enter in a tip that the gift card has enough money to cover.Click Update, and then Close. | The check should be moved to the Closed Checkstab. | 
| 20 | Active Card | Tip Without Digital Receipts | Run a balance inquiry on the card used in case 19. | The balance on the card should be decremented by the amount of the check and tip. | 
| 21 | Active Card | Tip With Digital Receipts | On the the Toast POS app home screen, navigate to the Setupsection and click Device Setup.Turn Digital Receipts on.From the home screen, in the Modesection, click Payment Terminal.Create an order worth less than the value on an active gift card.Click Pay.Click Gift Card.When the tip dialog appears, select a tip amount less than the gift card balance. This dialog does not allow you to tip more than the balance on the card.Complete the order. | The check should be moved to the Closed Checkstab. | 
| 22 | Active Card | Tip With Digital Receipts | Get the balance of the card used in case 21. | The balance on the card should be decremented by the amount of the check and tip. | 
| 23 | Active Card | Add Value | From the Toast POS app > New Order.Tap Gift Cards> Add Value ($).Enter any value, and click Next.Swipe an active gift card. | Verify that Add Value ($)is added to the check for the correct amount. | 
| 24 | Active Card | Add Value | Complete the order from case 23. | The check should move to the Closed Checkstab. | 
| 25 | Active Card | Add Value | Run a balance inquiry on the card used in cases 23-24. | The card balance should be increased by the correct amount. | 
| 26 | Active Card | Reverse Add Value | On the Closed Checkstab, find the order created in case 25.Click Pay ($).Void all payments.In the overflow menu, click Void Order.Confirm the void operation.Create a new order.Click Gift Cardand then click Balance Inquiry.Swipe the card whose Add Value action was voided. | The gift card balance should be decremented by the voided Add Value action. | 

#### Loyalty integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiLoyaltyIntegrationAuthentication.html)the JSON objects that you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-loyalty.csv).

| Case number | Category | Test case | Steps | Expected results | 
| --- | --- | --- | --- | --- |
| 1 | Account Lookup | Card swipe | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Swipe a card associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 2 | Account Lookup | Card swipe | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Swipe a card NOT associated with a loyalty account at that restaurant. | The Invalid Accounterror message should appear. | 
| 3 | Account Lookup | Card swipe | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Swipe a card that is NOT a loyalty account card. | The Card swiped is not a rewards carderror message should appear. | 
| 4 | Account Lookup | Keying in number | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Key in a card number associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 5 | Account Lookup | Scanning QR code | From the Toast POS app > New Order.Tap Rewards> Look Up Customer> Scan.Scan a QR code associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 6 | Account Lookup | Scanning QR code | From the Toast POS app > New Order.Tap Rewards> Look Up Customer> Scan.Scan a QR code NOT associated with a loyalty account at that restaurant. | The Invalid Accounterror message should appear. | 
| 7 | Account Lookup | By email | From the Toast POS app > New Order.Tap Rewards> Look Up Customer> Lookup.Key in an email address associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 8 | Account Lookup | By phone number | From the Toast POS app > New Order.Tap Rewards> Look Up Customer> Lookup.Key in a phone number associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 9 | Account Lookup | By name | From the Toast POS app > New Order.Tap Rewards> Look Up Customer> Lookup.Key in a name associated with a loyalty account at that restaurant. | The expected loyalty account should appear. | 
| 10 | Account Inquiry | Unavailable rewards | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards. | The expected rewards value should display, but because the awards are unavailable for redemption, you should not be able to apply them to a check. | 
| 11 | Account Inquiry | Available rewards | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer. | The expected rewards should be available redemption.A Redeembutton should be present. | 
| 12 | Account Inquiry | Rewards points | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards. | The expected rewards value should display on the dialog. | 
| 13 | Account Inquiry | Invalidated rewards | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer.Remove the items from your check.Tap Rewards> Look Up Customer. | The reward should be removed from the check.The error message Changes to the check have voided applied rewards. Discounts that are no longer applicable have been removedshould display. | 
| 14 | Redemption | Item-level discount | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer.Tap Redeemto add a reward to the check. | The reward should apply to the target item on the check.The amount discounted should be correct. | 
| 15 | Redemption | Item-level discount | Tap Pay. | The reward discount should be correctly carried to the payment screen. | 
| 16 | Redemption | Item-level discount | Complete payment on the check. | The payment should process successfully. | 
| 17 | Redemption | Check-level discount | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer.Tap Redeemto add a reward to the check. | The reward should apply to the check.The amount discounted should be correct. | 
| 18 | Redemption | Check-level discount | Tap Pay. | The reward discount should be correctly carried to the payment screen. | 
| 19 | Redemption | Check-level discount | Complete payment on the check. | The payment should process successfully. | 
| 20 | Redemption | Buy one get one discount | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer. | The expected reward should display, but should be unavailable for redemption. | 
| 21 | Redemption | Buy one get one discount | Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer. | The expected rewards should be available redemption.A Redeembutton should be present. | 
| 22 | Redemption | Buy one get one discount | Tap Redeemto add a reward to the check. | The reward should apply to the target item on the check.The amount discounted should be correct. | 
| 23 | Redemption | Buy one get one discount | Tap Pay. | The reward discount should be correctly carried to the payment screen. | 
| 24 | Redemption | Buy one get one discount | Complete payment on the check. | The payment should process successfully. | 
| 25 | Accrual and Reversal | Without reward applied to check | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items to the check.Tap Pay($). | The payment should process successfully.You should see the expected accrual message. | 
| 26 | Accrual and Reversal | Accrual reverse | On the Closed Checkstab, find the order placed in case 25.Tap Pay($).Void all payments.In the overflow menu, clock Void Order.Confirm the void operation. | The check should be successfully voided in Toast.You should see the expected reversal message. | 
| 27 | Accrual and Reversal | With reward applied to check | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer.Tap Redeemto add a reward to the check.Tap Pay.Complete payment on the check. | The payment should process successfully.You should see the expected accrual and redeem messages. | 
| 28 | Accrual and Reversal | Redemption reverse | On the Closed Checkstab, find the order placed in case 27.Tap Pay($).Void all payments.In the overflow menu, click Void Order.Confirm the void operation. | The check should be successfully voided in Toast,.You should see the expected reversal messages. | 
| 29 | Accrual and Reversal | With multiple rewards applied to check | From the Toast POS app > New Order.Tap Rewards> Look Up Customer.Look up a loyalty account that has associated rewards.Add items that would trigger rewards to the check.Tap Rewards> Look Up Customer.Tap Redeemto add a reward to the check.Repeat at least once in order to apply multiple rewards to the check.Tap Pay.Complete payment on the check. | The payment should process successfully.You should see the expected accrual and redeem messages. | 
| 30 | Accrual and Reversal | Partial redemption reverse | On the Closed Checkstab, find the order placed in case 29.Tap Update.Select a reward that was redeemed, and void it from the check.Tap Pay.Complete payment on the check. | The check should successfully close.You should see the expected reversal messages. | 

