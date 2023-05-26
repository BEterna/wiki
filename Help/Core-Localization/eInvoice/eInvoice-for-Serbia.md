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
4.	First, search for the configuration "Customer invoice model" and expand it to find "Customer invoice model (AD)". Import the latest configuration. When done, "Customer invoice model mapping (AD)" imports automatically. All the remaining configurations need to be imported in the following order:
- Prepayment invoice (RS),
- Prepayment Credit Note (RS),
- Project invoice (RS),
- Project Credit Note (RS),
- Sales invoice (RS),
- Sales Credit Note (RS)


**Electronic invoice parameters**
1.	Open **Accounts receivable > Setup > Serbia > E-Invoices > Electronic invoice parameters.**
2.	General eInvoice parameters are set up under the tab "General", such as:
- **Automatic sending of eInvoices**: Enable for downloading eInvoice after XML is created automatically and changing the status of the eInvoice to Sent.
- **Default unit of measure**: Default unit of measurement for eInvoice if a value is empty on the source entity.
- **Default unit of measure for prepayments**: Default unit of measurement for eInvoice prepayments if a value is empty on the source entity. It it mandatory to set this field to H87.
- **Download eInvoice as archive**: with this function ZIP file will be generated with eInvoice files (invoice and customized visualization). **Important**: visualization of the document is not part of this localized feature and needs to be implemented during project implementation).
- **Electronic signature**:
1. **Mandatory**: eInvoices must be signed with an electronic signature using an appropriate valid certificate.
1. **Optional**: if a valid certificate is available, eInvoices are automatically signed if "Automatic electronic signing of eInvoice" is enabled. Otherwise, the user manually signs eInvoice in the registry. eInvoice can also be sent without a signature.
1. **Disabled**: eInvoice can be sent without an electronic signature.

 - **Automatic electronic signing of eInvoices**: If set to Yes, eInvoice will be automatically signed. If the Electronic signature option Disabled is chosen, this parameter is disabled. (Not yet supported for Serbian localization)
3.	In the "**Profile**" section, create a Profile ID (B2G, B2B) and choose adequate Electronic reporting configurations:
- for Sales and Free text invoices: "Sales Invoice (RS)",
- for Sales and Free text credit notes: "Sales Credit Note (RS)",
- for Project invoices: "Project Invoice (RS)",
- for Project credit note: "Project Credit Note (RS)"
- For Prepayment invoice: "Prepayment Invoice (RS)"
- For Prepayment credit note: "Prepayment Credit Note (RS)".
4.	**Number sequence** section defines the number sequence code (Continuous is mandatory) for the eInvoice unique filename.

**Customer setup**
1.	Open **Accounts receivable > Customers > All Customers**.
2.	Enter the **Tax exempt number** (PIB) for the customer, the field is mandatory.
3.	Enter the **RegistrationID** (matični broj) for the customer in the field RegistrationID. The registration type must be linked with Registration category **Company registration number (AD)** and **SRB** country code.
4.	Enter the **RegistrationID** (GLN - global location number) for each customer address in the field RegistrationID. The registration type must be linked with Registration category **Branch ID** and **SRB** country code.
5.	Tick the **eInvoice attachment** option to Yes to use attachments for eInvoice documents.
6.	Define "**Profile ID**" from eInvoice parameters in the tab Invoice and delivery on the customer.
7.	Define **Invoice subtypes** in the customer table, values ID, and description that will be part of the Buyer reference in the XML file.
8.	Enter **JMBG** for the customer (Person) - Information is needed when eInvoice is generated.
9.	Enter **JBKJS** for the customer (Organization) who is using public services in the format **JBKJS:#####** (5-digit number) – Information is needed when eInvoice is generated.
10.	Define **Primary contact** for the customer, which will be used for eInvoice.

