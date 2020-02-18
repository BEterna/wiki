# How To: Post advance invoices

This topic provides specific information regarding sales and purchases prepayment invoices in D365O, required to comply with the local legislation for countries in the Adriatic region.

-----

Local tax authorities require VAT eligible companies that receive/give prepayments and will not deliver/receive products or services within the same tax period to report VAT from the received/given prepayment transactions in the same period as the prepayment has been given/received. In order to comply with local legislation, the purpose of this functionality is to enable posting the VAT from the received/given prepayments as soon as payments are posted.

This localized functionality allows for the sales or purchase advance invoice generation, processing and posting based on the posted received/given prepayments. Posting advance invoice post only the calculated VAT amount from the prepayment transactions to both - general ledger and VAT entry. When the final (original) invoice is posted, VAT from with the invoice settled advance invoice is automatically reversed and VAT of the final (original) invoice is posted. If only a partial amount of prepayment is applied, a proportional share of the Advance invoice will be reversed. Advance invoices can be either settled with sales or purchase documents or manually. VAT reversal occurs with the settlement.





1	Received advance invoices
1.1	Setup
1.1.1	Vendor posting profiles
Accounts payable – Setup – Vendor posting profiles
Setup a specific vendor posting profile for posting prepayments (please note, the content of the setup is country-related). Selecting main account in “Sales tax prepayments” field is mandatory if option “Sales tax on prepayment in payment journal” in Accounts payable parameters is marked (see chapter 1.1.3.2). Otherwise, the payment of prepayment cannot be posted in payment journal. 
 
1.1.2	Advance invoice journal
Accounts payable – Payment setup – Prepayment journal names
 
Create new entry, enter name, and select journal type “Prepayment to vendors”. Define voucher series for posting advance invoices, and select Amounts in the journal include sales tax (amounts, including VAT are entered on advance invoice).
1.1.3	Accounts payable parameters
Accounts payable – Setup – Accounts payable parameters
1.1.3.1	Adacta localization
Navigate to Adacta localization section and enable prepayments by selecting “Yes” in Use prepayments field. Select advance invoice journal name for reversal transaction in the field “Reversal journal name”. If advance invoices functionality is used as shown in test case “Purchase order and prepayment invoice” then reversal of advance invoice uses the voucher set up on this journal. 
 
1.1.3.2	Ledger and sales tax
Navigate to Ledger and sales tax section, tab Payment, and select Posting profile for payment journal with prepayment. When payment journal line is marked as prepayment, posting profile changes to the selected one. Mark “Yes” for sales tax on prepayment in payment journal included in the amount. In this case, posting profile should have main account for “Sales tax prepayments” (see Chapter 1.1). 
 

In tab Prepayment invoice, select Posting profile with which prepayment invoices will be posted. This setup will be used only in cases when posting definitions are not in use. Otherways setup from posting definitions is used for posting prepayment invoice.  
 
1.1.4	Procurement category for prepayments
Procurement and sourcing – Procurement categories
If prepayments will be recorded in connection with purchase orders and prepayment invoices, create new procurement category.
 
1.1.4.1	Posting setup for procurement category
Set up main account for posting liability for payment of prepayment.
 
1.1.5	Ledger posting groups
Tax – Setup – Sales tax – Ledger posting groups
If sales tax from prepayment should be posted on separate main account, create new Ledger posting group with sales tax receivable account and settlement account. 
 
Select this ledger posting group in localization field Ledger posting group for tax in prepayments. 
 
If no separate ledger posting group is specified, sales tax from prepayments will be posted with sales tax receivable main account from used ledger posting group.
1.1.6	Sales tax code
Tax – Indirect taxes – Sales tax – Sales tax codes
Some countries might wish to record separate sales tax codes for advance invoices (e.g. Serbia). In this case, create separate sales tax code:
 
1.2	Advance invoice
Accounts payable – Payments – Advance invoice 
Advance invoice is a completely localization feature. It is generated through advance journal. Create new journal and select journal name for Prepayments to vendors. Click on “Lines” to enter journal.
 
To create proposal of all transactions, posted as prepayment (posted with checkmark in field Prepayment journal voucher), navigate to Functions – Create prepayment proposal. 
 
