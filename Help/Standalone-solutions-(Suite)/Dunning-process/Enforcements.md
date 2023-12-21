#**Enforcement proposal template**
Credit and collections/Enforcements/Enforcement proposals (button Template)

To simplify day to day operations, enforcement template can be created. This template will be used when creating new enforcement proposals. In the template user can predefine all data that is common to new enforcement proposals. The data used in the template can be later changed in the enforcement proposal. 

Suggested common data, defined on the template:

|**Tab**|**Field**|**Description**|
|--|--|--|
|General|Billing classification|Select or enter billing classification that will be used for charging customer for| 
|General|Reference ID formatting|String that formats payment reference, where %1 is replace by proposal ID and %2 by customer account|
|General|Legal interest (Yes/No)|Are legal late interest available?|
|Participants|Table of data|Roles creditor, representative and depositor are usually same for all new enforcements. Each line in the table has own Details below. For creditor tab bank account should also be defined.|
|Suggestions|Table of data|In this table it can be defined usual means for transaction repayment, such as cash equivalents (money on bank account) or regular income…|
|Creditor cost|Table of data|Table of cost type where setup for Free text invoices and pending vendor invoices can be set (with Yes/No option for Legal interests).|

#**Enforcement proposal creation**

Enforcement proposals are created in Credit and collections/Enforcements/Enforcement proposals and can be created:
-	manually
-	directly from the open customer transactions
-	from the collection cases

##**Manual enforcement proposal creation**
1.	New
2.	New form is created, enter all necessary data (explained below in enforcement proposal details)
3.	Save
##**Create multiple enforcements proposals**
Multiple Enforcement proposal can be created in collections/Enforcements/Enforcement proposals:
1.	Create enforcement proposals
2.	Operation- Create new or add to existing
3.	Add additional search conditions and record to include
4.	Run in the background Yes (preferred) / No
5.	OK
##**Create enforcements proposals directly from collection cases**
1.	Credit and collections/Collections/Collections cases
2.	Choose a case
3.	Mark open transactions
4.	Assign to enforcement
5.	New proposal/existing proposal
6.	»Assign to enforcement« button

#**Enforcement proposal details**
The following web site contains detailed Instructions for enforcement proposal generation, which clearly defines all the proposal fields:
https://evlozisce.sodisce.si/dokumenti/priloga7.pdf* 

##**Enforcement proposal contains following data**
###**General**
|**Field**|**Description**|
|--|--|
|IDENTIFICATION|- _Enforcement proposal ID:_ is generated based on the pre-set number sequence<br>- _Description:_ a free text field. By adding a participant in »Participants« section, a value from the Name/Surname field from that section is added to the description.<br>- _Customer account:_ is automatically populated at the time of the Debtor selection in »Participants« section of the proposal.<br>- _Creation user:_ username of the worker, who prepared the enforcement|
|ENFORCEMENT PACKET|- _Enforcement packet ID:_ if an enforcement proposal is included to the enforcement packet, this field displays the packet field|
|STATUS|<br>-_Status:_ possible statuses are: Draft, Exported to XML, Included to the enforcement packet<br>-_Exported to XML:_ the date and time of the proposal export as XML file|
|DETAILS|<br>- _Billing classification:_ should be selected in case the costs should be charged to the creditor (»Creditor cost« section) with the selected billing classification (More in chapter 4.2.5).<br>- _Reference ID formatting_ a pre-set string for the creditor's invoice reference, where »%1« represents the Enforcement proposal ID and »%2« Customer account. Reference generated based on that pattern is transferred to the »Reference ID formatting« field to the creditor's bank account (see photo below). It is also possible to enter this reference manually. In this case the manually entered value will be transferred from the »Reference ID formatting« field in the »General »section to the »Reference ID formatting« field in the »Participants« field on the Enforcement proposal.<br>- _Legal interests:_ if set to “Yes”, setting is transferred to the authenticated document, where the same field exists (just defaults values to each authenticated document). Additionally, this field is set on the authenticated document, if a transaction of a type »Interest« is selected.<br>- _Economic matter:_ should be marked in a case of a dispute in which, based on the article 481 of »Zakon o pravdnem postopku« rules about the economic disputes apply. NOTE: currently this option is correctly transferred to XML but has to be set manually when XML is uploaded to e-Sodstvo portal, due to the bug on the portal.|
|PROJECT|- _Project ID:_ an identification of a project (in case user wants to post the costs of enforcement to a project, based on the project ID, adequate project is transferred to a vendor invoice, created in the »Creditor costs« section).|

###**Participants**
|**Field**|**Description**|
|--|--|
|ROLE|Possible roles when adding participants are: Debtor, Creditor, Executor, Representative, Assignee, Depositor, Debtors debtor, Civil court and Country court. NOTE: the following roles are mandatory for exporting XML: Debtor, Creditor, Depositor and Representative.|
|PARTICIPANT TYPE|Natural person, Legal entity, Sole proprietor, Court|
|PARTY ID|Based on the Participant type selection, records from the global address book are adequately filtered.|
|NAME|Is automatically transferred, based on the Party ID selection, but manual entry is also possible.|
|NAME/SURNAME|Is automatically transferred, based on the Party ID selection, but manual entry is also possible. NOTE: field can be overwritten with the participant’s name from the AJPES (Slovenian Taxable Persons), based on the tax identification number (VAT ID).|

When adding a participant, information required for filing the enforcements are transferred to »Details« and »Bank accounts« tabs.

###**Suggestions**
Different kinds of enforcement proposals are supported. Available from the list:
-	Bank account assets (Denarna sredstva OPP)
-	Real estate in the land register (Nepremičnina ZK)
-	Chattel (Premoženje)
-	The partner's share (Delež družbenika)
-	Regular income (Redni prihodki)
-	Preference stock (Prednostne delnice)
-	Other material property rights - Druge premoženjske materialne pravice
-	Real estate not in the land register (Nepremičnina ni ZK)
-	Property right (Stavbna pravica)
-	Other monetary receivables (Druge denarne terjatve)
Some of these “suggestions” need additional details.

###**Creditor costs**
|**Field**|**Description**|
|--|--|
|Cost type|Fee amount, Form, Posting, Lawyer, Other costs|
|Vendor account|Account of the vendor to which liabilities for the specified costs will be posted|
|Procurement category|For posting liability to vendor|
|Billing code|For transferring enforcement costs to the debtor|
|Description|Free text field|
|Unit|Unit of measure|
|Authentic document percent|By entering certain number – e.g. 10, 10% of the authenticated documents value will be calculated and transferred to “Amount” field.|
|Currency|Transaction currency|
|Reimbursement required|Checkmark is relevant only for cost types “Lawyer cost” or “Fee amount”|
|Liable for Slovenian VAT|Checkmark is relevant only for “Lawyer cost” cost type|