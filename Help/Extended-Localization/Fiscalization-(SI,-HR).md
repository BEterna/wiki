Fiscalization is fiscal law designed to avoid retailer fraud in Slovenia and Croatia. Fiscal law about cash registers has been introduced in countries to control the grey economy by enforcing all mandatory transaction reporting to the authorities. According to fiscal law, an appropriate fiscal receipt has to be printed and given to the customer.

Feature allows the generation of number sequence on sales documents (Sales Order, Free text invoice, Project Invoice, Prepayment invoice, FTI corrections, Credit notes, Collection letters, Interest notes  and Advance invoices) according to the Fiscal law. Fiscal number can be seen in field “Invoice” on Customer transaction. After posting, transaction is displayed in Fiscalization documents.

Feature is part of the LOC_FISCALIZATION extended localization package.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365%20ext%20LOC_Fiscalization.docx?d=wae690415ee784c6caee16a4a491ec95f&csf=1&e=mZe1gX)


1	Setup
1.1	General ledger parameters
General ledger – Ledger setup – General ledger parameters
Navigate to Adacta localization, tab Fiscalization:
•	Fiscalization: enable functionality to use fiscalization of outbound documents
•	Separator: define delimiter that identifies the distinction between different sets of fiscal number; allowed characters are \ / * - _|. : ; 
•	Fiscalization document: enable documents that need to use fiscalization numbering (note: standard numbering is replaced with fiscal numbering; voucher numbering remains standard!)
 
1.2	Fiscalization – locations
General ledger – Fiscalization – Locations
Integral part of fiscal number is company’s location. Create new entry and identify location.
 
1.3	Fiscalization – terminals
General ledger – Fiscalization – Terminals
Create new terminal and select adequate location.
 
1.4	Fiscalization number sequence setup
General ledger – Fiscalization – Fiscalization number sequence setup
The third part of fiscal number is invoice number which is determined by fiscalization number sequence. 
 
Create new entry, specify effective and expiration dates, and define Location and Terminal. Create number sequence code to select in Fiscalization sequence field. Be careful to select Continuous numbering.
 
1.5	Worker’s tax identification number
Worker who creates outbound documents should have valid tax identification number defined.
 
If tax identification number is not defined on Worker, error is thrown upon document posting.
 
2	Fiscalization documents
General ledger – Inquiries and reports – Fiscalization – Fiscalization documents
Overview of all transactions with fiscal number contains all the data that are sent to tax authority. 
 
Using button “Open document” in section Fiscalization, source document data is displayed for selected transaction. 
 

2.1	Sales invoice
Posting sales invoice standardly does not generate infolog with information about posted invoice.
 
Fiscal number can be seen in field “Invoice” on Customer transaction.
 
After posting, transaction is displayed in Fiscalization documents. 
 
2.2	Free text invoice
Upon FTI posting, infolog with information about fiscal number is generated. 
 
Field “Invoice” on Customer transaction is populated with generated fiscal number.
 
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
                           
