---
title: "Card declined message reference"
id: adminCreditCardDeclinedMessageReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
parentSectionTitle: "Credit card payments"
previousSectionFile: adminGuide-adminCreditCardPayments.md
previousSectionTitle: "Credit card payments"
nextSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
nextSectionTitle: "Service charges"
excerpt: "When a card payment cannot be processed, the Toast POS device shows a..."
procedures: 0
codeExamples: 0
---

When a card payment cannot be processed, the Toast POS device shows a message from the card network. These response messages can be difficult to interpret. The following table shows the response messages received most frequently on Toast POS devices with descriptions for why that message might appear.



> **Note**
> 
> The messages and the descriptions shown in the following tables are produced by the card processor, not by Toast. The information provided in these tables is intended for reference only, and is subject to change without notice by the card network.



<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Response Message</div></th>
      <th className=""><div className="">Descriptions</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">*REQUEST DENIED*</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Do not honor</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">AUTH DECLINED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Do not honor</p> <p className="text-base leading-relaxed">Transaction not permitted to issuer/cardholder</p> <p className="text-base leading-relaxed">Exceeds withdrawal limit</p> <p className="text-base leading-relaxed">Domain Restriction Controls Fail</p> <p className="text-base leading-relaxed">Declined-transaction in violation of law</p> <p className="text-base leading-relaxed">Declined PIN attempts</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">AUTH TRN NO AL'W</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Auth transaction not allowed for this payment</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">CALL OPER</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Refer to card issuer</p> <p className="text-base leading-relaxed">Refer to call center</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">CALL VOICE OPER</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Refer to card issuer</p> <p className="text-base leading-relaxed">Re-enter transaction</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">CARD EXPIRED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Expiration date check failed</p> <p className="text-base leading-relaxed">Expired card</p> <p className="text-base leading-relaxed">Card expiry date less than current date</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">CARDHLDR DECLINE</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Declined per cardholder request</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">CVD ERROR</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Do not honor</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">DECLINED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Declined by user</p> <p className="text-base leading-relaxed">Invalid effective date on card</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">ERR PROC FIELD</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Format error, invalid value in message</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">HOLD - CALL</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Pick up</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INV CARD NUMBER</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid cardholder account</p> <p className="text-base leading-relaxed">Account number not found in BIN table</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID AMOUNT</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid amount</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID CARD</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid card number</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID CARD NO</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid card number</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID EXP DATE</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid expiry date</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID FUNCTION </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Transaction not permitted to terminal </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID MERC NO </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid merchant or terminal </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">INVALID PIN </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Invalid pin </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">LOST/STOLEN CARD</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Lost or stolen card</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">NO CHECKING ACCT</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Error</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">PICK UP CARD </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Pick up card </p> <p className="text-base leading-relaxed">Decline - pick up card</p> <p className="text-base leading-relaxed">Pick up card - No Fraud</p> <p className="text-base leading-relaxed">Pick up card (Special Condition)</p> <p className="text-base leading-relaxed">Pick up card (Special Condition)(Fraud Account)</p> <p className="text-base leading-relaxed">Lost card - pick up</p> <p className="text-base leading-relaxed">Stolen card - pick up</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">PIN TRIES EXCEED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Re-enter transaction</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">PROC ERROR 13</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">System error</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">SECURITY VIOLATION</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Security violation</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">TRAN NOT ALLOWED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Transaction not permitted to terminal</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">TRANS DENIED</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Do not honor</p> <p className="text-base leading-relaxed">Invalid cardholder account</p> <p className="text-base leading-relaxed">Unable to locate record</p> <p className="text-base leading-relaxed">Insufficient funds</p> <p className="text-base leading-relaxed">Restricted card</p> <p className="text-base leading-relaxed">Security violation</p> <p className="text-base leading-relaxed">Account activity limit exceeded</p> <p className="text-base leading-relaxed">Allowable number of PIN entry tries exceeded</p> <p className="text-base leading-relaxed">One or more errors in message</p> <p className="text-base leading-relaxed">File is unavailable</p> <p className="text-base leading-relaxed">No credit account</p> <p className="text-base leading-relaxed">Fraudulent activity detected</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">TRANS NOT ALLOW</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Transactions not allowed to cardholder</p> <p className="text-base leading-relaxed">Transactions not allowed to terminal</p> <p className="text-base leading-relaxed">Illegal transaction - violation of law</p> <p className="text-base leading-relaxed">Capture transactions not allowed for this payment type</p> <p className="text-base leading-relaxed">Capture transaction on authorization only terminal</p> <p className="text-base leading-relaxed">Private label transaction not allowed for terminal</p> <p className="text-base leading-relaxed">Store reporting transactions not allowed</p></div></td>
    </tr>
  </tbody>
</table>
</div>