Enter “From date” and “To date” to filter payments of prepayments. Note: in case of prepayment invoice, the date for filter is the posting date of liability (posting date of prepayment invoice) and not the payment date of prepayment invoice. Optionally, enter Posting date and VAT date that advance invoices will be generated with.
Confirm the date parameters. 
 
Advance invoice is created in the journal. If the payment of prepayment was settled against purchase order through Settle open transactions (see test case 1.3.2), the invoice line is generated automatically.
 
If there is no purchase order or the payment of prepayment was not linked to one, the line is not generated. There is an infolog: “Prepayment is not completely allocated to orders.”
 
In this case, manually add the line: 
•	If there is no purchase order, add line with Item type “Text” and insert necessary data (quantity, amount, and sales tax group are populated automatically, enter item sales tax group). 
•	If there is a purchase order that has not been linked, select item type “item”, select purchase order and order line – quantity, amount, and sales tax data will transfer automatically. 
For countries that use separate sales tax codes for advance invoice (e.g. Serbia), it is necessary to change item sales tax group after the line generation.
 
Upon saving the line, Voucher amount/Line amount and Voucher VAT/Line VAT fields are calculated.
 
Enter Document receipt date, Document date, VAT date, and advance invoice number.
 
Check the sales tax that will be posted by each advance invoice by navigating to Inquiries – Sales tax. Check the sales tax for individual advance invoice line by clicking button “Sales tax” in tab Details.
 
Posting the journal posts only VAT. 
 
Check voucher for individual advance invoice by navigating to Inquiries – Voucher. Main account for debit transactions comes from ledger posting group, whereas main account for credit amount is from vendor posting profile (field “Sales tax prepayments”).
 
Check Evidenca PR report with date filter on VAT date to see VAT transaction.
Tax – Declarations – Slovenia – VAT – PR – “Evidenca PR” report
 
Upon posting the final invoice, advance invoice (and with it the posted VAT amount) is reversed. If final invoice is linked to purchase order that was settled against prepayment, reversal happens upon posting the invoice.
 
If there was no purchase order, reversal happens upon manually settling posted invoice and payment of prepayment. Navigate to “Settle transactions” on Vendor account.
 
Mark the transaction of prepayment and final invoice and select “Post”.
 
Message about reversal appears.
 
Check “Evidenca PR” report to see the reversal of VAT that was posted with advance invoice.
 
1.3	Test cases
1.3.1	Purchase order and prepayment invoice
 
Steps:
1	Purchase order: Create purchase order.
2	Prepayment: Define prepayment value on the purchase order.
3	Prepayment invoice: Record and post prepayment invoice.
4	Pay prepayment invoice: Transfer transaction of prepayment invoice to payment journal and post with general posting profile.
5	Advance invoice: Create advance invoice (line is automatically generated because of connection of prepayment to the purchase order) and post the VAT amount.
6	Final invoice: Generate final invoice.
7	Apply prepayment: Apply prepayment invoice. Upon posting the final invoice, advance invoice (and with it the posted VAT amount) is reversed.
Note: if posting definitions are active, functionality of prepayment invoice is standardly not available. Localization enables the usage of prepayment invoice even when posting definitions are active. 
1.3.2	Settle prepayment against purchase order
 
Steps:
1	Payment of prepayment: Create a payment journal with new payment. Mark the payment as a prepayment – posting profile changes to prepayment posting profile. Post the prepayment.
2	Settle prepayment against purchase order: Settle the prepayment against the purchase order – on the Action Pane, use Settle transactions and mark prepayment transaction.
3	Advance invoice: Create advance invoice – line is automatically generated because of connection of prepayment to the purchase order. Posting the advance invoice posts only VAT amount.
4	Final invoice: Create final invoice with link to purchase order. Upon posting, advance invoice is reversed.
1.3.3	Manually settle prepayment and final invoice
 
Steps:
1	Payment of prepayment: Create a payment of prepayment – mark the payment as a prepayment to post it with posting profile for prepayments.
2	Advance invoice: Create advance invoice – manually add the line. Posting the advance invoice posts only VAT amount.
3	Final invoice: Create and post final invoice.
4	Manually settle open transactions: Settle transaction of prepayment payment against the invoice. Upon posting, advance invoice is reversed.
1.3.4	Reverse VAT charge (article 76.a ZDDV-1)
The process can be any from the above. The only difference is that VAT posted with advance invoice (and later reversed by posting the final invoice) is both – sales tax receivable and sales tax payable.
 
