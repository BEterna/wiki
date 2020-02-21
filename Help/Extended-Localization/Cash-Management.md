# How To: Post Petty Cash

## Setup

Before you can use the petty cash functionality, you must complete the following prerequisites:
   - Set up cash accounts
   - Set up cash posting profiles
   - Set up number sequences for cash document numbering
   - Set up default values for Cash and bank management parameters
   - Set up cash journal names in General ledger

### Cash account setup

1. Petty cash accounts can be defined at Cash and bank management > Bank accounts > Cash accounts.
2. During the creation of a new cash account, it is possible to define:
   - Cash: code to identify cash account.
   - Name: description of the cash account.
   - Currency: default currency code for cash transactions.
   - Number sequence group: If the numbering of cash documents must differ from the numbering that is specified in the parameters, enter a code
   - More currencies: if posting in currencies that differ from the accounting currency is allowed 
   - Negative cash: if negative cash balances in any currency are allowed
   - Denomination summary required: if information about denominations are required
 
### Cash posting profile setup

1. Open Cash and bank management > Setup > Cash posting profiles.
2. In order to make integration with the General ledger, it is necessary to set up a cash posting profile and apply the appropriate main account for cash accounts.
 
### Cash and bank management parameters

1. Open Cash and bank management > Setup > Cash and bank management parameters.
2. On the Cash tab, enter the information for cash accounts.
3. On the Number sequence tab, specify number sequence codes for the Cash reimbursement slips, Cash disbursement slips, Cash correction voucher, and Exchange adjustment documents, and for the Cash report number.

### Cash journal setup

1. Open General Ledger > Journal setup > Journal names.
2. For posting cash transactions it is necessary to create new journal with Journal type “Cash”.
 
## Daily procedures

### Generate cash journal (Slip journal)

1. Open Cash and bank management > Cash transactions > Slip journal.
2. Create a new journal. Add a new line, and enter the following information:
   - Date - enter the date of the transaction.
   - Account - select the cash account. By default, a cash account is specified in the Cash and bank management parameters.
   - Description - enter explanatory text for the transaction.
   - Debit/Credit - use this field to register the amount of cash receipts/cash expenditures. The document type is filled in automatically, based on the amount that you entered for the cash document: 
     - Cash reimbursement slip – This value is used if you entered an amount in the Debit field for the cash account.
     - Cash disbursement slip – This value is used if you entered an amount in the Credit field for the cash account.
     - Correction – You entered a negative amount in either the Debit field or the Credit field for the cash account.
 
  - Approval status – The first transaction status is None. For information about how to set the transaction status, see the Approve and post cash journal section.
  - Sales tax group,  Item sales tax group – Specify group codes on tab General to calculate taxes on the operation.
  - Reason – On the Cash order tab, enter the text that describes the transaction subject. This text will be printed on the cash slip reporting form.
  - Document / Document date / Date receipt date – Enter the description, number, and date of the primary document that is the reason for the transaction (for example, advance reports, invoice, or order).
  - Representative type - This field can have the following values:<br>
      - Worker – The Representative lookup contains a list of employees if the Offset account field is set to Ledger or Bank, or a list of the counteragent's contact persons if the Offset account field is set to Customer or Vendor. To set up representatives, go to Basic – Setup – Contacts – Contact person.<br>
     - Vendor – The Representative lookup contains a list of vendors. <br>
     - Customer – The Representative lookup contains a list of customers.<br>
  - Representative - Select a representative of the type that you specified in the Representative type field.
  - Name of person – This field is filled in automatically, based on the Offset account and Representative fields. The printing form for cash slips will reflect this information.
  - Officials -  Are added automatically from Officials setup in Organization administration > Setup > Contacts > Officials and can be changed manually. 
  - Posting profile - Enter the posting profile for the cash account. By default, the posting profile that is specified in the Cash and bank management parameters is used.
 
It is also enabled to select Offset posting profile.

### Approve and post cash journal

1. To confirm a transaction, select the corresponding Slip journal line, and click Documents approval -> Approve. The transaction status is changed to Approved, and you can no longer edit the journal line. 
 The Approved status indicates that cash funds are received or expended. The cash balance is changed. Only approved cash transactions can be posted.
2. To cancel an Approved status and reset the status to None, click Documents approval -> Reset status. 
3. To post a journal, click Post -> Post and result of posting can be found in posted voucher transactions. 
 
## Cash management – inquiries and reports

### Cash order report

1. To print a cash order, select a Slip journal line, and then, on the Action Pane, click Print > Cash order report. Slip journal lines that have Confirmed, Approved, or Rejected status can be printed. 
2. The system generates a printing form for either a Cash reimbursement slip or a Cash disbursement slip, depending on whether an amount is entered in the Debit field the or Credit field for the selected line:
   - Amount in the Debit field: Cash reimbursement slip
   - Amount in the Credit field: Cash disbursement slip
      
### Cash report

1. After posting all cash transactions, one of the daily procedures should be the generation of cash reports. Navigate to Cash and bank management > Bank accounts > Cash accounts.
2. For each cash account, it is necessary to run procedure to create a cash report on a daily basis. Select appropriate cash account and press Create cash report. Enter parameters for “To date” and the user who creates the report.

All created cash reports can be reviewed/approved/printed if you press Created cash reports for a selected cash account.
 
For each cash report, there is possibility to see related cash transactions.  
 
3. To approve daily cash reports, press Document approval > Approve for the selected report number. 
4. For the approval process, it is necessary to enter Employee name who approves the report.
5. To print a daily cash report, press Print for the selected report number.
 
### Cash book

1. Open Cash and bank management > Inquiries and reports > Cash book report.
2. The report reflects actual cash fund movements (receipts and expenditures).
 
### Journal of registration

1. Open Cash and bank management > Inquiries and reports > Journal of registration of cash vouchers.
2. The report reflects all cash reimbursement and cash disbursement slips that have been issued.
 
