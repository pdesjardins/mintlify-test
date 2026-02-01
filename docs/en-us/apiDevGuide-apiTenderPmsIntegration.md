---
title: "Hotel property management system integration"
id: apiTenderPmsIntegration
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingATenderProviderIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Tender provider integrations"
previousSectionFile: apiDevGuide-apiTenderProviderIntegrationsOverview.md
previousSectionTitle: "Tender provider integrations overview"
nextSectionFile: apiDevGuide-apiTenderScanToPay.md
nextSectionTitle: "Scan-to-pay"
externalReferences: [https://doc.toasttab.com/tenderapidraftdoc/apiTenderApiReference.html#/definitions/Check]
excerpt: "Property management systems (PMS) are used by hotels and motels to coordinate systems used for servicing guests, charges, and further accounting. You can use the tender API to implement an..."
keywords: ["hotel", "property", "management", "system", "integration"]
procedures: 0
codeExamples: 0
---

### Hotel property management system integration

Property management systems (PMS) are used by hotels and motels to coordinate systems used for servicing guests, charges, and further accounting. You can use the tender API to implement an integration between a PMS and the Toast platform. The tender integration allows an employee at a hotel or restaurant to look up a guest's account and post charges to their hotel folio.

#### Transaction descriptions

The tender API supports the following transaction types for the PMS integration workflow:

- `[TENDER_SEARCH_CONFIG](apiTenderPmsIntegration.html#apiTenderConfigureSearchPMS)`: Request configured search terms for the restaurant. Search terms can be First Name, Last Name, Room Number, Email, or Company.


- [`TENDER_SEARCH`](apiTenderPmsIntegration.html#apiTenderSearchPMS): Search for an account.


- `[TENDER_RETRIEVE_DISCOUNTS](apiTenderPmsIntegration.html#apiRetrieveDiscountsPMS)`: Retrieve applicable discounts for a check.


- `[TENDER_RETRIEVE_PAYMENTS](apiTenderPmsIntegration.html#apiTenderRetrievePaymentsPMS)`: Retrieve payment for a check.


- `[TENDER_REDEEM](apiTenderPmsIntegration.html#apiTenderRedeemDiscountsPaymentsPMS)`: Confirm payment and discounts applied to a check.


- `[TENDER_GRATUITY](apiTenderPmsIntegration.html#apiTenderGratuityPMS)`: Add a tip to a previously confirmed payment.


- `[TENDER_REVERSE](apiTenderPmsIntegration.html#apiTenderReversePaymentsAndDiscountsPMS)`: Reverse a previous discount redemption or gratuity.



##### Configure search

Configuring the search is the first transaction that occurs when an employee initiates the workflow to charge a check to a guest's account.

**Procedure 10.10. Configure search workflow**

1. A guest wants to charge a check to a hotel room.


2. An employee selects Pay ($) to tender the check and selects hotel room charge as the payment method on the Toast POS device.


3. The Toast platform sends a `TENDER_SEARCH_CONFIG` request to the hotel PMS provider to get the search terms used by the provider to look up guest information.


4. The PMS provider sends a response in a `searchConfigResponse` object. Each key-value pair in this object defines an input field (`key`) with its type (`value`). Optional attributes for maximum length (`maxLength`) and tender property type (`tenderProperType`) for the key-value pair may be included.

The `value` must be one of the following:

| Value | Description | 
| --- | --- |
| `NUMBER` | A numeric value such as room number, or reservation number. | 
| `TEXT` | An alphanumeric value such as a guest's name or their company's name. | 
| `EMAIL` | The guest's email address. | 
| `PHONE_NUMBER` | A numeric-only value for the guest's phone number.  | 

The first four search terms are displayed on the guest lookup screen on the Toast POS device. The `value` also determines the type of virtual keyboard that is displayed for the search term. For example, `TEXT` does not allow a number pad to be used.



The following example shows the search terms configured as room number, name, reservation number, and company name.

**Example 10.18. Configure search request**

The `TENDER_SEARCH_CONFIG` transaction is a `POST` request to your tender API endpoint `https://<em>\{your endpoint\}</em>` with the following header parameters:

- `Toast-Transaction-Type`


- `Toast-Restaurant-External-ID`


- `Toast-Transaction-GUID`


- `Authorization`



This request has no message body.

  
**Example 10.19. Successful configure search response**

The following is an example of a successful configure search response.

```
\{
  "transactionStatus": "ACCEPT",
  "discountsResponse": null,
  "paymentsResponse": null,
  "gratuityResponse": null,
  "searchConfigResponse": \{
    "searchTermNames": [
      \{
        "key": "Room Number",
        "value": "TEXT", 
        "tenderPropertyType": "ROOM_ID", 
        "maxLength": 3
      },
      \{
        "key": "Name",
        "value": "TEXT",
        "tenderPropertyType": "OTHER",
        "maxLength": 30
      },
      \{
        "key": "Reservation Number",
        "value": "NUMBER",
        "tenderPropertyType": "OTHER",
        "maxLength": 10
      },
      \{
        "key": "Company Name",
        "value": "TEXT",
        "tenderPropertyType": "OTHER",
        "maxLength": 30
      \}
    ]
  \},
  "searchResponse": null,
  "redeemResponse": null
\}
```



(1) The value attribute must be TEXTif your integration supports alpha-numeric room numbers.

(2) The tenderProperType attribute must be associated with ROOM_ID for the key-value pair that defines Room Number in the configure search response and on each search response.

  
##### Guest search

After the search configuration request, the Toast POS device displays the guest search criteria. An employee can search for a guest on the Toast POS device using a guest's information, such as name, room number, or reservation number.

**Procedure 10.11. Guest search workflow**

1. An employee enters the guest's identifying information in the input fields on the Toast POS device and searches for the guest.


2. The Toast POS device sends a `TENDER_SEARCH`request to the PMS provider. The request is a `TenderTransaction` object that contains a `searchTransactionInformation` object which contains a `searchTerms` object. This `searchTerms`object contains the search criteria, in the form of a key-value pair:

- The `key` corresponds to the input field where the restaurant employee enters the guest's identifying information.


- The `value` corresponds to the string that the employee types on the Toast POS device. The `value` can be partial. For example, only first or last name, or partial name.




3. The PMS provider returns the results of the search request in a `searchResponse` object that contains a `searchResults` property. The `searchResults` property contains an array of `AccountInfo` objects. Each entry in the array corresponds to a guest and includes:

- An identifier for the guest (`tenderIdentifier`). Each `tenderIdentifier` should be unique for each guest returned in the `TENDER_SEARCH
                response`.



> **Important**
> 
> `tenderIdentifier` is generated by the integration partner and should never be generated using a guest's sensitive information, such as credit card details.



- The search results returned as key-value pairs with the guest information such as name and room number.



Guest search results are displayed on the Toast POS device.



The following example shows a search for a guest whose name contains `john`. The PMS provider responds with two results for `john adams` and `amy johns` and their information.

**Example 10.20. Search request message body**

```
\{
  "discountsTransactionInformation": null,
  "paymentsTransactionInformation": null,
  "redeemTransactionInformation": null,
  "gratuityTransactionInformation": null,
  "reverseTransactionInformation": null,
  "searchTransactionInformation": \{
    "swipeData": null,
    "scanData": null,
    "searchTerms": [
      \{
        "key": "Name",
        "value": "john",
        "tenderPropertyType": "OTHER",
        "maxLength": 30
      \}
    ],
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6",
    "checkGuid": "ad51d5f8-8573-4a4f-ad65-ce308f5ff763"
  \}
\}
```

  
**Example 10.21. Successful search response**

```
\{
  "transactionStatus": "ACCEPT",
  "discountsResponse": null,
  "paymentsResponse": null,
  "gratuityResponse": null,
  "searchConfigResponse": null,
  "searchResponse": \{
    "searchResults": [
      \{
        "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
        "properties": [
          \{
            "key": "Room Number",
            "value": "100",
            "tenderPropertyType": "ROOM_ID",
            "maxLength": null
          },
          \{
            "key": "Name",
            "value": "John Adams",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Reservation Number",
            "value": "54321",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Company Name",
            "value": "Toast, Inc.",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Guest Status",
            "value": "ACTIVE",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Charge Limit",
            "value": "$500.00",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          }
        ],
        "additionalProperties": [
          \{
            "key": "storedValue",
            "value": "403.25"
          }
        ]
      },
      \{
        "tenderIdentifier": "d453f4ea-627f-4f75-9674-eba26c7c621d",
        "properties": 
          \{
            "key": "Room Number",
            "value": "308",
            "tenderPropertyType": "ROOM_ID",
            "maxLength": null
          },
          \{
            "key": "Name",
            "value": "Amy Johns",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Reservation Number",
            "value": "12345",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Company Name",
            "value": "Toast, Inc.",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Guest Status",
            "value": "ACTIVE",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          },
          \{
            "key": "Charge Limit",
            "value": "$1000.00",
            "tenderPropertyType": "OTHER",
            "maxLength": null
          }
        ],
        "additionalProperties": [
          \{
            "key": "storedValue",
            "value": "980.73"
          \}
        ]
      \}
    ]
  \},
  "redeemResponse": null
\}
```

  
##### Retrieve discounts

After an employee selects a guest from the search results on the Toast POS device, the Toast platform retrieves discounts from the PMS provider.

**Procedure 10.12. Retrieve discounts workflow**

1. The Toast platform sends a `TENDER_RETRIEVE_DISCOUNTS` request to the PMS provider. The request includes a `TenderTransaction`object that holds the guest identifier (`tenderIdentifier`) and check (`Check`) in a `discountsTransactionInformation` object.


2. Your PMS integration determines the discounts to be applied to the check and responds to the Toast platform with a `discountsResponse` value in the `TenderTransactionResponse` object. Discount information is contained in this object. Note that the number of discounts can be zero.


3. The Toast platform applies the discounts and adds or updates the `appliedDiscounts` value of the `[Check](https://doc.toasttab.com/tenderapidraftdoc/apiTenderApiReference.html#/definitions/Check)`object.



> **Note**
> 
> As a provider, you might not support discounts for your restaurant. In this case, you can return an empty array in your response to the `TENDER_RETRIEVE_DISCOUNTS`request.




**Example 10.22. Retrieve discounts request body**

```
\{
  "discountsTransactionInformation": \{
    "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
    "accountInfo": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": []
    },
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6",
    "check": \{
      "guid": "ad51d5f8-8573-4a4f-ad65-ce308f5ff763",
      "entityType": null,
      "externalId": null,
      "displayNumber": "2",
      "payments": [],
      "appliedDiscounts": [],
      "shift": null,
      "lastModifiedDevice": null,
      "voidDate": null,
      "duration": null,
      "appliedPreauthInfo": null,
      "paidDate": null,
      "appliedLoyaltyInfo": null,
      "voided": null,
      "paymentStatus": null,
      "amount": 13.78,
      "tabName": null,
      "taxExempt": null,
      "netAmount": null,
      "tipAmount": null,
      "totalDiscountAmount": null,
      "removedSelections": [],
      "pickedUpDate": null,
      "taxExemptionAccount": null,
      "openedDate": null,
      "totalAmount": null,
      "selections": [
        \{
          "guid": "77cc9961-a859-4ae0-a545-3c7d36f796f4",
          "entityType": null,
          "externalId": null,
          "deferred": null,
          "preDiscountPrice": 13,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Fried Chicken Sliders",
          "appliedDiscounts": [],
          "externalPriceAmount": null,
          "modifiers": [],
          "seatNumber": null,
          "voidDate": null,
          "fulfillmentStatus": null,
          "optionGroupPricingMode": null,
          "giftCardSelectionInfo": null,
          "salesCategory": null,
          "selectionType": null,
          "price": 13,
          "voided": false,
          "appliedTaxes": [
            \{
              "guid": "ec0ba24e-afd8-45cc-b39b-311b4bddcc63",
              "entityType": null,
              "taxRate": \{
                "guid": "df6eeefc-3f1f-4669-a9ef-3718a53b8418",
                "entityType": "TaxRate"
              },
              "rate": 0.06,
              "name": "Test Tax Rate",
              "taxAmount": 0.78,
              "type": "PERCENT",
              "facilitatorCollectAndRemitTax": null
            }
          ],
          "storedValueTransactionId": null,
          "itemGroup": \{
            "guid": "0598f4e5-223a-4b91-a674-9929d42e532d",
            "entityType": "MenuGroup",
            "externalId": "200000017820067195",
            "multiLocationId": null
          },
          "item": \{
            "guid": "791f5203-22b6-469a-a0f9-29e1177219ac",
            "entityType": "MenuItem",
            "externalId": "200000017820067789",
            "multiLocationId": null
          \},
          "taxInclusion": "NOT_INCLUDED",
          "quantity": 1,
          "receiptLinePrice": 13,
          "unitOfMeasure": null,
          "refundDetails": null,
          "toastGiftCard": null,
          "tax": 0.78,
          "diningOption": null,
          "openPriceAmount": null,
          "voidBusinessDate": null,
          "createdDate": null,
          "preModifier": null,
          "modifiedDate": null
        \}
      ],
      "voidBusinessDate": null,
      "createdDate": null,
      "deleted": null,
      "createdDevice": null,
      "closedDate": null,
      "deletedDate": null,
      "billingCustomer": null,
      "guestProfile": null,
      "modifiedDate": null,
      "taxAmount": null,
      "driverShift": null,
      "appliedServiceCharges": [],
      "customer": null
    \},
    "totalDiscountable": 13
  \},
  "paymentsTransactionInformation": null,
  "redeemTransactionInformation": null,
  "gratuityTransactionInformation": null,
  "reverseTransactionInformation": null,
  "searchTransactionInformation": null
\}
```

  
**Example 10.23. Successful retrieve discounts response**

```
\{
  "transactionStatus": "ACCEPT",
  "discountsResponse": \{
    "account": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": null
    },
    "tenderDiscounts": [
      \{
        "name": "Tender Dollar Discount",
        "identifier": "5570ca31-7391-4b0c-bd45-9788cc686a5b",
        "amount": 1,
        "selectionGuid": null,
        "appliedDiscountGuid": "54397374-cc57-4145-9f0b-784f02d3ea5c"
      \}
    ]
  \},
  "paymentsResponse": null,
  "gratuityResponse": null,
  "searchConfigResponse": null,
  "searchResponse": null,
  "redeemResponse": null
\}
```

The retrieved discounts `tenderDiscounts` can be check-level or item-level discounts.

  
##### Retrieve payments

The Toast platform retrieves payments after applying the discounts received from the PMS provider.

**Procedure 10.13. Retrieve payments workflow**

1. The Toast platform sends a `TENDER_RETRIEVE_PAYMENTS` request to the PMS provider. The request includes a `TenderTransaction` object that holds the guest identifier (`tenderIdentifier`) and the updated `[Check](https://doc.toasttab.com/tenderapidraftdoc/apiTenderApiReference.html#/definitions/Check)`object in a `paymentsTransactionInformation`object.



> **Note**
> 
> When discounting item groups, item quantities cannot be greater than `1` in your discount response. Break up item groups into separate selections where item `quantity =
              1` and specify the discount for each separate selection.



2. Your tender integration determines the payment and responds to the Toast platform with a `paymentsResponse` value in the `TenderTransactionResponse` object, which includes the payment information.


3. The Toast platform applies the payment and updates the `Check` object.



**Example 10.24. Retrieve payments request body**

```
\{
  "discountsTransactionInformation": null,
  "paymentsTransactionInformation": \{
    "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
    "accountInfo": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [],
      "expansionSearchCriteria": []
    },
    "amount": 12.72,
    "tipAmount": 0,
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6",
    "check": \{
      "guid": "ad51d5f8-8573-4a4f-ad65-ce308f5ff763",
      "entityType": null,
      "externalId": null,
      "displayNumber": "2",
      "payments": [],
      "appliedDiscounts": [
        \{
          "guid": "54397374-cc57-4145-9f0b-784f02d3ea5c",
          "entityType": null,
          "externalId": null,
          "approver": null,
          "loyaltyDetails": null,
          "discountPercent": null,
          "appliedDiscountReason": null,
          "comboItems": [],
          "discountAmount": 1,
          "discount": null,
          "triggers": [],
          "appliedPromoCode": null,
          "processingState": "PENDING_APPLIED",
          "name": null,
          "nonTaxDiscountAmount": null,
          "discountType": null
        }
      ],
      "shift": null,
      "lastModifiedDevice": null,
      "voidDate": null,
      "duration": null,
      "appliedPreauthInfo": null,
      "paidDate": null,
      "appliedLoyaltyInfo": null,
      "voided": null,
      "paymentStatus": null,
      "amount": 12.72,
      "tabName": null,
      "taxExempt": null,
      "netAmount": null,
      "tipAmount": null,
      "totalDiscountAmount": null,
      "removedSelections": [],
      "pickedUpDate": null,
      "taxExemptionAccount": null,
      "openedDate": null,
      "totalAmount": null,
      "selections": [
        \{
          "guid": "77cc9961-a859-4ae0-a545-3c7d36f796f4",
          "entityType": null,
          "externalId": null,
          "deferred": null,
          "preDiscountPrice": 13,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Fried Chicken Sliders",
          "appliedDiscounts": [],
          "externalPriceAmount": null,
          "modifiers": [],
          "seatNumber": null,
          "voidDate": null,
          "fulfillmentStatus": null,
          "optionGroupPricingMode": null,
          "giftCardSelectionInfo": null,
          "salesCategory": \{
            "guid": "d7933a7d-5db7-447b-83c4-99fab2b536ab",
            "entityType": "SalesCategory",
            "externalId": "200000022647976825",
            "multiLocationId": null
          },
          "selectionType": null,
          "price": 13,
          "voided": false,
          "appliedTaxes": [
            \{
              "guid": "ec0ba24e-afd8-45cc-b39b-311b4bddcc63",
              "entityType": null,
              "taxRate": \{
                "guid": "df6eeefc-3f1f-4669-a9ef-3718a53b8418",
                "entityType": "TaxRate"
              },
              "rate": 0.06,
              "name": "Test Tax Rate",
              "taxAmount": 0.78,
              "type": "PERCENT",
              "facilitatorCollectAndRemitTax": null
            }
          ],
          "storedValueTransactionId": null,
          "itemGroup": \{
            "guid": "0598f4e5-223a-4b91-a674-9929d42e532d",
            "entityType": "MenuGroup",
            "externalId": "200000017820067195",
            "multiLocationId": null
          },
          "item": \{
            "guid": "791f5203-22b6-469a-a0f9-29e1177219ac",
            "entityType": "MenuItem",
            "externalId": "200000017820067789",
            "multiLocationId": null
          },
          "taxInclusion": "NOT_INCLUDED",
          "quantity": 1,
          "receiptLinePrice": 13,
          "unitOfMeasure": null,
          "refundDetails": null,
          "toastGiftCard": null,
          "tax": 0.78,
          "diningOption": null,
          "openPriceAmount": null,
          "voidBusinessDate": null,
          "createdDate": null,
          "preModifier": null,
          "modifiedDate": null
        }
      ],
      "voidBusinessDate": null,
      "createdDate": null,
      "deleted": null,
      "createdDevice": null,
      "closedDate": null,
      "deletedDate": null,
      "billingCustomer": null,
      "guestProfile": null,
      "modifiedDate": null,
      "taxAmount": null,
      "driverShift": null,
      "appliedServiceCharges": [],
      "customer": null
    },
    "tenderDiscountsApplied": [
      \{
        "name": "Tender Dollar Discount",
        "identifier": "5570ca31-7391-4b0c-bd45-9788cc686a5b",
        "amount": 1,
        "selectionGuid": null,
        "appliedDiscountGuid": "54397374-cc57-4145-9f0b-784f02d3ea5c"
      \}
    ]
  \},
  "redeemTransactionInformation": null,
  "gratuityTransactionInformation": null,
  "reverseTransactionInformation": null,
  "searchTransactionInformation": null
\}
```

  
**Example 10.25. Successful retrieve payments response**

```
\{
  "transactionStatus": "ACCEPT",
  "discountsResponse": null,
  "paymentsResponse": \{
    "account": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": null
    },
    "tenderPayments": [
      \{
        "name": "Tender Payment",
        "identifier": "c359cde2-a758-46f3-a6d1-7f00e9b18f86",
        "type": "STORED_VALUE",
        "amount": 12.72,
        "tipAmount": 0,
        "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d"
      \}
    ]
  \},
  "gratuityResponse": null,
  "searchConfigResponse": null,
  "searchResponse": null,
  "redeemResponse": null
\}
```

  
##### Redeem discounts and payments

After the Toast platform applies payments to the check, the discounts and payments are redeemed. For more information about gratuity payments, see [Gratuity](apiTenderPmsIntegration.html#apiTenderGratuityPMS).

**Procedure 10.14. Redeem discounts and payments workflow**

1. The Toast platform sends a `TENDER_REDEEM`request to the PMS provider.


2. The PMS provider marks the discounts as used and adds the payment to the guest's account.


3. The restaurant employee closes the check if the full amount is covered by the room charge.



**Example 10.26. Redeem discounts and payments request body**

```
\{
  "discountsTransactionInformation": null,
  "paymentsTransactionInformation": null,
  "redeemTransactionInformation": \{
    "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
    "accountInfo": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": []
    },
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6",
    "check": [contents omitted],
    "tenderPaymentsApplied": [
      \{
        "name": "Tender Payment",
        "identifier": "c359cde2-a758-46f3-a6d1-7f00e9b18f86",
        "type": "STORED_VALUE",
        "amount": 12.72,
        "tipAmount": 0,
        "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d"
      }
    ],
    "tenderDiscountsApplied": [
      \{
        "name": "Tender Dollar Discount",
        "identifier": "5570ca31-7391-4b0c-bd45-9788cc686a5b",
        "amount": 1,
        "selectionGuid": null,
        "appliedDiscountGuid": "54397374-cc57-4145-9f0b-784f02d3ea5c"
      }
    ],
    "revenueCenter": \{
      "guid": "cc2f37ef-a05e-43ca-afb8-5dc1175d90d7",
      "name": "Dining Room"
    \}
  \},
  "gratuityTransactionInformation": null,
  "reverseTransactionInformation": null,
  "searchTransactionInformation": null
\}
```

  
**Example 10.27. Successful redeem discounts and payments response**

```
\{
  "transactionStatus": "ACCEPT"
\}
```

  
##### Gratuity

If configured, the Toast platform prompts the restaurant employee for a gratuity after the Toast platform receives a response from the PMS provider about the discounts and payments redemption.



> **Note**
> 
> Gratuity functionality is configurable through Toast Web. Toast support recommends that integration developers use the gratuity transaction to consume all tips related to tender payments. Partners that do so should ignore non-zero values in the tipAmount field contained within the redeem transaction.


**Procedure 10.15. Gratuity workflow**

1. After an employee enters a gratuity amount, the Toast POS system sends a `TENDER_GRATUITY` request that specifies a gratuity amount to add to a `TENDER_REDEEM`transaction. The `Toast-Transaction-GUID` of `TENDER_REDEEM` to add the gratuity amount is provided in the `transactionToUpdate` value in the body of the `TENDER_GRATUITY` request.


2. The PMS provider responds to the Toast platform with a `gratuityResponse` value in the `TransactionResponseGratuity` object, which contains the value of gratuity that the guest added.



**Example 10.28. Gratuity request body**

```
\{
  "discountsTransactionInformation": null,
  "paymentsTransactionInformation": null,
  "redeemTransactionInformation": null,
  "gratuityTransactionInformation": \{
    "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
    "accountInfo": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": []
    \},
    "transactionToUpdate": "868cd4a6-66de-4f33-ad47-6867e67ba2e8",
    "additionalGratuity": 2.86, 
    "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d",
    "tenderPayments": [
      \{
        "name": "Tender Payment",
        "identifier": "c359cde2-a758-46f3-a6d1-7f00e9b18f86",
        "type": "STORED_VALUE",
        "amount": 12.72,
        "tipAmount": 0,
        "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d"
      }
    ],
    "checkInfo": \{
      "guid": "ad51d5f8-8573-4a4f-ad65-ce308f5ff763",
      "displayNumber": "2"
    \},
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6", 
    "check": [contents omitted] 
  \},
  "reverseTransactionInformation": null,
  "searchTransactionInformation": null
\}
```



(1) Gratuity added to the check during the gratuity transaction.

(2) The unique order identifier.

(3) A Check object that contains the order's complete transaction details.

  
**Example 10.29. Successful gratuity response body**

```
\{
  "transactionStatus": "ACCEPT",
  "discountsResponse": null,
  "paymentsResponse": null,
  "gratuityResponse": \{
    "account": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": null
    },
    "tenderPayments": [
      \{
        "name": "Tender Payment",
        "identifier": "c359cde2-a758-46f3-a6d1-7f00e9b18f86",
        "type": "STORED_VALUE",
        "amount": 12.72,
        "tipAmount": 2.86,
        "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d"
      \}
    ]
  \},
  "searchConfigResponse": null,
  "searchResponse": null,
  "redeemResponse": null
\}
```

  
##### Reverse payments and discounts

A transaction is reversed in the following situations:

- If the restaurant employee voids the payment, the Toast POS system sends a `TENDER_REVERSE` request to the PMS provider to reverse the payment and any applied discounts.


- If the restaurant employee voids the order, then the Toast POS system sends a `TENDER_REVERSE` request to the PMS provider.


- If a discount times out during redemption, then the Toast POS system sends a `TENDER_REVERSE` request to the PMS provider.



Reverse requests can be one or more of the following:

- Payments


- Discounts



In the request body, the value of `transactionToUpdate` is the `Toast-Transaction-GUID` of the `TENDER_REDEEM`request. The `discountsToRemove` and `paymentsToRemove` contain the discounts and payment identifiers, respectively. The `orderGuid` is the order's unique Toast identifier.

**Example 10.30. Reverse request body**

```
\{
  "discountsTransactionInformation": null,
  "paymentsTransactionInformation": null,
  "redeemTransactionInformation": null,
  "gratuityTransactionInformation": null,
  "reverseTransactionInformation": \{
    "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
    "accountInfo": \{
      "tenderIdentifier": "2670f8d0-c9c1-4dd1-b234-6922a81a7792",
      "properties": [contents omitted],
      "additionalProperties": [contents omitted],
      "expansionSearchCriteria": []
    },
    "transactionToUpdate": "868cd4a6-66de-4f33-ad47-6867e67ba2e8",
    "discountsToRemove": [
      "5570ca31-7391-4b0c-bd45-9788cc686a5b"
    ],
    "paymentsToRemove": [
      "c359cde2-a758-46f3-a6d1-7f00e9b18f86"
    ],
    "tenderPaymentsToRemove": [
      \{
        "name": "Tender Payment",
        "identifier": "c359cde2-a758-46f3-a6d1-7f00e9b18f86",
        "type": "STORED_VALUE",
        "amount": 12.72,
        "tipAmount": 2.86,
        "paymentGuid": "6980a7b8-edb4-469e-bcb6-869b1cad082d"
      }
    ],
    "tenderDiscountsToRemove": [
      \{
        "name": "Tender Dollar Discount",
        "identifier": "5570ca31-7391-4b0c-bd45-9788cc686a5b",
        "amount": 1,
        "selectionGuid": null,
        "appliedDiscountGuid": "54397374-cc57-4145-9f0b-784f02d3ea5c"
      }
    ],
    "checkInfo": \{
      "guid": "ad51d5f8-8573-4a4f-ad65-ce308f5ff763",
      "displayNumber": "2"
    \},
    "originalTransactionStatus": "ACCEPT",
    "orderGuid": "b34bf7f6-7836-4dbb-963d-d7c8115838f6"
  \},
  "searchTransactionInformation": null
\}
```

  
**Example 10.31. Successful reverse response body**

```
\{
  "transactionStatus": "ACCEPT"
\}
```

  
#### POS workflow

This section describes the user interface workflow in the Toast platform for billing a hotel restaurant guest using the hotel's PMS provider.

At the payment phase of the Toast platform order workflow:

1. A guest chooses to pay a balance due by applying the balance to their room charge.


2. An employee selects the Pay ($) button to navigate to the Payments screen.

![A screenshot of the Pay button you use to access the Payments screen.](https://doc.toasttab.com/doc/media/tender_pos1.png)


3. The restaurant employee selects the Otherbutton.

![A screenshot of the Other button on the Payments screen.](https://doc.toasttab.com/doc/media/tender_pos2.png)


4. The Select Alternate Payment Typedialog appears and Hotel Room Charge is listed as an option.



> **Note**
> 
> The name of the payment option is configurable from the Toast Web at Payments \> Other Payment Options.


![A screenshot of the Select Alternate Payment Type screen, showing the room charge option.](https://doc.toasttab.com/doc/media/tender_pos_pms1.png)


5. After selecting room charge, a Lookup Hotel Guest dialog appears.

![A screenshot of the Lookup Hotel Guest screen.](https://doc.toasttab.com/doc/media/tender_pos_pms2.png)


6. The restaurant employee enters information to look up a guest and selects Search. For example, they enter a room number in the Enter Room # field.


7. Once the search is complete, a list of search results appears on the Toast POS device.

![A screenshot of the Lookup Hotel Guest screen after a room number search.](https://doc.toasttab.com/doc/media/tender_pos_pms4.png)


8. The restaurant employee selects the record corresponding to the guest that owes the check amount and processes the payment with the PMS provider. If digital receipts are configured, the Toast POS device prompts the restaurant employee to add the tip amount.

If the restaurant employee chose to print a receipt, the Room Charge payment and any applied discounts are printed on the receipt.



#### Reporting

You can view information about tender transactions in the Sales Summary report. This report can be accessed by navigating to Reports \> Sales \> Sales Summary in Toast Web. Room charge tender payments appear in the Other section of the Sales Summary report, as shown below, and in the Payments tab. The payment Typeis shown as Other from the Payments tab.

![A screenshot of the Sales Summary report, showing hotel room charge transactions in the Other section.](https://doc.toasttab.com/doc/media/tender_reporting1_pms.png)

