# How To: Send Sales Documents to fiscalization

Fiscalization is fiscal law designed to avoid retailer fraud in Slovenia and Croatia. Fiscal law about cash registers has been introduced in countries to control the grey economy by enforcing all mandatory transaction reporting to the authorities. According to fiscal law, an appropriate fiscal receipt has to be printed and given to the customer.

The feature allows the generation of the number sequence on sales documents (Sales Order, Free text invoice, Project Invoice, Prepayment invoice, FTI corrections, Credit notes, Collection letters, Interest notes, and Advance invoices) according to the Fiscal law. The fiscal number can be seen in the field “Invoice” on Customer transactions. After posting, the transaction is displayed in Fiscalization documents.

The feature is part of the LOC_FISCALIZATION extended localization package.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Fiscalization.docx?d=wae690415ee784c6caee16a4a491ec95f&csf=1&e=mZe1gX)

## Setup

### General ledger parameters

1. Open General ledger – Ledger setup – General ledger parameters.
2. Navigate to Adacta localization, tab Fiscalization:
   - Fiscalization: enable functionality to use fiscalization of outbound documents
   - Separator: define delimiter that identifies the distinction between different sets of fiscal numbers; allowed characters are \ / * - _|. : ; 
   - Fiscalization document: enable documents that need to use fiscalization numbering (note: standard numbering is replaced with fiscal numbering; voucher numbering remains standard!)
 
### Fiscalization – locations

1. Open General ledger – Fiscalization – Locations.
2. An integral part of the fiscal number is the company’s location. Create a new entry and identify the location.
 
### Fiscalization – terminals

1. Open General ledger – Fiscalization – Terminals.
2. Create a new terminal and select an adequate location.
 
### Fiscalization number sequence setup

1. Open General ledger – Fiscalization – Fiscalization number sequence setup.
2. The third part of the fiscal number is invoice number which is determined by fiscalization number sequence. 
3. Create a new entry, specify effectively and expiration dates, and define Location and Terminal. Create a number sequence code to select in the Fiscalization sequence field. Be careful to select Continuous numbering.
 
### Worker’s tax identification number

The worker who creates outbound documents should have a valid tax identification number defined.
 
If the tax identification number is not defined on Worker, the error is thrown upon document posting.
 
## Fiscalization documents

1. Open General ledger – Inquiries and reports – Fiscalization – Fiscalization documents.
2. Overview of all transactions with fiscal number contains all the data that are sent to tax authority. 
3. Using the button “Open document” in section Fiscalization, source document data is displayed for the selected transactions. 

### Sales invoice

Posting sales invoice standardly does not generate infolog with information about the posted invoice.<br>
The fiscal number can be seen in the field “Invoice” on Customer transaction.<br>
After posting, the transaction is displayed in Fiscalization documents. 
 
### Free text invoice

Upon FTI posting, infolog with information about the fiscal number is generated.<br> 
Field “Invoice” on Customer transaction is populated with the generated fiscal numbers.
 
2.2.1	Correct FTI

Correcting FTI generates new fiscal number.
To correct a free text invoice that has already been posted, select the posted free text invoice. On the Invoice page, in section Cancel, select “Correct invoice”. Define a reason code, add comments, and select the date for new corrected invoice. Modify the corrected invoice, and post it.
 
After posting, fiscal numbers are generated for cancelling and corrected invoices.
 
Field “Invoice” on Customer transactions is populated with fiscal number of posted invoice.
 
Fiscal numbers of cancelled and corrected invoices can be seen in the list of all fiscalization documents.
 
2.3	Credit note
Fiscal number is generated after posting credit note.
 
It can be seen in field “Invoice” on Customer transaction.
 
Posted document can be seen in the list of all fiscalization documents.
 
2.4	Advance invoice
Posting advance invoice generates fiscal number that is recorded in field “Invoice”.
 
Reversing advance invoice also generates fiscal number.
 
Posted document can be seen in the list of all fiscalization documents
 
2.5	Project invoice
Posting invoice proposal generates fiscal number that is recorded in field “Invoice”.
 
Check all project invoices to find fiscal number in field “Invoice”.
 
Posted document can be seen in the list of all fiscalization documents.
 
2.6	Collection letter
Collection letters are generated with fiscal numbers. 
 
Right after creation they can be seen in Fiscalization documents form.
 
Posting collection letter generates fiscal number. 
 
Field “Invoice” on Customer transaction is populated with fiscal number.
 
2.7	Interest note
Created interest notes have fiscal numbers.
 
Transactions can be seen in Fiscalization documents list.
 
Posted transaction is generated with fiscal number.
 
Customer transaction has fiscal number in field Invoice.
 
3	Test cases
                           
