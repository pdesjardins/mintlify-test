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

You can use these test plans to validate your integrations.

## Gift card integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiDevGuide-apiGiftCardIntegrationAuthentication)the JSON objects you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-giftcard.csv).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Case number</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Card type</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Test case name</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Steps</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Expected results</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">1</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-Existent Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Add Value ($).</p> <p className="text-base leading-relaxed">Enter any value, and click Next.</p> <p className="text-base leading-relaxed">Swipe or enter a number not associated with a gift card at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gift card cannot be found error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">2</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-Existent Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Balance Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Balance Inquiry.</p> <p className="text-base leading-relaxed">Swipe or enter a number not associated with a gift card at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gift card cannot be found error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">3</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-Existent Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Add items to your order.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">Swipe or enter a number not associated with a gift card at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gift card cannot be found error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">4</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-Existent Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sell Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Sell Card.</p> <p className="text-base leading-relaxed">Enter any value, and click <code className="font-mono text-sm">Next</code>.</p> <p className="text-base leading-relaxed">Swipe or enter a number not associated with a gift card at the restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gift card cannot be found error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Add Value ($).</p> <p className="text-base leading-relaxed">Enter any value, and click Next.</p> <p className="text-base leading-relaxed">Swipe an inactive gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card is inactive error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">6</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Balance Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Balance Inquiry.</p> <p className="text-base leading-relaxed">Swipe an inactive gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card is inactive error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">7</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Add items to your order.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">Swipe an inactive gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card is inactive error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">8</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sell Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Sell Card.</p> <p className="text-base leading-relaxed">Enter any value, and click Next.</p> <p className="text-base leading-relaxed">Swipe inactive gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card should display as an item selection on the check, for the amount for which you sold it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">9</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sell Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Pay cash for the check you created in case 8, which contains the gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You should be able to sell and pay for the gift card successfully.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">10</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sell Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Balance Inquiry.</p> <p className="text-base leading-relaxed">Swipe the gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card's balance should be the amount for which you sold it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">11</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Inactive Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reverse Sell Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Follow the steps from case 8.</p> <p className="text-base leading-relaxed">From the Toast POS app, navigate to the Closed Orders tab.</p> <p className="text-base leading-relaxed">Locate the check from your card sale.</p> <p className="text-base leading-relaxed">Click Update, then Pay, then Void. Confirm the void operation.</p> <p className="text-base leading-relaxed">In the overflow menu, click Void Order. Confirm the void operation.</p> <p className="text-base leading-relaxed">Create a new order.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">Click Balance Inquiry.</p> <p className="text-base leading-relaxed">Enter in the card number for the gift card you originally sold.</p> <p className="text-base leading-relaxed">Click Done.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card is inactive error message appears.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">12</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Balance Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Balance Inquiry.</p> <p className="text-base leading-relaxed">Swipe active gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The balance should be the correct and expected balance on the card.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">13</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem Full Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Add items to your order.</p> <p className="text-base leading-relaxed">Ensure that the total amount due is less than the amount on the gift card.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">Swipe an active gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The order should go to the Paid Checks tab on the POS, and it should have a gift card payment for the full order amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">14</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem Full Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Run a balance inquiry on the card used in case 13.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The balance should be decremented by the amount of the previous order.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">15</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem Partial Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Add items to your order.</p> <p className="text-base leading-relaxed">Ensure the total amount due is more than the amount on the gift card.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">Swipe an active gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Payments screen will open.</p> <p className="text-base leading-relaxed">Verify that there is a gift card payment for the full amount of the gift card in the payments list.</p> <p className="text-base leading-relaxed">Verify that there is a balance due.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">16</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem Partial Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Complete the order from case 15 with a second payment.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The order should appear on the Paid Checks tab.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">17</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redeem Partial Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Run a balance inquiry on the card used in case 16.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The card balance should be $0.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">18</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reverse Redeem</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Paid Checks tab, locate one of the orders created and paid for in one of the previous two tests.</p> <p className="text-base leading-relaxed">Click Pay ($).</p> <p className="text-base leading-relaxed">Note the card number you use to pay for this order, and the amount of money for which you redeem it.</p> <p className="text-base leading-relaxed">Click each payment and press Remove / Void.</p> <p className="text-base leading-relaxed">In the overflow menu, clock Void Order.</p> <p className="text-base leading-relaxed">Create a new order.</p> <p className="text-base leading-relaxed">Run a balance inquiry on the gift card for which you voided the payment.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The card balance should be incremented by the amount of the voided payment.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">19</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tip Without Digital Receipts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the the Toast POS app home screen, navigate to the Setup section and click Device Setup.</p> <p className="text-base leading-relaxed">Turn off digital receipts.</p> <p className="text-base leading-relaxed">From the home screen, in the Mode section, click Payment Terminal.</p> <p className="text-base leading-relaxed">Create an order worth less than the value of an active gift card.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">On the Paid Checks tab, locate the previous check and click Pay ($).</p> <p className="text-base leading-relaxed">Enter in a tip that the gift card has enough money to cover.</p> <p className="text-base leading-relaxed">Click Update, and then Close.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should be moved to the Closed Checks tab.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">20</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tip Without Digital Receipts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Run a balance inquiry on the card used in case 19.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The balance on the card should be decremented by the amount of the check and tip.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">21</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tip With Digital Receipts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the the Toast POS app home screen, navigate to the Setup section and click Device Setup.</p> <p className="text-base leading-relaxed">Turn Digital Receipts on.</p> <p className="text-base leading-relaxed">From the home screen, in the Mode section, click Payment Terminal.</p> <p className="text-base leading-relaxed">Create an order worth less than the value on an active gift card.</p> <p className="text-base leading-relaxed">Click Pay.</p> <p className="text-base leading-relaxed">Click Gift Card.</p> <p className="text-base leading-relaxed">When the tip dialog appears, select a tip amount less than the gift card balance. This dialog does not allow you to tip more than the balance on the card.</p> <p className="text-base leading-relaxed">Complete the order.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should be moved to the Closed Checks tab.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">22</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tip With Digital Receipts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Get the balance of the card used in case 21.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The balance on the card should be decremented by the amount of the check and tip.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">23</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Gift Cards &gt; Add Value ($).</p> <p className="text-base leading-relaxed">Enter any value, and click Next.</p> <p className="text-base leading-relaxed">Swipe an active gift card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Verify that Add Value ($) is added to the check for the correct amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">24</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Complete the order from case 23.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should move to the Closed Checks tab.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">25</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Run a balance inquiry on the card used in cases 23-24.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The card balance should be increased by the correct amount.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">26</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Active Card</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reverse Add Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Closed Checks tab, find the order created in case 25.</p> <p className="text-base leading-relaxed">Click Pay ($).</p> <p className="text-base leading-relaxed">Void all payments.</p> <p className="text-base leading-relaxed">In the overflow menu, click Void Order.</p> <p className="text-base leading-relaxed">Confirm the void operation.</p> <p className="text-base leading-relaxed">Create a new order.</p> <p className="text-base leading-relaxed">Click Gift Card and then click Balance Inquiry.</p> <p className="text-base leading-relaxed">Swipe the card whose Add Value action was voided.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The gift card balance should be decremented by the voided Add Value action.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Loyalty integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiDevGuide-apiLoyaltyIntegrationAuthentication)the JSON objects that you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-loyalty.csv).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Case number</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Category</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Test case</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Steps</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Expected results</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">1</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Card swipe</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Swipe a card associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">2</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Card swipe</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Swipe a card NOT associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Invalid Account error message should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">3</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Card swipe</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Swipe a card that is NOT a loyalty account card.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Card swiped is not a rewards card error message should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">4</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Keying in number</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Key in a card number associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Scanning QR code</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer &gt; Scan.</p> <p className="text-base leading-relaxed">Scan a QR code associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">6</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Scanning QR code</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer &gt; Scan.</p> <p className="text-base leading-relaxed">Scan a QR code NOT associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Invalid Account error message should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">7</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">By email</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer &gt; Lookup.</p> <p className="text-base leading-relaxed">Key in an email address associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">8</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">By phone number</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer &gt; Lookup.</p> <p className="text-base leading-relaxed">Key in a phone number associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">9</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Lookup</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">By name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer &gt; Lookup.</p> <p className="text-base leading-relaxed">Key in a name associated with a loyalty account at that restaurant.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected loyalty account should appear.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">10</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unavailable rewards</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected rewards value should display, but because the awards are unavailable for redemption, you should not be able to apply them to a check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">11</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Available rewards</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected rewards should be available redemption.</p> <p className="text-base leading-relaxed">A Redeem button should be present.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">12</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Rewards points</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected rewards value should display on the dialog.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">13</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Account Inquiry</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalidated rewards</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Remove the items from your check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward should be removed from the check.</p> <p className="text-base leading-relaxed">The error message Changes to the check have voided applied rewards. Discounts that are no longer applicable have been removed should display.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">14</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Tap Redeem to add a reward to the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward should apply to the target item on the check.</p> <p className="text-base leading-relaxed">The amount discounted should be correct.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">15</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tap Pay.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward discount should be correctly carried to the payment screen.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">16</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">17</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Check-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Tap Redeem to add a reward to the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward should apply to the check.</p> <p className="text-base leading-relaxed">The amount discounted should be correct.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">18</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Check-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tap Pay.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward discount should be correctly carried to the payment screen.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">19</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Check-level discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">20</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy one get one discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected reward should display, but should be unavailable for redemption.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">21</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy one get one discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The expected rewards should be available redemption.</p> <p className="text-base leading-relaxed">A Redeem button should be present.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">22</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy one get one discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tap Redeem to add a reward to the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward should apply to the target item on the check.</p> <p className="text-base leading-relaxed">The amount discounted should be correct.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">23</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy one get one discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tap Pay.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The reward discount should be correctly carried to the payment screen.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">24</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy one get one discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">25</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Without reward applied to check</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items to the check.</p> <p className="text-base leading-relaxed">Tap Pay($).</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p> <p className="text-base leading-relaxed">You should see the expected accrual message.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">26</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual reverse</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Closed Checks tab, find the order placed in case 25.</p> <p className="text-base leading-relaxed">Tap Pay($).</p> <p className="text-base leading-relaxed">Void all payments.</p> <p className="text-base leading-relaxed">In the overflow menu, clock Void Order.</p> <p className="text-base leading-relaxed">Confirm the void operation.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should be successfully voided in Toast.</p> <p className="text-base leading-relaxed">You should see the expected reversal message.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">27</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">With reward applied to check</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Tap Redeem to add a reward to the check.</p> <p className="text-base leading-relaxed">Tap Pay.</p> <p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p> <p className="text-base leading-relaxed">You should see the expected accrual and redeem messages.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">28</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Redemption reverse</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Closed Checks tab, find the order placed in case 27.</p> <p className="text-base leading-relaxed">Tap Pay($).</p> <p className="text-base leading-relaxed">Void all payments.</p> <p className="text-base leading-relaxed">In the overflow menu, click Void Order.</p> <p className="text-base leading-relaxed">Confirm the void operation.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should be successfully voided in Toast,.</p> <p className="text-base leading-relaxed">You should see the expected reversal messages.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">29</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">With multiple rewards applied to check</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">From the Toast POS app &gt; New Order.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Look up a loyalty account that has associated rewards.</p> <p className="text-base leading-relaxed">Add items that would trigger rewards to the check.</p> <p className="text-base leading-relaxed">Tap Rewards &gt; Look Up Customer.</p> <p className="text-base leading-relaxed">Tap Redeem to add a reward to the check.</p> <p className="text-base leading-relaxed">Repeat at least once in order to apply multiple rewards to the check.</p> <p className="text-base leading-relaxed">Tap Pay.</p> <p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The payment should process successfully.</p> <p className="text-base leading-relaxed">You should see the expected accrual and redeem messages.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">30</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Accrual and Reversal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Partial redemption reverse</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Closed Checks tab, find the order placed in case 29.</p> <p className="text-base leading-relaxed">Tap Update.</p> <p className="text-base leading-relaxed">Select a reward that was redeemed, and void it from the check.</p> <p className="text-base leading-relaxed">Tap Pay.</p> <p className="text-base leading-relaxed">Complete payment on the check.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The check should successfully close.</p> <p className="text-base leading-relaxed">You should see the expected reversal messages.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

