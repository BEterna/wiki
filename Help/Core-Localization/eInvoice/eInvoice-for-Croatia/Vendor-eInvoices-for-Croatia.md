# Vendor eInvoices for Croatia

eInovices can be imported and processed into the following document types: 
- Pending vendor invoice / Credit note

Supported providers: 
- CRO: Financial Agency (FINA)

## **Prerequisites**
---
Before starting the setup, ensure you have the following:
- Valid certificate: A valid digital certificate with a password is required. This certificate is crucial for accessing the service provider's endpoint and retrieve eInvoice data.
- FINA account: Ensure you have an account on the FINA platform. This account should have the necessary roles assigned to allow you to send and receive eInvoices.


## **Setup**
---

### **Import format configuration**
Configuration for import of invoices is available. In the case of standard changes, the configuration needs to be adjusted.
1.	Open **Workspaces > Electronic reporting > Reporting configurations**.
2.	Choose Exchange -> Load XML file on any configuration. Based on file content it will automatically upload to correct configuration.
3.	Before upload, check the latest version of these files with the developer. Click “Browse” and choose the configuration files (be sure to upload the “Vendor invoice model AD“ first because the following ones are dependent on it). After the file has loaded, click OK to upload it to configuration.
4.	First, search for configuration “Vendor invoice model” and expand it to find “Vendor invoice model AD “. Import the latest configuration. When done, “Vendor invoice model mapping AD” imports automatically. All the remaining configurations need to be imported in the following order:
    -  Purchase credit note (HR)
    - Purchase invoice (HR)


### **Configure B2B electronic document providers**
This configuration is mandatory when an automatic process floe of vendor eInvoices is desired.

- Navigate to **Accounts receivable > Setup > Croatia > E-Invoices > Configure B2B electronic document providers**.
- Define a new provider: enter the name and select a desired provider from the drop down list (FINA).
- Set up the key values:
    - Click the _Reset values_ button to add the required key values.
    - Enter the following values:
      - _endpointURL_: url of connection with web service
      - _keyVaultCertificateName_: name of the certificate
      - _taxNumber_: company’s tax number

### **Configure digital certificate**
The digital certificate is essential for accessing the service provider's endpoint and retrieve eInvoice data.
- Access key vault parameters:
  - Go to System administration > Setup > Key vault parameters.
- Create a new parameter and set up the following key values (obtained from Azure):
  - Key Vault URL
  - Key Vault client
  - Key Vault secret key
- Set up secrets by accessing the Secrets tab and entering:
  - Name 
  - Secret 
  - Secret type (certificate, manual, key).

### **Electronic invoice parameters**
1. Open **Accounts receivable > Setup > Croatia > E-Invoices > Electronic invoice parameters**.
2. General eInvoice parameters are set up under tab “General” and are the same as for the [Customer eInvoice process](/Help/Core-Localization/eInvoice/eInvoice-for-Croatia/Customer-eInvoices-for-Croatia).
3. In the “Profile” section create Profile ID, select the Electronic document provider and choose adequate Electronic reporting configurations: 
   - for Purchase invoices: “Purchase invoice (HR)”,
   - for Purchase credit notes: “Purchase credit note (HR)”.


## **Vendor eInvoice registry**
---
Vendor eInvoice data is stored in Electronic vendor documents, which can be found in **Accounts payable > Invoices > E-invoices > Electronic vendor documents**. These documents can be created automatically by pulling eInvoice data from a service provider or can be created manually. In any case a unique _External ID_ is required.


### **Automatic creation of eInvoices**

1. Navigate to **Accounts payable > Invoices > E-invoices > Electronic vendor documents**.
2. Click on **Get incoming documents**
3. Here, also batch processing of documents can be set. This means that you can set up processing at any given time of the day with recurrence. 
4. By clicking **OK** the system will import all vendor documents from selected provider.
5. By clicking on Export button you can export the invoice in XML version

### **Manual creation of eInvoices**
1. Open **Accounts payable > Invoices > E-invoices > Electronic vendor documents**
2. Create **New** record and navigate to **Details** tab to open a form where you can enter the XML file manually.
3. Fill in the following details:
   - External ID
   - Electronic document profile
   - Provider
   - Invoice date
   - Incoming XML content
4. By clicking **Process** you will import the XML file based on which the system will create a pending vendor invoice and populate it with all the relevant data from XML file.
5. By clicking on Export button you can export the invoice in XML version

### **Processing vendor eInvoices**
The steps for invoices that contain purchase orders with services are already described under **Automatic creation of eInvoices.** The main difference between purchase order with services and purchase orders with inventory tracked items is that purchase orders with items must be linked to a purchase order that has a posted product receipt.

The reference to which purchase order is invoice connected is added in XML file under OrderReference field. The ID of the purchase order needs to be adjusted to the actual ID within the system in order  to have a successful match. If there is no link to purchase order for stocked item at the time of processing, the system will throw an error.

If the user, while processing makes a mistake and wants to process the file again, the processed document should be deleted and then imported and processed again.

###Setup for External item number
1. Go to **Product information management > Products > Released products**
2. Choose an item that you want to set up
3. Under **Purchase tab > Related information** click on External item description
4. Here you should add **vendor relation** and **external item number**- that is the supplier's identification number for the items included in the order. Based on this setup the system will match  vendors with items.
5. The connection between an item and vendor can also be made from vendor's side by going to **Accounts payable > Vendors > All vendors**. Choose a relevant vendor and go to **Procurement tab > Set up > External item description**. Here you can connect all relevant items to the chosen vendor.

## **Test cases**
---
Under construction