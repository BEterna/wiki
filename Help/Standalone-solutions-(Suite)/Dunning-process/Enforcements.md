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

