This section summarizes TAX package features, developed in scope of the LOC_TAX extended localization packet.

-----

#Defaulting VAT date and VAT payable date

According to the local legislation, a taxable event occurs when goods/services are received/delivered or when goods are imported in case of goods from other EU countries, while multiple exceptions exist. Hence, the obligation to report the calculated VAT occurs with the taxable event. By standard D365O posts tax transactions on the transaction posting date, which is not in line with the local legal requirements. Therefore, to post, settle and report VAT according to the local legal requirements, additional VAT date (VAT date, VAT Payable date and Document receipt date) fields were added to sales and purchase documents from where they are transferred to tax transactions.

In scope of this extended localization functionality, in order to facilitate the posting, there is a possibility to set up VAT date and VAT payable date defaulting. Options for defaulting are:
-	None: VAT date has to be entered manually
-	Posting date: VAT date defaults from posting date (field “Date” in journals and FTI, “Invoice date” on Sales invoice)
-	Document date: field “Invoice date” on vendor invoice
-	Document receipt date: applicable only for inbound documents

This additional setup for defaulting VAT dates exists in the parameters of the following modules: General ledger, Accounts Payable and Accounts Receivable.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_VAT%20features.docx?Web=1) (chapter 1.1)

-----

#Import of Slovenian taxable persons (SI)

This extended localization feature enables the import of Slovenian taxpayers from Financial Administration of the Republic of Slovenia (FURS). Information like tax registration number, ID number (i.e. company registration number), taxable person type, name, and address of taxpayer, and the information whether partner is liable for Slovenian VAT or whether it has special handling based on 76.a article of ZDDV-1 can be recorded in the list.

For import of taxpayers, it is necessary to insert the URLs of the documents on FURS web page. Links to the adequate documents are available in the document, linked below. After confirming, taxpayers are imported to Slovenian taxable persons. Upon using the feature, users can also choose, whether they want already imported information to be overwritten or only new taxable persons information should be imported. Additionally, this feature also allows for Tax exempt numbers table to be populated with the VAT IDs of the taxable persons, imported with the full taxable persons list from the Slovenian tax authority. 

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapter 1.7)

-----

#Update customer information based on Tax exempt number (SI)

This extended localization feature enables users to default data when creating new customers, based on the entered tax identification number.

If Slovenian taxpayers have been imported from the database provided by the Slovenian tax authority (FURS), it is possible to select the imported Sales tax numbers/VAT IDs when creating new customers. When creating a new customer, Tax exempt number (Sales tax number/VAT ID) has to be chosen from the drop-down menu. Customer’s Name and Primary address are automatically updated from SI taxpayers entity. Feature allows the automatic transfer of Customer’s Name and Primary address from SI taxpayers table, based on the entered value in field “Tax exempt number” when creating new customer.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapter 1.8)

-----

#Validate Tax exempt numbers (VIES database)

VIES is an electronic mean of validating VAT-identification numbers of economic operators registered in the European Union for cross border transactions on goods or services. When you need to verify the VAT number of your customer in another Member State through VIES on the web, this request will be sent, through a secure connection, to the relevant national database to check if the given number is recorded there. If yes, the "Valid" status will be displayed. If not, "Invalid" status will be displayed.

This extended localization feature makes it possible to validate values entered in “Tax exempt number” field on customer and vendor accounts and through the Tax-exempt numbers form with an online VIES database.

[Detailed documentation](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Tax%20identification%20number.docx?Web=1) (chapter 1.9)