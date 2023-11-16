# BE-terna suite
[[_TOC_]]

###10.0.20231116.01
|Suite|Description|Type|
|---|---|---|
|Investment management|Possibility to create an Item return document for items with an inventory status Reserved ordered. |New feature|
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


