This topic provides country/region-specific information about setting up, creating, and exporting eInvoices in the prescribed electronic form (UBL 2.1 standard) to comply with Serbian legislation. eInovices can be generated for the following document types:
- Free text invoice / Credit note
- Sales Invoice / Credit note
- Project invoice / Credit note
- Advance invoice / Credit note (only for RS)

Supported providers:
- RS: Ministry of Finance eFaktura

#**Setup**
________________________________________
**Export format configuration**

Configuration for export of invoices according to the UBL 2.1 standard is available. In the case of standard changes, the configuration needs to be adjusted.
1.	Open ****Workspaces** > Electronic reporting > Reporting configurations**.
2.	Choose Exchange > Load XML file on any configuration. Based on file content, it will automatically upload to the correct configuration.
3.	Before uploading, check the latest version of these files with the developer. Click "Browse" and choose the configuration files (be sure to upload the "Customer invoice model (AD)" first because the following ones are dependent on it). After the file has loaded, click OK to upload it to configuration.
4.	First, search for configuration "Customer invoice model" and expand it to find "Customer invoice model (AD)". Import the latest configuration. When done, "Customer invoice model mapping (AD)" imports automatically. All the remaining configurations need to be imported in the following order:
- Prepayment invoice (RS),
- Prepayment Credit Note (RS),
- Project invoice (RS),
- Project Credit Note (RS),
- Sales invoice (RS),
- Sales Credit Note (RS)


**Electronic invoice parameters**
1.	Open **Accounts receivable > Setup > Serbia > E-Invoices > Electronic invoice parameters.**
2.	General eInvoice parameters are set up under the tab "General", such as:
- **Automatic sending of eInvoices**: enable to download eInvoice after XML is created automatically
- **Default unit of measure**: Default unit of measurement for eInvoice if a value is empty on the source entity
- **Download eInvoice as archive**: with this function ZIP file will be generated with eInvoice files (invoice and customized visualization). **Important**: visualization of the document is not part of this localized feature and needs to be implemented during project implementation).
- **Electronic signature**:
1. **Mandatory**: created eInvoices need to be signed with an electronic signature using an appropriate valid certificate.
1. **Optional**: if a valid certificate is available, eInvoices are automatically signed if "Automatic electronic signing of eInvoice" is enabled. Otherwise, the user manually signs eInvoice in the registry. EInvoice can also be sent without a signature.
1. **Disabled**: eInvoice can be sent without an electronic signature.

 - **Automatic electronic signing of eInvoices**: If set to Yes, eInvoice will be automatically signed. If the Electronic signature option Disabled is chosen, this parameter is disabled. (Not yet supported for Serbian localization)
3.	In the "**Profile**" section, create a Profile ID (B2G, B2B) and choose adequate Electronic reporting configurations:
- for Sales and Free text invoices: "Sales Invoice (RS)",
- for Sales and Free text credit notes: "Sales Credit Note (RS)",
- for Project invoices: "Project Invoice (RS)",
- for Project credit note: "Project Credit Note (RS)"
- For Prepayment invoice: "Prepayment Invoice (RS)"
- For Prepayment credit note: "Prepayment Credit Note (RS)".
4.	The "Number sequence" section defines the number sequence code (Continuous is mandatory) for the eInvoice unique filename.

**Customer setup**
1.	Open **Accounts receivable > Customers > All Customers**.
2.	Tick the **eInvoice** option to Yes.
3.	Define "**Profile ID**" from eInvoice parameters in the tab Invoice and delivery on the customer.
4.	Enter **JMBG** for the customer (Person) - Information is needed when eInvoice is generated.
5.	Enter **JBKJS** for the customer (Organization) who is using public services – Information is needed when eInvoice is generated.
6.	Define **primary contact** for the customer, which will be used for eInvoice.

**Legal entity setup**
1. Open **Organization administration > Organizations > Legal entities**.
1. Under tab Addresses, the primary address for the legal entity needs to be entered
1. Under tab Bank account information, the primary bank account needs to be entered
1. Under tab Contact information, the primary contact needs to be entered
1. If the legal entity is the public institution, the **JBKJS** needs to be defined under the Serbia section of the Registration numbers tab
1. If the legal entity is a person, the **JMBG** needs to be defined under the Serbia section of the Registration numbers tab
1. If the legal entity is registered for tax, the Tax registration identifier needs to be VAT under the Serbia section of the Registration numbers tab; otherwise, it should be NO-VAT

**Unit of measure setup**
1.	Open **Organization administration > Setup > Units > Units.**
2.	Select unit of measure and open External codes
3.	Under tab Overview, enter code eRacun and enable option Standard code
4.	Under tab Value, enter the code used for eInvoices for the selected unit of measure (aligned with UBL 2.1)

**VAT category**
1.	Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2.	Select Sales tax code and under tab Be-terna localization/EINVOICE/VAT Category choose the appropriate category (S-standard rate, Z-zero rate, E-exempt from VAT, AE-VAT reverse charge, G-exempt export, O-services outside scope of VAT)

#**eInvoice registry**
________________________________________
**Electronic customer invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic customer invoices.**
2.	Posting sales or free text invoices for customers with Profile ID automatically generates eInvoice.
3.	Created eInvoice can be found in the customer eInvoices registry with " **New** " status.
4.	**Create an XML** function that creates the XML version of the invoice. The XML file is created and stored in the "Outgoing XML" field in the Details tab. Here, more information about eInvoice is displayed, including a unique file name, details about the user, and created date.
5.	Status is changed to "**Created**". eInvoice unique file name is generated as defined in the number sequence.
6.	After XML has been created, the button "**Send**" is enabled. By clicking the button, the eInvoice status changes to "Sent". An XML version of the eInvoice is downloaded at the same time.
7.	**Multiple selections** are also enabled for actions. Mark the eInvoices with a checkmark and select the appropriate action (Create XML, Send).
8.	**Export** - The XML version of eInvoice is exported (eInvoice status remains unchanged) on a user's computer.
Manually changing status to higher status is not allowed.
Export of eInvoice before the creation of XML (e.g. status "New" or "Not ready") is not allowed.

**Electronic project invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic project invoices.**
2.	Posting invoice for customers with Profile ID automatically generates eInvoice.
3.	Created eInvoice can be found in the project eInvoices registry with " New " status.
Project eInvoices are subject to the same procedures and actions as FTIs or Sales invoices.

**Electronic prepayment invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic prepayment invoices**.
2.	Posting invoice for customers with Profile ID automatically generates eInvoice.
3.	Created eInvoice can be found in the prepayment eInvoices registry with " New " status.
Prepayment eInvoices are subject to the same procedures and actions as FTIs or Sales invoices.

**Subsequent creation of eInvoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic customer/project invoices >** button “Select”.
2.	EInvoices can be subsequently generated according to selected filters for already posted invoices or invoices deleted from the eInvoice registry for the customer with adequate Profile ID. Navigate to the button "Select" and define the Criteria for the subsequent creation of eInvoices.
3.	After confirming, subsequent eInvoices are created with a "Not Ready" status.
Proceed with the same procedures and actions as described in the chapters above.

