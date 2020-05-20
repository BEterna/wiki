Following fields are added to Customer and Vendor: 

## Tax registration number
 Davčna številka in Slovenian localization and OIB in Croatian localization. 

1. Go to **Accounts receivable > Customers > All customers > Select customer > Invoice and delivery tab > Tax registration number field** or **Accounts payable> Vendors > All Vendors > Select Vendor > Invoice and delivery tab > Tax registration number field**
1. Enter **Tax registration number** manually or select from drop-down list
1. Drop-down list shows information from SI Taxable persons
1. _Valid only for SI_: If value is selected from SI Taxable persons list (Slovenia), values in the field Taxable person type, Company ID and Tax exempt code (if Customer/Vendor is liable for VAT) are **populated automatically**.


## Taxable person type (SI only) 
Three types of taxable perons are available: 



## Company ID (MŠ - si)

Implemented defaulting of taxable person type, vat id and company id from tax registration number when selected (slovenian taxable persons

dentification retrieval priority: OK
Customer/vendor: 
DŠ/OIB:  OK. Če obstaja podatek na kupcu in v Registration ID's, se na Reporting tab na TAx trans vzame podatek iz kupca. V nasprotnem primeru se vzame podatek iz Registratin ID.  
1. Tax registration number on customer or vendor
2. Registration IDs
Company ID (MŠ): OK Če obstaja podatek na kupcu in v Registration ID's, se na reporte vzame podatek iz kupca. V nasprotnem primeru se vzame podatek iz Registratin ID.
1. ID number on customer or vendor
2. Registrations IDs 
Legal entity:
DŠ/OIB: OK
1. Tax registration number on legal entity
2. Registration IDs
VAT num.: OK
1. VAT exempt number export on legal entity
2. Registrations IDs 