2	Issued advance invoices
2.1	Setup
2.1.1	Customer posting profiles
Accounts receivable – Setup – Customer posting profiles
To use the prepayment functionality, you need to setup a specific customer posting profile. Selecting main account in “Sales tax prepayments” field is mandatory if option “Sales tax on prepayment in payment journal” in Accounts receivable parameters is marked (see chapter 2.1.3.2). Otherwise, the received payment of prepayment cannot be posted.
 
2.1.2	Advance invoice journal
Accounts receivable – Payment setup – Prepayment journal names
Create new entry, enter name, and select journal type “Customer’s prepayment”. Define voucher series for posting advance invoices, and select Amounts in the journal include sales tax (amounts, including VAT are entered on advance invoice).
 
2.1.3	Accounts receivable parameters
Accounts receivable – Setup – Accounts receivable parameters
2.1.3.1	Adacta localization
Navigate to Adacta localization and enable prepayments functionality in field “Use prepayments”. 
 
2.1.3.2	Ledger and sales tax
Navigate to Ledger and sales tax section and select a posting profile to use for posting prepayments in payment journals. Select “Yes” in field “Sales tax on prepayment journal voucher”. In this case, posting profile should have main account for “Sales tax prepayments” (see chapter 2.1.1).
 
2.1.4	Ledger posting groups
Tax – Setup – Sales tax – Ledger posting groups
If sales tax from received prepayment should be posted on separate main account, create new Ledger posting group with sales tax payable account and settlement account. 
 
Select this ledger posting group in localization field Ledger posting group for tax in prepayments. 
 
If no separate ledger posting group is specified, sales tax from received prepayments will be posted with sales tax payable main account from used ledger posting group.
2.2	Advance invoice 
Accounts receivable – Payments – Advance invoice 
Advance invoice is a completely localization feature. It is generated through advance journal. Create new journal and select journal name for Customer’s prepayment. Click on “Lines” to enter journal.
 
To create proposal of all transactions, posted as prepayment (posted with checkmark in field Prepayment journal voucher), navigate to Functions – Create prepayment proposal. 
 
Enter date range for received prepayments (“From date”, “To date”) for which advance invoices will be generated. Optionally, enter Posting date and VAT date that advance invoices will be generated with. Confirm the parameters.
 
Advance invoices are created in the journal. If the received payment of prepayment was settled against sales order through Settle open transactions (see test case), the invoice line is generated automatically.
 
If there is no sales order or the payment of prepayment was not linked to one, the line is not generated. There is an infolog: “Prepayment is not completely allocated to orders.”
 
In this case, manually add the line: 
•	If there is no sales order, add line with Item type “Text” (quantity, amount, sales tax group – if defined on customer – are automatically populated, add item sales tax group). 
•	If there is a sales order that has not been linked to received prepayment, select item type “item”, select sales order and order line – quantity, amount, and sales tax data will transfer automatically. 
Upon saving the line, Voucher amount/Line amount and Voucher VAT/Line VAT fields are calculated.
 
Enter VAT date for generated advance invoices.
 
Check the sales tax that will be posted by each advance invoice by navigating to Inquiries – Sales tax. 
 
 
Posting the journal posts only VAT. 
 
Check voucher for individual advance invoice by navigating to Inquiries – Voucher. Main account for credit transactions comes from ledger posting group, whereas main account for debit amount is from customer posting profile (field “Sales tax prepayments”).
 
Advance invoice printout is not included in localization – it is project related. 
Check Evidenca IR report with date filter on VAT date to see VAT transaction.
 
Upon posting the final invoice, advance invoice (and with it the posted VAT amount) is reversed. If final invoice is linked to sales order that was settled against received prepayment, reversal happens upon posting the invoice.
 
If there was no sales order, it is possible to settle received prepayment against free text invoice – if done before posting, reversal happens upon posting the FTI. 
 
If not, navigate to “Settle transactions” on Customer account.
 
Mark the transaction of prepayment and FTI and select “Post”.
 
Message about reversal appears.
 
Check “Evidenca PR” report to see the reversal of VAT that was posted with advance invoice.
 
2.3	Test cases
2.3.1	Prepayment linked to sales order
 
2.3.2	Manually settling received prepayment and FTI
 

