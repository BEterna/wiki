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
Under construction

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
Vendor eInvoice data is stored in Electronic vendor documents. which can be found in **Accounts payable > Invoices > E-invoices > Electronic vendor documents**. These documents can be pulled from a service provider or can be created manually. In any case a unique 

### **Automatic import of eInvoices**
Under construction

### **Manual import of eInvoices**
Under construction

### **Processing vendor eInvoices**
Under construction


## **Test cases**
---
Under construction