# BE-terna suite
[[_TOC_]]
___
###10.0.2024xx
|Suite|Description|Type|
|---|---|---|
|Advanced banking|Asseco (RS) ER format was updated to support both roots: stmtrlist and pmtnotification.|Bug fix|
___
###10.0.20240509.01
|Suite|Description|Type|
|---|---|---|
|Advanced banking|Due date on all lines in general journal is now related to the entered posting date and not to current system date.|Bug fix|
|Advance banking|Mismatch in presenting data in realized cash flow report when handling customer payment returns via GL accounts is fixed.| Bug fix|
|Dunning| Name for number sequence module was changed from Dunning (Adacta) to Dunning (BE-terna).|Updated feature|
___
###10.0.20240412.02
|Suite|Description|Type|
|---|---|---|
|Travel and expenses enhancements|Data entity TrvRequisitions_AdTrv extended with the possibility to manage Display default dimension value when creating Travel requisition through the data entity.|Updated feature|

___
###10.0.20240412.01
|Suite|Description|Type|
|---|---|---|
|Loan and deposits|Possibility to change due date on flow/action lines is enabled.|New feature|
|Vendor invoice lines import|Data entity for consumers is enabled to import new consumers. Also, new data entity AdEinvConsumerEntity is available in data management|Bug fix|
|Advanced banking|Bank statements import: New Camt.053 and Camt.054 ER format for CRO available according to new legislation requirements.|Updated feature|
|Advanced banking|Fixed issue with presenting data in the correct Debit or Credit column in realized cash flow report when handling customer payment returns via General ledger journals.|Bug fix|
|Investment management|Enabled updates for fields Project purpose, Start Date and End Date in Projects_AdIMI Data entity. The modification is a **breaking change** as affects the Projects_AdIMI staging table. To prevent disruptions after applying the change to the environment, the following steps are necessary:<li>Stop all jobs for Data management projects that use Projects_AdIMI Data entity.<li>Refresh the data entity list (as a result the staging table should be named as ProjectStagingV2_AdIMI).<li>Regenerate the mapping of the data entity (Modify target mapping).<li>Update all Data management projects that use Projects_AdIMI Data entity either by removing the old data entity for them or by deleting and recreating the Data managament project anew.<li>Recreate new jobs (and optional: delete old recurring jobs that were previously stopped).<li>Notify 3rd party system that consume data from Projects_AdIMI Data entity.|Bug fix|
|Fixed asset management|Prevented disposal document data update via data entity "AssetDisposal document lines per header" when disposal document in status Posted or Reversed.|Bug fix|

___
###10.0.20240409.01
|Suite|Description|Type|
|---|---|---|
|Reinvoicing|A checkbox was added to the vendor invoice journal and the pending vendor invoice to indicate if an invoice was reinvoiced. On both forms, a reinvoiced sales order button was added that shows all sales order lines that were reinvoiced with the selected vendor invoice.|New feature|

___
###10.0.20240314.01
|Suite|Description|Type|
|---|---|---|
|Investment management|Processing item requirements batch job extended with a new use case scenario supporting processing of item requirements that are created withing the same TransactionId|New Feature|
|Travel and Expenses enhancements|New data entity TrvRequisitions_AdTrv is available for importing Travel requisition headers.|New feature|

___
###10.0.20240306.01
|Suite|Description|Type|
|---|---|---|
|Loans and deposits|Fixed multiple posting of the same flow on received or given loan.|Bug fix|

___
###10.0.20240305.01
|Suite|Description|Type|
|---|---|---|
|Advanced banking|The features for automatic importing of Bank statements by using the periodic tasks: Bank statement import (ER), Bank debit credit notification import (ER) are deprecated and will retire on 31.5.2024. The standard import of Bank statements should be used instead.|Deprecated feature|
|Advanced banking|Bank statement import: New electronic format for Asseco RS (xml) is enabled for importing bank statements in Serbia.|New feature|
|Deferrals in Accounts Payable|Fixed case thet prevented using deferrals on a non-posted pending vendor invoice while also using standard prepayment functionality.|Bug fix|
|Public procurement|Enabling fields on lines when opening purchase agreement that has no related documents. Relevant fields are disabled only when the Purchase agreement related documents exist.|Bug fix|
|Investment management|Fix for posting generated shipments for direct consumption, when more than one shipment was created for the same item requirement and the same inventory dimensions and quantity data is defined on these shipments. Posting logic now also includes the correct Route ID.|Bug fix|

___
###10.0.20240125.01
|Suite|Description|Type|
|---|---|---|
|Asset insurance|Code review and best practice cleanup performed. These changes are internal and do not introduce any new features or alter existing functionality.|/|
|Advanced banking|Fixed bank statement proccesing when the option to have transactions unmarked by default is used. |Bug fix|
|Dunning process|Code review and best practice cleanup performed. These changes are internal and do not introduce any new features or alter existing functionality.|/|
|Investment management|Fixed issue when posting Item return documents of the type Cancel using items blocked for inventiry that prevented the return process to generate inventory transactions, but marked the returned document as posted nevertheless. |Bug fix|
|Investment management|New validation added in the batch job "Process item requirements" when generating shipments to a "terrain" type of warehouse (indirect consumption). The new functionality validates if a tranzit warehouse is defined and does not process item requirememnts where this validation fails.|New feature|
|Advanced product management| Fixed issue with registered technical characteristics for a selected item being deleted when an inventiry transaction for the same item is deleted. |Bug fix|

