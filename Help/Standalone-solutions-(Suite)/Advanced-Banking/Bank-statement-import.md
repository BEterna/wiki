# Import bank statement

This topic includes information about two options for bank statement import: 
- Bank statement transformations, used for mapping D365 fields with the information from bank statements (**Data management** - Option 1).
- **Electronic reporting formats** for bank statement import (Option 2). 

The following bank statement formats are supported as part of this package: 

   - Slovenia – ISO 20022 (HalcomSI)
   - Croatia – FINA
   - Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using the standard D365 bank reconciliation or additional bank statement processing features this package offers.

## **Setup**

### **Setup of Data management (Option 1)**
---

### **Data management setup**

#### Create Source data format

<br>Open System administration > Workspaces > Data management > Configure data source.

It is necessary to create a new Source data format. Setup depends on the type of import file. 

Example of XML file import setup:  

|**Source name**| **Operations** | 
|--|--|
|**Source name** |XML-Element  |
|**Description**  |XML Element  |
|**Type**  |File  |
|**Default extension**  |XML  |
|**File format**  |XML |
|**XML style**  |Element  |
|**Root document**  |Document  |
|**Language locale**  |*pick a local language that you want to use  |
|**Time zone preference**  | Company or Manual |


 
### **Bank statement import setup** 
_NOTE: This option requires a valid transformation for a specific bank statement format. Although sample transformations for formats listed below are provided in this document, they must be considered only as samples that may require additional adaptation according to data specifics used by a Bank in their bank statements preparation procedure._

## Set up the import of HalcomSI (ISO20022) bank statements

First, you must define the bank statement format processing group for HalcomSI bank statements using the data entity framework.
1.	Go to **Workspaces** > **Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_SI**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. Select **BankStatementDocumentEntity** in the list, then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Halcom_SI.xslt** file that you saved earlier.
11.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://erp-releases.be-terna.com/b/adaxreleases?path=adsuite%2f10.0%2fAdSuiteBankStmt-Transformations%2f). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for HalcomSI bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **HalcomSI**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group you defined earlier, such as **BankStatementImport_SI**.
6.	Enable the XML file option.



##Set up the import of FINA (ISO20022) bank statements

First, you must define the bank statement format processing group for FINA bank statements using the data entity framework.

1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_HR**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click Upload, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. Select **BankStatementDocumentEntity** in the list, then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **FINA_TxtToXML_HR.xslt** file that you saved earlier.
11.	For sequence number 2, click **Upload file**, and select the **FINA_XMLToRecon_HR.xslt** file that you saved earlier.
12.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://erp-releases.be-terna.com/b/adaxreleases?path=adsuite%2f10.0%2fAdSuiteBankStmt-Transformations%2f). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for FINA bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **FINA**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group you defined earlier, such as **BankStatementImport_HR**.
6.	Disable XML file option; enter File type = txt




##Set up the import of HalcomRS bank statements

First, you must define the bank statement format processing group for HalcomRS bank statements using the data entity framework.
1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_RS**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. Select **BankStatementDocumentEntity** in the list, then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Halcom_TxtToXML_RS.xslt** file that you saved earlier.
11.	For sequence number 2, click **Upload** file, and select the **Halcom_XMLToRecon_RS.xslt** file that you saved earlier.
12.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://erp-releases.be-terna.com/b/adaxreleases?path=adsuite%2f10.0%2fAdSuiteBankStmt-Transformations%2f). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for HalcomRS bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **HalcomRS**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group you defined earlier, such as **BankStatementImport_RS**.
6.	Disable XML file option; enter File type = txt
7.	Enable Halcom RS option 



An additional column, “Halcom RS” is available, which is **specific for Serbian bank statements import**. Halcom_RS is special because it generates two files for one bank statement imported as a .zip file. Halcom_RS has a checkmark in the “Halcom RS” field for that purpose.

##Set up the import of AssecoRS (Pexim) bank statements

First, you must define the bank statement format processing group for AssecoRS bank statements using the data entity framework.
1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_Asseco**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. Select **BankStatementDocumentEntity** in the list, then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Asseco_RS.xslt** file that you saved earlier.
11.	Click **Apply transforms**

