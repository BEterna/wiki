1	Setup for Cash Management feature
Before you can use the petty cash functionality, you must complete the following prerequisites:
•	Set up cash accounts
•	Set up cash posting profiles
•	Set up number sequences for cash document numbering
•	Set up default values for Cash and bank management parameters
•	Set up cash journal names in General ledger
1.1	Cash account setup
Petty cash accounts can be defined at Cash and bank management > Bank accounts > Cash accounts.
 
During creation of new cash account, it is possible to define:
•	Cash: code to identify cash account
•	Name: description of the cash account
•	Currency: default currency code for cash transactions
•	Number sequence group: If the numbering of cash documents must differ from the numbering that is specified in the parameters, enter a code
•	More currencies: if posting in currencies that differ from the accounting currency is allowed 
•	Negative cash: if negative cash balances in any currency are allowed
•	Denomination summary required: if information about denominations are required
 
1.2	Cash posting profile setup
Cash and bank management > Setup > Cash posting profiles
In order to make integration with General ledger it is necessary to set up cash posting pofile and apply appropriate main account for cash accounts.
 
1.3	Cash and bank management parameters
Cash and bank management > Setup > Cash and bank management parameters
On the Cash tab, enter the information for cash accounts.
 
On the Number sequence tab, specify number sequence codes for the Cash reimbursement slips, Cash disbursement slips, Cash correction voucher, and Exchange adjustment documents, and for Cash report number.
1.4	Cash journal setup
General Ledger > Journal setup > Journal names
For posting of cash transactions it is necessary to create new journal with Journal type “Cash”.
 
2	Daily procedures
2.1	Generate cash journal (Slip journal)
Cash and bank management > Cash transactions > Slip journal,
Create a new journal. Add a new line, and enter the following information:
Date - enter the date of the transaction.
Account - select the cash account. By default, a cash account is specified in the Cash and bank management parameters.
Description - enter explanatory text for the transaction.
Debit/Credit - use this field to register amount of cash receipts/cash expenditures. Document type is filled in automatically, based on the amount that you entered for the cash document: 
•	Cash reimbursement slip – This value is used if you entered an amount in the Debit field for the cash account.
•	Cash disbursement slip – This value is used if you entered an amount in the Credit field for the cash account.
•	Correction – You entered a negative amount in either the Debit field or the Credit field for the cash account.
 
Approval status – The first transaction status is None. For information about how to set the transaction status, see the Approve and post cash journal section.

Sales tax group,  Item sales tax group – Specify groups codes on tab General to calculate taxes on the operation.

Reason – On the Cash order tab, enter text that describes the transaction subject. This text will be printed on the cash slip reporting form.

Document / Document date / Date receipt date – Enter the description, number, and date of the primary document that is the reason for the transaction (for example, advance reports, invoice, or order).
Representative type - This field can have the following values:
•	Worker – The Representative lookup contains a list of employees if the Offset account field is set to Ledger or Bank, or a list of the counteragent's contact persons if the Offset account field is set to Customer or Vendor. To set up representatives, go to Basic – Setup – Contacts – Contact person.
•	Vendor – The Representative lookup contains a list of vendors. 
•	Customer – The Representative lookup contains a list of customers.
Representative - Select a representative of the type that you specified in the Representative type field.
Name of person – This field is filled in automatically, based on the Offset account and Representative fields. The printing form for cash slips will reflect this information.
 



Officials -  Are added automatically from Officials setup in Organization administration > Setup > Contacts > Officials and can be changed manually. 
 
Posting profile - Enter the posting profile for the cash account. By default, the posting profile that is specified in the Cash and bank management parameters is used.
 
It is also enabled to select Offset posting profile.
2.2	Approve and post cash journal
To confirm a transaction, select the corresponding Slip journal line, and click Documents approval  Approve. The transaction status is changed to Approved, and you can no longer edit the journal line. 
 
The Approved status indicates that cash funds are received or expended. The cash balance is changed. Only approved cash transactions can be posted.
 
To cancel an Approved status and reset the status to None, click Documents approval  Reset status. 
 
To post a journal, click Post Post and result of posting can be found in posted voucher transactions. 
 
3	Cash management – inquiries and reports
3.1	Cash order report
To print a cash order, select a Slip journal line, and then, on the Action Pane, click Print > Cash order report. Slip journal lines that have Confirmed, Approved, or Rejected status can be printed. 
 
The system generates a printing form for either a Cash reimbursement slip or a Cash disbursement slip, depending on whether an amount is entered in the Debit field the or Credit field for the selected line:
•	Amount in the Debit field: Cash reimbursement slip
•	Amount in the Credit field: Cash disbursement slip

      
3.2	Cash report
After posting of all cash transactions, one of daily procedures should be generation of cash report. Naviagte to Cash and bank management > Bank accounts > Cash accounts.
 
For each cash account it is necessary to run procedure to create cash report on daily basis. Select appropriate cash account and press Create cash report. Enter parameters for “To date” and user who creates the report.
 
All created cash reports can be reviewed/approved/printed if you press Created cash reports for selected cash account.
 
 
For each cash report there is possibility to see related cash transactions.  
 
To approve daily cash reports, press Document approval > Approve for selected report number. 
 
For approval process it is necessary to enter Employee name who approves the report.
 
To print daily cash report, press Print for selected report number.
 
 
3.3	Cash book
Cash and bank management > Inquiries and reports > Cash book report 
The report reflects actual cash fund movements (receipts and expenditures).
 
 
3.4	Journal of registration
Cash and bank management > Inquiries and reports > Journal of registration of cash vouchers 
The report reflects all cash reimbursement and cash disbursement slips that have been issued.
 
