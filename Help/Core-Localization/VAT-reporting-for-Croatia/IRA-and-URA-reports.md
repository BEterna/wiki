# Create an IRA and URA report

IRA and URA consist of the receivable and payable tax transactions and provide data about the applicable VAT rates for each of the sales tax transactions. IRA provides such information for the receivable, while URA for payable transactions. These two lists have to be available to be extracted from D365, in case the adequate Croatian tax authority requires so. URA report can be exported as XML file in the format, accepted by the Croatian tax authorities.
 
## IRA report 
---
###IRA form

1. Open **Tax > Declarations > Croatia  > VAT > IRA form**.
2. Enter reporting parameters such as Sales tax settlement period and VAT dates or/and Posting dates. 
3. After confirmation, the report is generated. 

###IRA report form
IRA report form is a form that can show all VAT transactions, including non-taxable items (Prolazne stavke). Use this form for more comprehensive VAT control and better control between the Invoice journal and the IRA form. To include non-taxable items it is needed to create a new **sales tax code** which will be used for all non-taxable items that can appear on the invoice. For this new sales tax code it is recommended to use a separate **settlement period** for easier review of those VAT transactions in IRA report form. 

To open IRA report form follow the steps: 
1. Open **Tax > Declarations > Croatia > VAT > IRA report form**
2. Click the button “Show report in table” to open reporting parameters. Define the Settlement periods and dates. 
   - to review VAT transactions for sales tax codes associated with _only one settlement period_, enter this settlement period in the field Settlement period
   - to review VAT transactions for sales tax codes associated with _two different settlement periods_, enter one settlement period in the field Settlement period and the second one in the field Non-reporting settlement period
   - to review _all VAT transactions_ leave empty both fields for settlement periods 

3. After confirmation, a list of all relevant transactions for the defined date range and settlement periods is created. Use the function “Export to Excel” to export lines to Excel. Combination Ctrl + Shift + E can also be used for export.

## URA report 
---
###URA form
URA report form is a form that can show all VAT transactions, including non-taxable items (Prolazne stavke). Use this form for more comprehensive VAT control and better control between the Invoice journal and the URA form. To include non-taxable items it is needed to create a new **sales tax code** which will be used for all non-taxable items that can appear on the invoice. For this new sales tax code it is recommended to use a separate **settlement period** for easier review of those VAT transactions in URA report form. 


To open URA report form follow the steps: 
1. Open **Tax > Declarations > Croatia > VAT > URA report form**
2. Click the button “Show report in table” to open reporting parameters. Define the Settlement periods and dates. 
   - to review VAT transactions for sales tax codes associated with _only one settlement period_, enter this settlement period in the field Settlement period
   - to review VAT transactions for sales tax codes associated with _two different settlement periods_, enter one settlement period in the field Settlement period and the second one in the field Non-reporting settlement period
   - to review _all VAT transactions_ leave empty both fields for settlement periods 

3. After confirmation, a list of all relevant transactions for the defined date range and settlement periods is created. Use the function “Export to Excel” to export lines to Excel. Combination Ctrl + Shift + E can also be used for export.

### Export URA form to XML
1. Open **Tax > Declarations > Croatia > VAT > Export URA form to XML**.
2. Enter reporting parameters such as Responsible employee, Sales tax settlement period and VAT dates or/and Posting dates, File name. 
3. After confirmation, the report is generated. 

###URA report form
1. Open **Tax > Declarations > Croatia > VAT > URAreport form**
2. Click the button “Show report in table” to open reporting parameters. Define the Settlement periods and dates. After confirmation, a list of all relevant transactions in the defined period is created.
3. Use the function “Export to Excel” to export lines to Excel. Combination Ctrl + Shift + E can also be used for export.