Transformations for the supported formats can be found on [**this link**](https://erp-releases.be-terna.com/b/adaxreleases?path=adsuite%2f10.0%2fAdSuiteBankStmt-Transformations%2f). 

After the format processing group is set up, the next step is to define the **bank statement format** rules for AssecoRS bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **AssecoRS**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group you defined earlier, such as **BankStatementImport_Asseco**.
6.	Enable the XML file option.


### **Setup of Electronic reporting formats** 
---

### Import Electronic reporting configurations (Option 2)
<br>

1. Go to **Organization administration > Workspaces > Electronic reporting**
2. Open **Be-terna repository**
3. Click **Add** and **create** new configuration repository by choosing **BE-terna Suite (Bank Statements)**
4. Select the repository created in the previous bullet and **Open**. 
5. **Import** all **Bank statement models**

Imported transformation files are then displayed in Electronic reporting configurations as: 
- **Camt.053 Format (AD)** for bank statements 
- **Camt.054 Format (AD)** for bank debit credit notifications
- **Halcom (RS)** for bank statements


### Bank statement format setup
#### Camt.053 and Camt.054 formats
1. Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**
2. **Add** new **Bank statement import configuration**
3. Specify a **statement format**, such as **Camt.053** or **Camt.054**
4. Enter a **name for the format**.
5. Choose the file type **XML** 
6. Select **Import configuration format** from the list of ER configurations

#### Halcom RS formats
1. Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**
2. **Add** new **Bank statement import configuration**
3. Specify a **statement format**, such as **Halcom RS**.
4. Enter a **name for the format**.
5. Choose the file type **TXT** for Halcom RS 
6. Check the **Combine text files** because Halcom RS has two files under one .zip file
7. In the **Matches**, put the matching rule on the file name. For Halcom RS, use `(.*)_cov\.txt:(.*)\.txt`
8. Mark **Generic Electronic import format field** 
9. Select **Import configuration format** from the list of ER configurations

### Bank account setup
---

Import is enabled only for bank accounts with a checkmark in the “Advanced bank reconciliation” field.
 
Once this option is enabled on a bank account, it cannot be reversed (the button turns inactive, grey). The optional setup is the definition of Statement format. 

### Configuration of import sources
---

Configuring different sources (e.g., SharePoint) for importing bank debit credit notifications and statements to D365FO is possible. Configuration of SharePoint is optional – it can also be entered manually or imported from a PC.

To **configure SharePoint** as a statement/notification source: 
1. Go to **Organization administration > Document management > Document types**.
2. Create Document type **Inbox** for each file type (bank statement or/and notification)
2. Create Document type **Completed** for each file type (bank statement or/and notification)
2. Create Document type **Error** for each file type (bank statement or/and notification)
  
![image.png](/.attachments/image-f7e7cef3-851b-48e8-98ab-b18e70b83e63.png)

The same number of folders should be created on the **connecting SharePoint**. Each newly created Document type must then be **mapped** with the **related SharePoint folder**. To do that, enter the URL address of each SharePoint folder in the **Sharepoint Address field** of the Document type setup.

Finally, **mapping of Electronic reporting sources** with **Document types** needs to be configured. 
1. Go to **Organization administration > Electronic reporting > Electronic reporting source**. 
2. Create a **new source** for each file type (one for bank statements and one for notifications). 
3. In field “**Format**” configure **Camt.054 Format (AD)** as bank notification and **Camt.053 Format (AD)** as bank statements source.
4. On each newly created Electronic reporting source **add a new File source**, and enter the adequate name (bank statement or notification)
5. Click on Settings  
6. Enable **SharePoint** and connect **Document types** with adequate **document categories** 

![image.png](/.attachments/image-9111f5aa-8841-4d1d-b72a-9dbad06ff1c2.png)

## **Import Bank statement**
---

Bank Statement is imported in **Cash and Bank management > Bank statement reconciliation > Bank statements > Import statement**.

At import, the system checks for a **unique combination** of bank account number, SWIFT code, routing number, IBAN, and currency between bank account records in D365FO and information from the statement. Therefore, importing multiple bank account records in D365FO with the same account number but different currencies is possible.

_NOTE: No validation exists to avoid duplicated bank statements in D365FO - the same bank statement can be imported several times._

If adequate setup exists, bank statements can also be imported directly from the configured sources (SharePoint) through **Cash and bank management > Periodic tasks > Bank statements import (ER)**.


_NOTE: For Serbia, bank statement files should be zipped before import._ 
 
1. Set **Import statements for multiple bank accounts in all legal entities** to yes if you want to import statements for multiple accounts simultaneously. NOTE: importing statements to multiple bank accounts in D365FO with the same account number is not allowed. 
1. Select **Bank account** from list of bank accounts.
1. Select **Statement format**. If the format is already defined on the Bank account, this field is populated automatically after choosing the Bank account. During import, the system will recognize the bank account based on IBAN if it is not defined in the parameters.
1. Click **Upload** 
1. Click **OK**

A Bank Statement is imported when shown in the list of bank statements. After import, the bank statement can be validated and reconciled. 

_NOTE: Sometimes bank statements also include lines with a date outside the defined bank statement period. To avoid failure of bank statement validation, a new functionality that allows users to change the booking date on selected lines that were imported is available in the Bank statement detail form (new button Change booking date)._ 


Check **[Test Scenario](/Help/Extended-Localization/Bank-package-features/Bank-statement-import.xlsx)** for Slovenian bank statement import.
 
