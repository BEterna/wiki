# eInvoices for Croatia 

The purpose of this feature is to enable the Invoice export in the prescribed electronic form (UBL 2.1 standard). The export file can be generated for multiple invoices. Web service communication is not part of this feature. 

## **Setup**
---

### **Export format configuration**

Configuration for export of invoices according to the UBL 2.1 standard is available. In the case of standard changes, the configuration needs to be adjusted. 

1. Open **Workspaces > Electronic reporting > Reporting configurations**.
2. Choose Exchange -> Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
3. Before upload, check the latest version of these files with the developer. 
Click “Browse” and choose the configuration files (be sure to upload the “Customer invoice model AdLoc“ first because the following ones are dependent on it). After the file has loaded, click OK to upload it to configuration.
4. First, search for configuration “Customer invoice model” and expand it to find “Customer invoice model AdLoc “. Import the latest configuration. When done, “Customer invoice model mapping AdLoc” imports automatically. All the remaining configurations need to be imported in the following order:
   - Project Credit Note HR,
   - Project invoice HR,
   - Sales Credit Note HR,
   - Sales invoice HR.
  
### **Business processes setup**
1. To define possible business processes open **Accounts receivable > Setup > Croatia > E-Invoices > Business processes**.
1. Create needed business processes:
   - **Business process id**: Define the exact code used to identify the type of invoice
   - **Description**: Enter a description of a business process 
   - **Enabled for invoice**: Set yes if the business process should be used for invoices
   - **Enabled for credit note**: Set yes if the business process should be used for credit notes

Please note that at least two business processes need to be created, one for invoices and one for credit notes. If all business processes need to be open, use the following Excel as help for the setup [Business processes_ProfileID.xlsx](/.attachments/Business%20processes_ProfileID-0c904e70-3ffa-4b82-b36a-160d328b9a65.xlsx)


### **Electronic invoice parameters**

1. Open **Accounts receivable > Setup > Croatia > E-Invoices > Electronic invoice parameters**.
2. General eInvoice parameters are set up under tab “General”, such as:
   - **Automatic sending of eInvoices**: enable to automatically download eInvoice after XML is created
   - **Default unit of measure**: Default unit of measure for eInvoice if a value is empty on source entity 
   - **Default business process for invoices**: Define the default business process for the invoice that is commonly used for all customers. In the case that some customer use different business processes for invoices this can be defined directly on customer card.  
   - **Default business process for credit notes**: Define the default business process for the credit notes that is commonly used for all customers. In the case that some customer use different business processes for credit notes this can be defined directly on customer card. 
   - **Download eInvoice as archive**: with this function, ZIP file will be generated with eInvoice files (invoice and customized visualization). Important: visualization of the document is not part of this localized feature and needs to be implemented during project implementation).
   - **Memorandum information**
   - **Signature options** (Not yet supported for Croatian localization)
3. In the “Profile” section create Profile ID and choose adequate Electronic reporting configurations:
   - for Sales and Free text invoices: “Sales Invoice HR”,
   - for Sales and Free text credit notes: “Sales Credit Note HR”,
   - for Project invoices: “Project Invoice HR”,
   - For Project credit note: “Project Credit Note HR”. 
4.  In the „**Number sequence**“ section set number sequence which will be used for eInvoice export

For B2G purposes (UBL 2.1) one provider configuration is needed. In case of supporting additional standards, new providers would be added and configured. 
 
It is necessary to define eInvoice unique file name in the “Number sequences” section. 
 
### Certificate

Not yet supported for Croatian localization.

### **Customer setup**

1. Open **Accounts receivable > Customers > All Customers**.
1. Enable **eInvoice attachment** field if visualization for eInvoice needs to be included in XML
2. Define “**Profile ID**” from eInvoice parameters in the tab Invoice and delivery on the customer.
1. Define **Business unit** for the Order account if XML needs to include additional customer identification in the following examples:
   - If the Invoice account is different from the Order account and XML needs to have information about the business unit for the Order account
   - If the Order account is the same as the Invoice account but XML needs to have additional information about the business unit for the Order account
