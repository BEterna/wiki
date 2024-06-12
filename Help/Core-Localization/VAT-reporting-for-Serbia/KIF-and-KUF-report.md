# Create KIF and KUF report

KIF and KUF consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. KIF provides such information for the receivable, while KUF for payable transactions. 

**IMPORTANT**: KIF and KUF functionality within the solution is obsolete for Serbia and part of a legacy functionality for customers that used this functionality in the past. To comply with regulatory and auditing requirements the following reports and inquiries presenting data that is mandatory for POPDV reporting can be used instead:
- Accounts payable - Invoice journal inquiry
- Accounts payable - Vendor Invoice journal report
- Accounts payable - Posted prepayment vendor invoices 
- Accounts receivable - Invoice journal inquiry
- Accounts receivable - Customer Invoice journal report
- Accounts receivable - Posted prepayment customer invoices 
- Tax - Sales tax by vendor report
- Tax - Sales tax by customer report
- Tax - Sales tax general journal reconciliation
- Tax - Sales tax transaction
- Tax - Sales tax/ledger reconciliation
- Tax - Sales tax list
- Tax - Specification
- Tax - Sales tax specification by ledger transaction


## Setup

The main prerequisite: VAT Book reports are available in legal entities with SRB country/region code.

### Sales tax authorities setup

1. Open Tax – Indirect taxes – Sales tax – Sales tax authorities. In order to enable Serbian VAT reports layouts, this setup is required. 
 
### Sales tax reporting codes

1. Open Tax – Setup – Sales tax – Sales tax reporting codes.

The generation of reports is based on **[Reporting codes](Reporting-codes.xlsx)**. Reporting code carries information about which field the transaction will be recorded in. Reporting codes can also be imported using Excel add-in.

### Sales tax codes reporting setup

1. Open Tax – Indirect taxes – Sales tax – Sales tax codes.

VAT reports are generated according to the setup of sales tax reporting codes on sales tax codes. 

## KIF report

1. Open Tax – Declarations – Serbia – VAT – KIF report.
2. Enter reporting parameters such as Sales tax settlement period and VAT dates or/and Posting dates.
3. After confirmation, a report is generated.
 
## KUF report

1. Open Tax – Declarations – Serbia – VAT – KUF report.
2. Enter reporting parameters such as Sales tax settlement period and VAT dates or/and Posting dates.
3. After confirmation, a report is generated.
 