___
###10.0.20231219.01
|Suite|Description|Type|
|---|---|---|
|Deferrals|Enabled the option to run Posting deferrals batch job by using date range as a parameter. |New feature|
|Deferrals|Fixed missing security properties on Maintain deferrals duty.|Bug fix|
|Investment management|Fixed missing security properties on IM integration manager role.|Bug fix|
|Investment management|A new checkmark "Use project correction for negative quantity consumption" has been added to the project management and accounting parameters. When enabled, Process expense consumption job automatically sets the "correction" checkmark on the expense journal line to "yes" when the line quantity is negative.|New feature|

___
###10.0.20231204.01
|Suite|Description|Type|
|---|---|---|
|Fixed asset management|Fixed issue with disposal document reversal that changed the status of the document to Reversed after user aborted the reversal proces. |Bug fix|
|Fixed asset management|Enabled code extension on functionality Propose disposal lines in Disposal document.|Changed feature|

___
###10.0.20231116.01
|Suite|Description|Type|
|---|---|---|
|Investment management|Possibility to create an Item return document of the type Cancel for items with an inventory status Reserved ordered. |New feature|
|Investment management|Increased the field length of the parameter PurchAgreementId in API: ProjPurchRequisition.|Bug fix|

___
###10.0.20231027.01
|Suite|Description|Type|
|---|---|---|
|Advanced banking|Improved bank statement proccesing with the option to configure if transactions in the Bank statement proccessing journal are marked or unmarked by default.|New feature|
|Advanced banking|Improved bank statement processing with the option to display the current sum of marked Customer/Vendor transactions.|New feature|
|Fixed asset management|Updated data entity for Asset counting journal lines (Asset counting lines per header): fields Missed, Surplus, Write off, Counted, User enabled for import. Additional validation added to prevent marking counting journal lines with more than one option among Missed, Surplus, Write off.|Changed feature|
___
###10.0.20231019.01
**!!! Important: 10.0.35 application dependency !!!**
|Suite|Description|Type|
|---|---|---|
|Travel and Expenses enhancements| Per diem calculation updated due to changes in Microsoft standard calculation for per diems in version 10.0.35. Per diem rate tiers: Include percent setup is removed. |Dependency update|


___
###10.0.20230929.04
|Suite|Description|Type|
|---|---|---|
|Investment management| Import of a selected Purchase agreement per purchase requisition line is enabled in the Investment management - integration API: ProjPurchRequisition. The functionality is available only when the feature: Enable input of Purchase agreement in createPurchReqService and PurchaseRequisitionLineEntity is enabled.|New feature|
|Investment management| Cleanup for past data (posted records or records in errors) enabled in Project management and accounting > Inquiries and reports > Investment management in forms: Hour consumption (external), Item consumption (external), Cost consumption (external).|New feature|

___
### 10.0.20230929.02
|Suite|Description|Type|
|---|---|---|
|Travel and expenses| New option to force dates entered by the user in the Delegate extended form on to automatically generated records in the Delegates form is added.|New feature|

___
### 10.0.20230929.01
|Suite|Description|Type|
|---|---|---|
|Advanced banking - Bank statement import| New electronic format for Halcom RS is enabled for importing bank statements in Serbia. |New feature|
|Fixed asset management| Calculation of the amount value for transactions generated in the partial disposal process corrected in order to not generate rounding differences.|Bug fix|

___
### 10.0.20230807.01
|Suite|Description|Type|
|---|---|---|
|Defferals|Deferral header can be posted automatically, if the checkbox mark “Don’t post deferral header” is set to “No” when creating the deferral.”|New feature|
|Investment management|Timesheets automatic generation process - error when posting Timesheets "TTSBEGIN/TTSCOMMIT pair has been detected" fixed.|Bug fix|

___
### 10.0.20230725.01
!!! Important: 10.0.34 application dependency !!!
|Suite|Description|Type|
|---|---|---|
|Investment management|Fix for missing parameter inventVersionid on Inventory adjustment print|Dependency update|

___
### 10.0.20230720.01
|Suite|Description|Type|
|---|---|---|
|Investment management|Process expense consumption job: Generating project transaction with negative quantity with appropriate (negative) amounts|Bug Fix|
|Investment management|Additional logic implemented for ProjItemRequirementDeliveries_AdIMI data entity taking into consideration multi inventory transactions related to the same item requirement|New feature|
|Investment management|Updated TechAssetFixedAssetEntity_AdIM data entity unique key impacting BYOD export (data entity mapping structure refresh and republish of data must be performed on existing environments if export to BYOD is enabled)|BugFix|

