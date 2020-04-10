# Import bank statement

This topic includes information about the bank statement transformations, used for mapping D365 fields with the information from bank statements. Transformations for following bank statement formats are added as part of this package: 

   - Slovenia – ISO 20022 (HalcomSI)
   - Croatia – FINA
   - Serbia – Assecco (Pexim) and HalcomRS

After import, bank statements can be processed using standard D365 bank reconciliation feature or additional bank statement processing features that this package is offering.


## **Setup**
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
|**Default dextension**  |XML  |
|**File format**  |XML |
|**XML style**  |Element  |
|**Root document**  |Document  |
|**Language locale**  |*pick local language that you want to use  |
|**Time zone preference**  | Company or Manual |


 
### **Bank statement import setup** 

## Set up the import of HalcomSI (ISO20022) bank statements

First, you must define the bank statement format processing group for HalcomSI bank statements by using the data entity framework.
1.	Go to **Workspaces** > **Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_SI**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click **Upload**, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **Halcom_SI.xslt** file that you saved earlier.
11.	Click **Apply transforms**

After the format processing group is set up, the next step is to define the bank statement format rules for HalcomSI bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **HalcomSI**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_SI**.

##Set up the import of FINA (ISO20022) bank statements

First, you must define the bank statement format processing group for FINA bank statements by using the data entity framework.

1.	Go to **Workspaces > Data management**.
2.	Click **Import**.
3.	Enter a name for the format, such as **BankStatementImport_HR**.
4.	Set the **Source data format** field to **XML-Element**
5.	Set the **Entity name** field to **Bank statements**.
6.	To upload the import files, click Upload, and then browse to select the **[SampleBankCompositeEntity.xml](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)** file that you saved earlier.
7.	After the Bank statements entity is uploaded and the mapping is completed, click the **View map** action for the entity.
8.	The Bank statements entity is a composite entity that consists of four separate entities. In the list, select **BankStatementDocumentEntity**, and then click the **View map** action.
9.	On the **Transformations** tab, click **New**.
10.	For sequence number 1, click **Upload file**, and select the **FINA_TxtToXML_HR.xslt** file that you saved earlier.
11.	For sequence number 2, click **Upload file**, and select the **FINA_XMLToRecon_HR.xslt** file that you saved earlier.
12.	Click **Apply transforms**

After the format processing group is set up, the next step is to define the bank statement format rules for FINA bank statements.
1.	Go to **Cash and bank management > Setup > Advanced bank reconciliation setup > Bank statement format**.
2.	Click **New**.
3.	Specify a statement format, such as **FINA**.
4.	Enter a name for the format.
5.	Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_HR**.


Open System administration > Workspaces > Data management > Import

Generate separate import group for Each bank format. 
1. **Create new import project** and name it the way that it will give enough information about the content  (e.g. BankStatementImport_SI) 



1. In the Selected entities Area **add new entity** (New File):

|Field| Value |
|--|--|
|**Entity name**  | Bank statements |
| **Source data format** |Choose one of data sources, generated in the previous step e.g. XML-Element |
|**Use sample file**  |Yes  |
|**Default refresh type**  | Any of two options |
|**Upload data file**  | upload SampleBankCompositeEntity sample file located in AOT resources |

file sample: [**SampleBankCompositeEntity.xml**](/.attachments/SampleBankCompositeEntity-33b781da-249e-4e72-8896-9fe62b83ea6d.xml)

![image.png](/.attachments/image-b253b583-0da5-4da6-a950-4522f5efad9f.png)

3. After the Bank statements entity is uploaded and the mapping is completed,  **XSLT transformation** can be applied. 
   - Click the **View map action** for the entity.
   -  On the **Transformations** tab, click **New**.
   - For sequence number 1, click **Upload file**, and select the adequate transformation file. 
   - Click New (only if multiple transformations are used).
   - For sequence number 2, click **Upload file**, and select the adequate transformation file, etc. 
   - Click **Apply transforms**.

| **Format** | **Transformation** |
|--|--|
|**Halcom**  |Halcom_SI.xslt  | 
|**FINA**  | 1. FINA_TxtToXML_HR.xslt <br>2. FINA_XMLToRecon_HR.xslt | 
|**Asecco (Pexim)**  | Asseco_RS.xslt |
|**HalcomRS**  | 1. Halcom_TxtToXML_RS.xslt <br>2. Halcom_XMLToRecon_RS.xslt |


Transformations for the supported formats can be found on [this link](https://ad365o.visualstudio.com/AdSuite/_versionControl?path=%24%2FAdSuite%2FBankStatements%2FMain%2F10%2FMetadata%2FAdactaSuiteBankStatements%2FAdactaSuiteBankStatements%2FAxResource%2FResourceContent%2FData). 
 
After the format processing group is set up, the next step is to define the bank statement format rules for bank statements.
 
### **Bank statement format**

Open Cash and bank management > Setup > Advanced bank reconciliation > Bank statement format.

Enter all bank statement formats that will be used in the bank statement processing. Formats added by this package are listed at the beginning of this chapter. 

1. Click **New**.
1. Specify a statement format, such as **HalcomSI**.
1. Enter a name for the format.
1. Set the **Processing group** field to the group that you defined earlier, such as **BankStatementImport_SI**.
1. Select the **XML file** check box if XML format is used for upload. If not, live empty.


There is an additional column “Halcom RS” available, which is **specific for Serbian bank statements import**. Halcom_RS is special in a way that it generates two files for one bank statement which is then imported as .zip file. For that purpose, Halcom_RS has a checkmark in the field “Halcom RS”.

### Bank account setup

Import is enabled only for bank accounts that have a checkmark in field “Advanced bank reconciliation”.
 
Once this option is enabled on a bank account it cannot be reversed (button turns inactive, grey). The optional setup is the definition of Statement format. 

## **Import**
---

Bank Statement is imported in Cash and Bank management > Bank statement reconciliation > Bank statements > Import statement.

For Serbia, bank statement files should be zipped before import. 
 
1. Select **Bank account** from list of bank accounts.
1. Select **Statement format**. If the format is already defined on Bank account, this field is populated automatically after choosing Bank account. During import, the system will recognize bank account based on IBAN number if it is not defined in parameters.
1. Click **Upload** 
1. Click **OK**

Bank Statement is imported when it is shown in the list of bank statements. After import, the bank statement can be validated and reconciled. 


Check **[Test Scenario](Bank-statement-import.xlsx)** for Slovenian bank statement import.
 
