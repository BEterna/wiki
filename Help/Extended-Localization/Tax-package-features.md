This section summarizes TAX package features, developed in scope of the LOC_TAX extended localization packet.

-----

#Defaulting VAT date and VAT payable date

As part of localization package VAT date is added to some documents (for more details check Localization features) and can be entered manually. With tax package user is able to setup defaulting rules for VAT date calculations. It is possible to set up VAT date and VAT payable date defaulting. Options for defaulting are:
-	None: VAT date has to be entered manually
-	Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
-	Document date: field “Invoice date” on vendor invoice
-	Document receipt date: applicable only for inbound documents

This additional setup for defaulting VAT dates exists in the parameters of the following modules: General ledger, Accounts Payable and Accounts Receivable.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_VAT%20features.docx?d=w42e2c5023dca417b9b1c9c691af0e3bf&csf=1&e=yex0Q8) (chapter 1.1)

-----

#Closing of Settlement period

VAT settlement period can be closed using extended localization feature.  

Field “Closed” is added to Period intervals. If field is marked, period is closed for VAT posting. This means that sales tax transactions can’t be posted into that period. Field can be un-marked whenever wanted.  

-----

#Import of Slovenian taxable persons (SI)

This extended localization feature enables the import of Slovenian taxpayers from Financial Administration of the Republic of Slovenia (FURS). Information like tax registration number, ID number (i.e. company registration number), taxable person type, name, and address of taxpayer, and the information whether partner is liable for Slovenian VAT or whether it has special handling based on 76.a article of ZDDV-1 can be recorded in the list.

For import of taxpayers, it is necessary to insert the URLs of the documents on FURS web page. Links to the adequate documents are available in the document, linked below. After confirming, taxpayers are imported to Slovenian taxable persons. Upon using the feature, users can also choose, whether they want already imported information to be overwritten or only new taxable persons information should be imported. Additionally, this feature also allows for Tax exempt numbers table to be populated with the VAT IDs of the taxable persons, imported with the full taxable persons list from the Slovenian tax authority. 

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Tax%20identification%20number.docx?d=wa2bf0a8b9616456eade04fa02e33d080&csf=1&e=GFXnKo) (chapter 1.7)

-----

#Update customer information based on Tax exempt number (SI)

This extended localization feature enables users to default data when creating new customers, based on the entered tax identification number.

If Slovenian taxpayers have been imported from the database provided by the Slovenian tax authority (FURS), it is possible to select the imported Sales tax numbers/VAT IDs when creating new customers. When creating a new customer, Tax exempt number (Sales tax number/VAT ID) must to be chosen from the drop-down menu. Customer’s Name and Primary address are automatically updated from SI taxpayers entity. 

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Tax%20identification%20number.docx?d=wa2bf0a8b9616456eade04fa02e33d080&csf=1&e=GFXnKo) (chapter 1.8)

-----

#Validate Tax exempt numbers (VIES database)

This extended localization feature makes it possible to validate values entered in “Tax exempt number” field on customer and vendor accounts and through the Tax-exempt numbers form with an online VIES database.

VIES is an electronic means of transmitting information related to VAT registration of companies registered in European Union.  When user needs to verify the VAT number of company from another Member State through VIES on the web, this request will be sent, to the relevant national database to check if the given number is valid. If yes, the "Valid" status will be displayed. If not, "Invalid" status will be displayed.


[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Tax%20identification%20number.docx?d=wa2bf0a8b9616456eade04fa02e33d080&csf=1&e=GFXnKo) (chapter 1.9)