___
### 10.0.20230706.01
|Suite|Description|Type|
|---|---|---|
|Bank statements|Security fix for button "Change booking date" in bank statement form|Bug fix|
|Compensations|Updated link on voucher field for customer and vendor transactions in the Compensation form. By clicking the voucher value, user is redirected to a new form showing the selected voucher transactions.|Bug fix|
|Compensations|New button added for customer and vendor transactions in the Compensation form for viewing the selected customer or vendor transaction. By clicking the button "Go to customer transaction" or "Go to vendor transaction", user is redirected to a new form showing the selected customer or vendor transaction.|New feature|

___
### 10.0.20230628.01
|Suite|Description|Type|
|---|---|---|
|Investment management|Updated functionality for Item return document of the type Reversal enabling the return of an item with a specific serial number. The functionality upgrades the standard MS D365FO logic in cases when a project consumption of an item is reversed (item is return from the project consumption back on stock) while the initial consumption was performed through an item requirement linked to more than one original inventory transactions. When using the return LotId functionality, the standard logic does not necessarily link the return transaction with the correct inventory transaction of the selected serial number. The Item return document functionality includes an additional search that finds the inventory transaction with the required serial number.|Updated feature|

___
### 10.0.20230626.01
|Suite|Description|Type|
|---|---|---|
|All Suite packages|No changes implemented. Only version number increased.|None|

___
### 10.0.20230525.01
|Suite|Description|Type|
|---|---|---|
|Deferrals|Calculation of deferral amounts based on exchange rates that were saved on the original document|Bug fix|
|Public procurement|Enabled the option to have the same Vendor as a Co-tender in different Consortiums on the same procurement public case|Bug fix|

___
### 10.0.20230419.01
|Suite|Description|Type|
|---|---|---|
|Bank statements|New button on bank statement lines for manual changing Booking date when bank statement header in status Open and bank statement line in status Booked|New feature|
___
### 10.0_2023.04.07.1
|Suite|Description|Type|
|---|---|---|
|Bank statements|Updated ER format for importing bank statements: when bank statement dates do not have a time zone specified, they imported as by the timezone of the legal entity the bank statement is imported to.|Bug fix|
|Realized Cash flow|New infolog message added after recalculation of data is concluded|New feature|
|Compensations|Disabled customer/vendor transaction reversal, when transaction included in an already posted compensation|Bug fix|
|Compensations|Enabled the possibility to change the status of the compensation to Open even when compensation and transaction amounts do not match|Bug fix|

___
### 10.0.20230317.01
|Suite|Description|Type|
|---|---|---|
|Realized Cash flow|Inquiry optimization|New feature|
|Bank statements|Import when date and time format includes fractions of seconds|Bug fix|
|Business events|10.0.32 Dependency update|Dependency update|

___
### 10.0.20230223.01
|Suite|Description|Type|
|---|---|---|
|Fixed asset management|Low value asset: registering cost amounts in Low value asset assignment view for all transactions|New feature|
|Fixed asset management|Low value asset: return proposal posting fix|Bug fix|
|Compensations|Error handling during journal posting|Bug fix|
___
### 10.0.20230202.01
|Suite|Description|Type|
|---|---|---|
|Fixed asset management|Fixed asset book Profile calculation - Partial disposal transaction included|New feature|
___
### 10.0_2022.12.23.1
|Suite|Description|Type|
|---|---|---|
|Fixed asset management|Disposal document - Original document view from Fixed asset transactions|New feature|
|Fixed asset management|Disposal document in reversed status cannot be reverted to draft|Bug fix|
___
### 10.0_2022.12.19.1
|Suite|Description|Type|
|---|---|---|
|Public Procurement|Preparer transfer from Public Procurement case to Purchase agreement|New feature|
|Public Procurement|Incorrect RFQ line update from Public Procurement case|Bug fix|
___
### 10.0_2022.12.03.1
!!! Important: 10.0.26 application depandency !!!
___
### 10.0_2022.11.24.2
|Suite|Description|Type|
|---|---|---|
|Travel and Expense enhancements|Travel requisition to travel expense dimension transfer fix|Bug fix|


### 10.0.2022.11.09.01
|Suite|Description|Type|
|---|---|---|
|Project Invoice enhancements|Added Open transactions button on Project invoice proposal form|New feature|

##*10.0_2022.10.12.1

|Suite| Description | Type|
|--|--|--|
| Bank statements | Removing script from xslt transformations  |MS deprecated feature|
| eInvice | XSLT transformation for specification import - Petrol invoices  |New feature|
| eInvice | XSLT transformation fix for negative amounts - Telekom specification |Bug fix|
___

##*10.0_2022.08.25.1

|Suite| Description | Type|
|--|--|--|
| Vendor invoice lines import | Access to Financial dimensions tab on Consumer definition form  |Bug fix  |


## *10.0_2022.05.09.1

**!!!** *Important: 10.0.25 application depandency* **!!!**
___

##*10.0_2022.05.31.01



|Suite| Description | Type|
|--|--|--|
| Vendor invoice lines import | Added LOT ID on imported lines with Project ID |Bug fix  |


