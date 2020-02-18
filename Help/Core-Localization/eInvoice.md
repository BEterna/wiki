# How To: Create eInvoices for Slovenia and Croatia

An electronic invoice (eInvoice) is sent electronically over the internet, rather than being paper-based, and can be easily integrated into a customer's accounts payable system. In Slovenia and Croatia, eInvoices are mandatory to be used for the country budget users (governmental bodies) according to current local legislations (e.g. ZOPSPU - The law on the provision of payment services to budget users in case of Slovenia). 

This localized feature enables to set up, generate, process, review, sign (SI) and export customer eInvoices, in accordance with the supported local eInvoice formats (e.g. eSlog in case of Slovenia), which local (Slovenian or Croatian) budget users currently use. Using this localization feature, eInvoices can be created automatically when posting customer, vendor or project invoices and exported to the required XML formats.

## Setup

This topic provides country/region-specific information about how to set up, create and export eInvoices in order to comply with Slovenian and Croatian legislation.


1.1	Export format configuration
Workspaces – Electronic reporting  Reporting configurations
 
Choose Exchange  Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
 
Files for upload are attached below. Before upload, check the latest version of these files with developer.
   
Click “Browse” and choose attached files (be sure to upload Customer invoice model (AD).xml first because the following ones are dependent on it). After the file has loaded, click OK to upload it to configuration.
 
Search for configuration “Customer invoice model (AD)” and expand it to find Project invoice – eSlog 1.6 (SI) and Sales invoice – eSlog 1.6 (SI). Check for status “Completed” in tab Versions.
 
1.2	Electronic invoice parameters
Accounts receivables – Setup – Slovenia – E-Invoices – Electronic invoice parameters
General eInvoice parameters are set up under tab “General”, such as:
•	Creation of envelope: enable or disable to generate envelope upon eInvoice export or sending. 
•	Automatic sending of eInvoices: enable to automatically download eInvoice after XML is created
•	Bank: company bank for received customer payments (validation upon SWIFT and IBAN is executed in eInvoice registry).
•	Default unit of measure: value in this field is transferred to eInvoice when unit is not defined on customer invoice (there is no field “Unit” on Free text invoice so the value in this field is always transferred to eInvoice).
•	Signature options – enable/disable “Automatic electronic signing of eInvoice” and define “Electronic signature” options. Possible choices are: 
o	Mandatory: created eInvoices need to be signed with electronic signature using appropriate valid certificate.
o	Optional: if valid certificate is available, eInvoices are automatically signed if “Automatic electronic signing of eInvoice” is enabled. Otherwise, the user manually signs eInvoice in the registry. EInvoice can also be sent without signature.
o	Disabled: eInvoice can be sent without electronic signature. 
•	Download eInvoice as archive: with this function ZIP file will be generated with eInvoice files (invoice, envelope and customized visualization). Important: visualization of the document is not part of this localized feature and needs to be implemented during project implementation.  
 

In “Profile” section create Profile ID and choose adequate Electronic reporting configurations for Sales and FTI, and Project invoice.
 
It is necessary to define eInvoice unique file name in “Number sequences” section. 
 
1.3	External codes
Organization administration – Setup – Units – Units
It is necessary to map standard eInvoice units of measure to AX units that will be used on customer invoices (e.g. AX unit “pcs” is defined in eInvoice documentation as “pce”). This is done through External codes, where External code definition and Code both have to be named “eRacun” in order for validation to be successful.
 
Attached below you will find documentation on eInvoice standard eSLOG 1.6. Units of measure can be found in pages 78–81.
 
1.4	Certificate
Accounts receivable – Setup – Electronic signature certificates
For testing purposes it is possible to define certificate for electronic signature of eInvoices.
 
1.5	Customer setup
Define “Profile ID” from eInvoice parameters in tab Invoice and delivery on customer that eInvoices will be issued for.
 
Mandatory data such as name, address, tax exempt or tax registration number, ID number, and default bank account (and IBAN and SWIFT for that bank account) are being validated in eInvoice registry upon creating XML (more on that below).
2	EInvoice registry
2.1	Electronic customer invoices
Accounts receivable – Invoices – E-Invoices – Electronic customer invoices 
Posting sales or free text invoice for customer with Profile ID automatically generates eInvoice.
 
Created eInvoice can be found in customer eInvoices registry with status “New”. 
 
To be able to Sign, Export, or Send eInvoice, it is necessary to generate XML file through button “Create XML”. 
Create XML function executes validation of the following parameters:
•	LEGAL ENTITY ACCOUNT INFORMATION (name, bank account with IBAN and SWIFT; address with country, city and ZIP code)
•	INVOICING AND DELIVERY CUSTOMER ACCOUNT INFORMATION (name, bank account with IBAN and SWIFT; address with country, city and ZIP code)
•	Tax exempt or tax identification number and company identification number on both customer and legal entity (NOTE: adequate registration categories must be selected for each of the required registration IDs: Tax identification number (AD), Company registration number (AD), VAT ID (if VAT ID is entered in Registration IDs)
•	Invoice ID
•	Unit of measure for on invoice used units or a default unit of measure with adequate set up external codes (value for external code must be “eRacun” or validation fails) 
•	Purpose code (either on customer transaction or on legal entity
•	External codes for on invoice used Units of measure or Default unit of measure
•	Currency code
If any of listed parameters is missing, system throws an error and XML is not created. 
 
If validation is successful, status is changed to “Created”, eInvoice unique file name is generated as defined in number sequence. 
 
XML file is created and stored in field “Outgoing XML” in tab Details. Here, more information about eInvoice is displayed, including unique file name, details about user, creating date, and signature data. 
 
If “Automatic electronic signing of eInvoice” is enabled in eInvoice parameters, eInvoice is automatically signed after XML creation. 
After XML has been created, buttons “Create signature” and “Send” are enabled. 
 
Using “Create signature” and “Send” adequately changes the status of eInvoice. 
 
Multiple selection is also enabled for actions. Mark the eInvoices with checkmark and select appropriate action.
 
Manually changing status to higher status is not allowed.
 
Using button “Export” or “Send”, envelope (if enabled in parameters) and eInvoice are downloaded to selected directory (first, select location for envelope and save, then select location for eInvoice and save). If “Export” is used, status stays the same; status is changed to Sent after using action “Send”.
 
Export of eInvoice before creation of XML (e.g. status “New” or “Not ready”) is not allowed.
 
2.1.1	Test cases for FTI and Sales invoice
 
2.2	Electronic project invoices
Accounts receivable – Invoices – E-Invoices – Electronic project invoices 
Posting invoice proposal for customer with Profile ID automatically generates eInvoice.
 
Created eInvoice can be found in project eInvoices registry with status “New”. 
 
Project eInvoices are subject to the same procedures and actions as described in chapter 2.1 Electronic customer invoices. 
2.2.1	Test case for project invoice
 
2.3	Subsequent creation of eInvoices
Accounts receivable – Invoices – E-Invoices – Electronic customer/project invoices  button “Select”
EInvoices can be subsequently generated according to selected filters for already posted invoices or invoices deleted from eInvoice registry for the customer with adequate Profile ID. Navigate to button “Select” and define Criteria for subsequent creation of eInvoices. 
 
After confirming, subsequent eInvoices are created with status “Not ready”.
 
Proceed with the same procedures and actions as described in chapters above. 
2.3.1	Test case 
 