1. Define **Default business process for invoice** for cases where a customer uses a different business process for invoices than the one already defined on Electronic invoice parameters. In the case that some customers should use different business processes for different invoices this can be defined directly on a document.
1. Define **Default business process for credit note** for cases where a customer uses a different business process for credit notes than the one already defined on Electronic invoice parameters. In the case that some customers should use different business processes for different credit notes this can be defined directly on a document.
3. Enter **OIB** for the customer - Information is needed when eInvoice is generated.
   - on Invoice and delivery tab > field OIB or
   - on Registration ID's > OIB. Information is needed when eInvoice is generated.<br>  _Note: priorities described in [Additional identification numbers](/Help/Core-Localization/Company,-Customer-and-Vendor-identification-numbers/Additional-identification-numbers)_
4. Define **primary contact** for the customer:
   - Add new contact for the customer and define the primary email address which will be used for eInvoices
   - On the Sales demographics tab choose the defined contact for the customer
1. Define **address** for customer

### **Legal entity setup**
1.	Open **Organization administration > Organizations > Legal entities**.
2.	Under tab Addresses, the primary address for the legal entity needs to be entered
3.	Under tab Contact information, the primary email address needs to be entered
4.	Under tab Tax registration, field Tax registration number needs to be populated with OIB

### **Unit of measure setup**
1.	Open **Organization administration > Setup > Units > Units**.
2.	Select unit of measure and open External codes
3.	Under tab Overview, enter code eRacun and enable option Standard code
4.	Under tab Value, enter code used for eInvoices for the selected unit of measure (aligned with UN/ECE Recommendation 20)

**Posting invoices**
1. If **Reference to Agreement** needs to be used on eInvoice use field **Customer reference**. Customer reference field can be found on Sales order header or Free text invoice header. If project invoices are used, customer reference field should be entered on Project contract under Details on Funding sources.  
1. Define **Business unit** on invoice in the case that an invoice should have a specific business unit different from the default busniness unit defined on Electronic invoice parameters or the default business unit defined on the customer card.

## **eInvoice registry**
---

### Electronic customer invoices

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic customer invoices**.
2. Posting sales or free text invoices for customers with Profile ID automatically generates eInvoice. 
3. Created eInvoice can be found in customer eInvoices registry with status “New”. 
4. **Create an XML** function that creates the XML version of the invoice. No validation of the information from the customer/invoice is currently supported in terms of Croatian localization.
The XML file is created and stored in the field “Outgoing XML” in the Details tab. Here, more information about eInvoice is displayed, including a unique file name, details about the user and created date.
5. Status is changed to “**Created**”. eInvoice unique file name is generated as defined in the number sequence.
6. After XML has been created, the button “**Send**” is enabled. By clicking the button, eInvoice status changes to “Sent”. An XML version of the eInvoice is downloaded at the same time.
7. **Multiple selections** are also enabled for actions. Mark the eInvoices with a checkmark and select appropriate action (Create XML, Send).
 
Manually changing status to higher status is not allowed.
 
**The following functions are available**:
   - “Export” - XML version of eInvoice is exported (eInvoice status remains unchanged) and
   - “Send” (if function “Download eInvoice as an archive in Electronic invoice parameters is enabled), a ZIP file containing the XML version of the eInvoice is downloaded. eInvoice status changes to “Sent”.
 
Export of eInvoice before the creation of XML (e.g. status “New” or “Not ready”) is not allowed.
 

 
### **Electronic project invoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic project invoices**.
2. Posting invoice proposal for customers with Profile ID automatically generates eInvoice.
3. Created eInvoice can be found in the project eInvoices registry with status “New”. 

Project eInvoices are subject to the same procedures and actions as FTIs or Sales invoices.

### **Subsequent creation of eInvoices**

1. Open **Accounts receivable > Invoices > E-Invoices > Electronic customer/project invoices** > button “Select”.
2. EInvoices can be subsequently generated according to selected filters for already posted invoices or invoices deleted from eInvoice registry for the customer with adequate Profile ID. Navigate to button “Select” and define Criteria for the subsequent creation of eInvoices. 
3. After confirming, subsequent eInvoices are created with status “Not ready”.
 
Proceed with the same procedures and actions as described in the chapters above. 

## **Test cases**
---
#### Test cases for FTI and Sales invoice

Check **[Test Scenario](e-Invoices-HR.zip)**.
#### Test case for project invoice

Check **[Test Scenario](e-Invoices-HR.zip)**.


#### Test case 

Check **[Test Scenario](e-Invoices-HR.zip)**.