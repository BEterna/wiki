# How To: Set default bank account

This topic includes information about the preferred bank account of the legal entity from which inflows and outflows are preferred to be paid/received.

In terms of inflows (customers), the feature is added so that information about the preferred bank account of the legal entity regarding the expected inflows from customers can be defined on the customer group level. When creating a new customer, when entering the Customer group, the default bank account from the customer group is transferred to newly created customer. When creating sales documents (Sales quotation, Sales order, Sales invoice and FTI), this company bank account is transferred from the customer to the sales documents. The bank account to which company wants to receive inflows in connection with the document should be specified. This bank account is transferred to the following documents if they exist (e.g. from sales order to invoice), but it can also be manually changed on each sales document. Bank account information is also transferred to the document printout and open customer transaction when documents are posted.

In terms of outflows - each vendor bank account can be mapped to a specific company bank account from which payment should later be proposed. Preferred bank account from which outflows for each specific vendor should be paid can be set on each of the vendor’s bank accounts. Information about the specified bank account can be used during payment proposal preparation in the presence of an adequate setup.

[Detailed document](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20ext%20LOC%20Company%20bank%20account%20(customers%20and%20vendors).docx?d=wb79c4fe1e75a4472a8219c19584621e2&csf=1&e=woygzq)

1	CUSTOMERS
Feature is added so that the information about the preffered bank account can be  defined on the document level and later used when printing the document. This way customers are directed to pay to the bank account, preffered by the issuing company. 
1.1	Customer groups
Accounts receivable/Setup/Customer groups
A new field »Company bank account« is added to the Customer groups table. It is possible to select a default bank account for each customer group, to which company wants to receive inflows.
 
1.2	Customers
When creating a new customer, company bank account is transferred from the specified customer group. If no company bank account is specified on the selected customer group, it can also be manually selected on each customer.
 
1.3	Sales documents
When creating sales documents (Sales quotation, Sales order, Sales invoice and FTI), company bank account is transferred from the customer to the document (field »Company bank account«), where it can still be manually changed. This field identifies the bank account to which company wants to receive the future inflows connected with the document.
After customer invoice is posted, Company bank account is transferred to the created open customer transaction.
1.3.1	FTI
Company bank account is transferred from customer to FTI:
 
When FTI is posted, company bank account is transferred to field »Company« on the created open customer transaction:
 

1.3.2	Sales quotation
Company bank account is transferred from customer to the created Sales quotation:
 
1.3.3	Sales order
If Sales order is created from the sales quatation, company bank account is transferred from the sales quotation (and not customer).
 

If Sales order is created without the preexisting Sales quotation, Company bank account is transferred from customer.
1.3.4	Sales invoice
When creating Sales invoice from Sales order, Company bank account is transferred from sales order (not from customer account) to the invoice.
 
When invoice is posted, company bank account from the invoice is transferred to the newly created customer invoice journal and open customer transaction.
 

 
2	Vendors
Feature purpose: Each vendor bank account can be mapped to specific company bank account from which payment should later be proposed. Information is later used during payment proposal preparation. 
2.1	Specify company bank account on vendor's bank account
For each of the vendor's bank accounts it is possible to specify a default company bank account, from which the liabilities towards vendor are expected to be paid.
 
2.2	Vendor invoice
Company bank account from which the liabilities towards vendor are desired to be paid is defaulted from vendor to Vendor invoice  based on the selected vendor's bank account specified on the invoice. Both vendor's and company bank account on the invoice can still be manually changed.
 
After invoice is posted, information about the company bank account from the invoice is transferred to the created open vendor transaction.
 
2.2.1	Vendor invoice journal
Functionality is not supported for invoices generated using Vendor invoice journal. Company bank account in that case will not be transferred to the created open vendor transaction once vendor invoice journal is posted.
2.3	Vendor payment journal
2.3.1	Methods of payment
Company bank accounts is transferred from open vendor transactions to vendor payment journal if payment attribute »Third party bank« is checked on the payment method, used when generating vendor payment lines via the Payment proposal function.
 
2.4	Payment proposal
Accounts payable/Payments/Payment journal
When creating a new payment proposal, company bank account from open customer transaction is transferred to the generated payment journal line as an Offset bank account (via the selected  payment method).
Alternate bank account field displays the vendor's bank account to which the payments should be made. Bank account field displays the company bank account (set on the alternate bank account) from which company will pay the liabilities to vendor.
 

 
NOTE: functionality only works if Payment proposal function is used to create payment journal lines. If payment journal lines are generated manually or with the »Settle transactions« function, offset bank account will not be changed and has to be adjusted manually.