**Legal entity setup**
1. Open **Organization administration > Organizations > Legal entities**.
1. Under tab Addresses, the primary address for the legal entity needs to be entered
3.	Enter the **RegistrationID** (matični broj) for the Legal entity in the field RegistrationID. The registration type must be linked with Registration category **Company registration number (AD)** and **SRB** country code.
4.	Enter the **RegistrationID** (GLN - global location number) for each Legal entity address in the field RegistrationID. The registration type must be linked with Registration category **Branch ID** and **SRB** country code.
1. Under the tab Bank account information, the primary bank account needs to be entered
1. Under the tab Contact information, the primary contact needs to be entered
1. If the legal entity is the public institution, the **JBKJS** needs to be defined under the Serbia section of the Registration numbers tab
1. If the legal entity is a person, the **JMBG** needs to be defined under the Serbia section of the Registration numbers tab
1. If the legal entity is registered for tax, the Tax registration identifier needs to be VAT under the Serbia section of the Registration numbers tab; otherwise, it should be NO-VAT

**Unit of measure setup**
1.	Open **Organization administration > Setup > Units > Units.**
2.	Select a unit of measure and open External codes
3.	Under the tab Overview, enter code eRacun and enable the option Standard code
4.	Under tab Value, enter the code used for eInvoices for the selected unit of measure (aligned with [UBL 2.1](https://www.truugo.com/ubl/2.1/cl_unitofmeasure/))

**VAT category**
1.	Open **Tax > Indirect taxes > Sales tax > Sales tax codes**.
2.	Select Sales tax code and under tab **Be-terna localization > EINVOICE > VAT Category** choose the appropriate category (S-standard rate, Z-zero rate, E-exempt from VAT, AE-VAT reverse charge, G-exempt export, O-services outside the scope of VAT, R-Exempt from VAT, OE- services outside the scope of VAT2, SS- special VAT cases, N-anull)

**Sales tax-exempt codes**
1.	Open **Tax > Setup > Sales tax > Sales tax exempt codes**
2.	Create exempt codes according to a specific article of the VAT law in Serbia. In the column Exempt code (eInvoice), enter the article of the VAT law in format **PDV-RS-##-#-#** (example: PDV-RS-25-2-2 or PDV-RS-11-1-1)
3.	For each sales tax exempt code in the Translation option, enter the exact quote of the article in Serbian language (example: "Poresko oslobođenje bez prava na odbitak prethodnog poreza za promet zemljišta, kao i na davanje u zakup tog zemljišta")
4.	Use the Exempt checkbox in the Sales tax group set up on the Sales tax codes and choose the adequate Exempt code. For each exempt case, a new Sales tax code is needed

**Attachments**
1.	Open **Accounts receivable > Setup > Forms > Form setup**
2.	Under the Invoice/Free text invoice tab, set **Include document on sheet** to Header or All
3.	Open **Organization administration > Document management > Document management parameters** and under the General tab set **Use active document table** to "Yes
4.	Open **Organization administration > Document management > Active document tables** and add Sales order, Customer invoice journal, and Customer free text invoice with "Always enabled"
5.	Create a document and add the attachment to the header. Only header attachments with an **External** restriction will be automatically transferred to eInvoice documents. Note that the file size must not exceed 3MB.

#**eInvoice registry**
________________________________________
**Electronic customer invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic customer invoices.**
2.	Posting sales or free text invoices for customers with Profile ID will automatically generate eInvoice.
3.	Created eInvoice can be found in the customer eInvoices registry with "**New**" status.
4.	**Create an XML** function that creates the XML version of the invoice. The XML file is created and stored in the "Outgoing XML" field in the Details tab. Here, more information about eInvoice is displayed, including a unique file name, details about the user, and created date.
5.	Status is changed to "**Created**". eInvoice unique file name is generated as defined in the number sequence.
6.	After XML has been created, the button "**Send**" is enabled. By clicking the button, the eInvoice status changes to "Sent". An XML version of the eInvoice is downloaded at the same time.
7.	**Multiple selections** are also enabled for actions. Mark the eInvoices with a checkmark and select the appropriate action (Create XML, Send).
8.	**Export** - The XML version of eInvoice is exported (eInvoice status remains unchanged) on a user's computer.
Manually changing status to higher status is not allowed.
Export of eInvoice before the creation of XML (e.g., status "New" or "Not ready") is not allowed.


**Electronic project invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic project invoices.**
2.	Posting invoice for customers with Profile ID automatically generates eInvoice.
3.	Created eInvoice can be found in the project eInvoices registry with "New" status.
Project eInvoices are subject to the same procedures and actions as FTIs or Sales invoices.

**Electronic prepayment invoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic prepayment invoices**.
2.	Posting invoice for customers with Profile ID automatically generates eInvoice.
3.	Created eInvoice can be found in the prepayment eInvoices registry with "New" status.
Prepayment eInvoices are subject to the same procedures and actions as FTIs or Sales invoices.

**Additional fields – eInvoice documents**
1.	The period fields (**Start date and End date**) are added to the Free Text invoice, Project Invoice, Sales Order, and Posting Invoice Headers. These fields are mandatory for posting Credit notes and Debit notes if Document reference is not applied.
2.	If the user marks a Credit note with an Invoice using Settle transactions, **Document reference** and **Issue date** of the original Invoice fields will be applied in the XML file. 
3.	The **Debit note** checkbox is added to Free text invoices, Project invoices, Sales orders, and Posting Invoice Headers.
4.	The **Customer reference** field is intended for ContractDocumentReference in the XML file. The data can be filled during Sales agreement creation and past on to the Sales order and Invoice or manually added. Customer reference on the Project contract can be added through Funding sources > Details and transferred to the Project invoice. Customer reference on the Prepayment can be added through the General tab.
5.	The **Customer requisition** and **Customer requisition date** fields are intended for OrderReference in the XML file. The data can be filled during the Release order from the Sales agreement and past on to the Invoice or manually added. Customer requisition on the Project contract can be added through Funding sources/Details and transferred to the Project Invoice. Customer requisition on the Prepayment can be added through the General tab.
3.	The **Bar codes** on the Items are added to the XML tag StandardItemIdentification.
3.	The **External item numbers** on the Items are added to the XML tag SellersItemIdentification.
3.	The **Packing slip number** and **Packing slip date**, if exists, are added to the XML tag DespatchDocumentReference.
3.	The **Packing slip return number** and **Packing slip return date**, if exists, are added to the XML tag DespatchDocumentReference.

**Subsequent creation of eInvoices**
1.	Open **Accounts receivable > Invoices > E-Invoices > Electronic customer/project/prepayment invoices >** button “Select”.
2.	EInvoices can be subsequently generated according to selected filters for already posted invoices or invoices deleted from the eInvoice registry for the customer with an adequate Profile ID. Navigate to the button "Select" and define the Criteria for the subsequent creation of eInvoices.
3.	After confirming, subsequent eInvoices are created with a "Not Ready" status.
Proceed with the same procedures and actions as described in the chapters above.


#**Test cases**
________________________________________
1. Standard discounts can be used on Invoices and are calculated to fit eFaktura portal logic by using standard fields (Quantity, Unit price, Discount, Discount percent, Total discount) in the XML files. Check [**Test scenarios for Discounts**](/.attachments/Test-scenarios-Discounts-8fafc905-8abd-4f20-b4cd-1057cddbdfce.zip)

2. Prepayment invoices must be created through Be-terna localization using Prepayment journals for the correct document type to be used in the XML file. Check [**Test scenarios for Prepayments**](/.attachments/Test-scenarios-Prepayments-a4d3e4f5-24bc-450a-b877-d0805590a1e5.zip)
3. Settlement between prepayment and final invoices must be created to decrease the VAT amounts and correct data to be added to the XML file. Check 
4. Add notes or attachments to the Sales order, Sales order invoice, FreeText Invoice, Project invoice. Check 