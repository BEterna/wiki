# eInvoices for Slovenia

## **Setup**
---

This topic provides country/region-specific information about how to set up, create and export eInvoices in order to comply with Slovenian and Croatian legislation.

### Export format configuration

1. Open Workspaces – Electronic reporting -> Reporting configurations.
2. Choose Exchange -> Load **[XML file](e-Invoices-SI.zip)** on any configuration. Based on file content it will automatically upload to correct configuration. Before upload, check the latest version of these files with the developer.
3. Click “Browse” and choose the attached files (be sure to upload the Customer invoice model (AD).xml first because the following ones are dependent on it). After the file has loaded, click OK to upload it to configuration.
4. Search for configuration “Customer invoice model (AD)” and expand it to find Project invoice – eSlog 1.6 (SI) and Sales invoice – eSlog 1.6 (SI). Check for status “Completed” in tab Versions.
 
### Electronic invoice parameters

1. Open Accounts receivables – Setup – Slovenia – E-Invoices – Electronic invoice parameters.
2. General eInvoice parameters are set up under tab “General”, such as:
   - Creation of envelope: enable or disable to generate envelope upon eInvoice export or sending. 
   - Automatic sending of eInvoices: enable to automatically download eInvoice after XML is created
   - Bank: company bank for received customer payments (validation upon SWIFT and IBAN is executed in eInvoice registry).
   - The default unit of measure: value in this field is transferred to eInvoice when the unit is not defined on customer invoice (there is no field “Unit” on Free text invoice so the value in this field is always transferred to eInvoice).
   - Signature options – enable/disable “Automatic electronic signing of eInvoice” and define “Electronic signature” options. Possible choices are: 
      - Mandatory: created eInvoices need to be signed with electronic signature using an appropriate valid certificate.
      - Optional: if a valid certificate is available, eInvoices are automatically signed if “Automatic electronic signing of eInvoice” is enabled. Otherwise, the user manually signs eInvoice in the registry. EInvoice can also be sent without a signature.
      - Disabled: eInvoice can be sent without an electronic signature. 
   - Download eInvoice as archive: with this function ZIP file will be generated with eInvoice files (invoice, envelope, and customized visualization). Important: visualization of the document is not part of this localized feature and needs to be implemented during project implementation.  
3. In the “Profile” section create Profile ID and choose adequate Electronic reporting configurations for Sales and FTI, and Project invoice.
 
It is necessary to define eInvoice unique file name in the “Number sequences” section. 
 
### External codes

1. Open Organization administration – Setup – Units – Units.
2. It is necessary to map standard eInvoice units of measure to AX units that will be used on customer invoices (e.g. AX unit “pcs” is defined in eInvoice documentation as “pce”). This is done through External codes, where External code definition and Code both have to be named “eRacun” in order for validation to be successful.
 
Attached below you will find documentation on [eInvoice standard eSLOG 1.6.](e-Invoices-SI.zip) Units of measure can be found on pages 78–81.
 
###  Certificate

1. Open Accounts receivable – Setup – Electronic signature certificates.
2. For testing purposes, it is possible to define a certificate for the electronic signature of eInvoices.
 
### Customer setup - profile ID

1. Define “Profile ID” from eInvoice parameters in tab Invoice and delivery on the customer that eInvoices will be issued for.
2. Mandatory data such as name, address, tax exempt or tax registration number, ID number, and default bank account (and IBAN and SWIFT for that bank account) are being validated in the eInvoice registry upon creating XML (more on that below).

### Customer setup - Taxable person type
1. Go to **Accounts receivable > Customers > All customers > Select Customer > Invoice and delivery tab**
1. Select **Taxable person type** from drop-down menu. Available options: 
   - Legal entity
   - Sole proprietor
   - Natural person

## **EInvoice registry**
---

### Electronic customer invoices

1. Open Accounts receivable – Invoices – E-Invoices – Electronic customer invoices.
2. Posting sales or free text invoices for customers with Profile ID automatically generates eInvoice.
3. Created eInvoice can be found in customer eInvoices registry with status “New”. 
4. To be able to Sign, Export, or Send eInvoice, it is necessary to generate XML file through the button “Create XML”. 
Create XML function executes validation of the following parameters:
   - LEGAL ENTITY ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - INVOICING AND DELIVERY CUSTOMER ACCOUNT INFORMATION (name, a bank account with IBAN and SWIFT; address with country, city and ZIP code)
   - Tax exempt or tax identification number and company identification number on both customer and legal entity (NOTE: adequate registration categories must be selected for each of the required registration IDs: Tax identification number (AD), Company registration number (AD), VAT ID (if VAT ID is entered in Registration IDs)
   - Invoice ID
   - Unit of measure for on invoice used units or a default unit of measure with adequate set up external codes (value for external code must be “eRacun” or validation fails) 
   - Purpose code (either on customer transaction or on legal entity
   - External codes for on invoice used Units of measure or Default unit of measure
   - Currency code

   If any of the listed parameters are missing, the system throws an error and XML is not created. 
 
5. If validation is successful, status is changed to “Created”, eInvoice unique file name is generated as defined in the number sequence. 
6. The XML file is created and stored in the field “Outgoing XML” in tab Details. Here, more information about eInvoice is displayed, including a unique file name, details about the user, creating date, and signature data. 
7. If “Automatic electronic signing of eInvoice” is enabled in eInvoice parameters, eInvoice is automatically signed after XML creation. 
8. After XML has been created, buttons “Create signature” and “Send” are enabled. 
9. Using “Create signature” and “Send” adequately changes the status of eInvoice. 
10. Multiple selections are also enabled for actions. Mark the eInvoices with a checkmark and select appropriate action.

    Manually changing status to higher status is not allowed.
 
11. Using the button “Export” or “Send”, envelope (if enabled in parameters) and eInvoice are downloaded to the selected directory (first, select location for the envelope and save, then the select location for eInvoice and save). If “Export” is used, status stays the same; status is changed to Sent after using the action “Send”.
12. Export of eInvoice before the creation of XML (e.g. status “New” or “Not ready”) is not allowed.
 
Check [Test Scenario](e-Invoices-SI.zip).
 
### Electronic project invoices

1. Open Accounts receivable – Invoices – E-Invoices – Electronic project invoices.
2. Posting invoice proposal for customers with Profile ID automatically generates eInvoice.
3. Created eInvoice can be found in the project eInvoices registry with status “New”. 

Project eInvoices are subject to the same procedures and actions as described in chapter Electronic customer invoices. 

Check **[Test Scenario](e-Invoices-SI.zip)**.

### Subsequent creation of eInvoices

Accounts receivable – Invoices – E-Invoices – Electronic customer/project invoices  button “Select”
EInvoices can be subsequently generated according to selected filters for already posted invoices or invoices deleted from eInvoice registry for the customer with adequate Profile ID. Navigate to button “Select” and define Criteria for the subsequent creation of eInvoices. 
 
After confirming, subsequent eInvoices are created with status “Not ready”.
 
Proceed with the same procedures and actions as described in the chapters above. 

Check **[Test Scenario](e-Invoices-SI.zip)**.
