# User enhanced Bank Reconciliation

The solution enables enhanced advanced bank reconciliation. Based on the transactions from the bank statement, processing can be performed (either manually or based on the pre-set processing rules). In contrast to standard D365O reconciliation, this feature enables automatic matching of imported transactions from bank statements with Open customer transactions (inflows) and not yet posted Vendor payment journals (outflows). After matching, transactions can be posted directly from the bank reconciliation processing journal. 

This solution is part of the AdactaSuiteBankStatements AdSuite D365O package.

## **Setup**
---

### Journal names

1. Open Cash and bank management > Setup > Bank Statements > Journal names.
2. Set up bank statement processing journals and define account types that the bank statement lines can be mapped to.
 
### Unknown inflows

1. Open Cash and bank management > Setup > Bank Statements > Unknown inflows.
2. Define main accounts for unknown inflows and outflows for each bank account to automatically transfer bank statement line amount – when marked unknown – to this account.
 
### Processing rules

1. Open Cash and bank management > Setup > Bank Statements > Processing rules.

Bank statement processing functionality enables automatic reconciliation of data from the electronic bank statement against the transactions in the system, using processing rules.

Steps: 
1. Create a new processing rule set and click “Edit rule set rules” to define processing rules.
1. Create a new processing rule; define its priority (order of execution) and a type of rule:
   - Terminating: if the transaction meets the criteria of the current matching rule in the processing, it will not be included in the processing of the next rule.
   - Nonterminating: if the transaction meets the condition of the current matching rule in the processing, it will nonetheless be included in the processing of the next rule.
5. In the Match tab, define criteria by which bank statement lines are filtered. When using regex match type, regex is verified, named capture groups are recognized and saved below as string values.
In the Actions tab, define the appropriate action (detailed descriptions of each action is found in chapter Action types).<br>
   Depending on the selected action type, an additional tab is shown where criteria for transaction matching are defined. <br>
The rule below says, if bank statement lines with credit transactions and reference number of regex value are found, match them with vendor journal lines, that have the same reference number (field in vendor payment journal is called Payment reference) as bank statement lines.
 
### Action types

Different action types enable the setup of various processing actions. 


| Action  |  Description |
|---|---|
|Rewrite fields   |This action temporarily changes the value of any field in the bank statement using regex. In the “Field label” field, select the field that needs to be changed. The “Rewrite match” field represents the regex (search condition), the value corresponding to this key is overwritten with “Rewrite output”. The change that happens is not stored in the bank statement, as it is recorded only temporarily; this temporary record is then available for the next action.   |
|Extract variables   |Using this action type, processing can extract a variable from an arbitrary field of the bank statement line in the same way as using regex values.   |
|Ignore   |Depending on the condition defined in the Match tab, a credit/debit ignore line is created with this action.   |
|Mark for confirmation   |If this action type is selected, a checkmark “Confirmation required” is set on the bank statements line after processing, which requires the user to manually confirm the indicated line. It is commonly used in combination with an action where a subsequent review is recommended.   |
|Set context   |This action type creates a context that the following actions can use. It is usually combined with other actions. Contexts can be of different types (Ledger, Vendor, Customer…) and are set from regex values (a variable that can be used in field Context variable) or directly specified with a combination of account type and ledger.   |
|Set context if empty   |Used similarly to action type from chapter Set context. Usually used in combination with other actions. It takes place if the previous action did not produce any matching results.   |
|On account   |This action creates a matching of the bank statement line to the account that is defined by the previous action. It is commonly used in combination with the action Set context.   |
|Match collection letter   |If this action type is included in a rule, processing will check customer collection letter journal transactions, additionally filtered by criteria in the Customer transaction matching tab and settle them upon bank statement posting.   |
|Match customer*/vendor open transactions   |*Match customer open transactions processing rule is discontinued and replaced with the Match customer open transactions V2 rule. Vendor open transactions are matched with bank statement lines according to filters set in transaction matching. “Settle matched transaction” action is needed to settle the transactions against bank statement lines, that have been matched during processing.   |
|Match customer open transactions V2   |A new Matching rule is added in order to enable the matching of open customer transactions according to Dispute status. Consequently, the following fields from CustDispute table are added: Collection status, Note, Last Payment amount  |
|Settle matched customer/vendor transactions   | Bank statement lines that have been matched with the previous action are settled against paired customer or vendor transactions with this action.  |
|Settle matched and other customer/vendor transactions by the due date   |Customer or vendor transactions that have been matched with Match customer/vendor open transactions are settled with the current bank statement line. If the amount on the bank statement line exceeds the matched customer or vendor transaction amount, the amount difference gets settled against other open transactions for that customer/vendor, using sorting by the due date (from oldest to latest). This action can also consume customer/vendor as a context in combination with Match customer/vendor bank account action for example. In that case, the bank statement line gets settled against all open transactions sorted by the due date, as described in the previous paragraph.   |
|Match customer/vendor bank account   |Customer or vendor transactions are filtered according to criteria set in the Customer matching/Vendor matching tab and settled against bank statement lines, corresponding to the following action types. If more partners use the same bank account, a warning is thrown after processing.   |
|Match customer/vendor journal lines   |Unposted vendor/customer payment journal lines are matched and settled against bank statement lines according to criteria, defined in Journal matching.    |


 
### Bank account

1. Open Cash and bank management > Bank accounts > Bank accounts.
2. On tab Reconciliation, define processing rules set for the selected bank account.
 
## **Bank statement processing**
---

### Import and validate bank statement

Import and validate bank statement in Cash and bank management > Bank statement reconciliation > Bank statements.

[Detailed documentation](https://ad365o.visualstudio.com/AdLoc/_wiki/wikis/WIPdoc/83/Bank-statement-import?anchor=import-bank-statement)
 
### Bank statement processing journal

Open Cash and bank management > Bank statement reconciliation > Bank statement processing journal.

#### Generate debit and credit journal

1. Generate bank statement processing journal for validated bank statement lines by selecting Credit and Debit journal names and defining the number of lines per each journal.
2. Credit and Debit journals are created. Open the desired journal by clicking on Lines.
3. The form is divided into two tabs. Information about the bank statement lines is found in tab Bank statement lines. Reference number represents payment reference, the Document number is payment ID. Tab Matching is divided into two sections: the right part is used for transaction matching (account types that the bank statement lines can be mapped to are defined in journal setup – see chapter Journal names), whereas the left section provides information about the matched transaction.
 
#### Processing 

1. Run processing to automatically match bank statement lines with transactions in the system, according to processing rules. 
2. After the processing is done, message about the results and possible warnings are displayed.
3. Transactions that match the criteria from processing rules are mapped to adequate bank statement lines. Bank statement lines are marked as Processed. The field Ledger account displays the account that the line was mapped to. Bank statement lines that have not been matched and lines that have been matched by a processing rule that has action type “Mark for confirmation” included, are marked as Confirmation required.
4. For line, that has been matched, information about the matched transaction is displayed in tab Matching.
5. If bank statement line is marked as Unknown, the matching line is automatically created according to setup in Unknown inflows. Bank statement line needs to be manually marked as Confirmed.
 
####  Manual matching

It is possible to manually match bank statement lines to desired account types. Depending on setup on processing journal, account types that are available are Vendor, Customer, Bank account, and General ledger.
1. Select Vendor/Customer account. Open transactions will list below. 
2. If action “Account” is used, the amount from the bank statement line will be posted on a selected vendor/customer account with no link to any transaction. Confirmation is required.
3. It is possible to mark the desired transaction from listed open vendor/customer transactions and match it with bank statement line. Put checkmark in field Marked and click Transfer. The transaction will be settled against the bank statement line in the amount of the bank statement line. Confirmation is required.
4. Bank statement line can be transferred to account type Bank. Select Bank account and click Account to match bank statement line against a bank account. Confirmation is required.
5. Bank statement line transaction can also be settled on main account. In tab General ledger, select main account and click Transfer. Link type General ledger is created. Confirmation is required.
 
When journal setup allows Customer account type, additional action Prepayment is available. With this bank statement line can be marked as prepayment and will be posted according to customer posting profile for prepayments, selected upon Transfer. 
 
#### Transfer

Use the Transfer function to transfer processed and confirmed (if confirmation is required) bank statement lines to the general journal for posting. 
 
Transfer parameters:


|**Parameter**| **Description** |
|--|--|
|Journal name  |Select journal for bank statement posting  |
|Lines per journal  |Limit the number of lines per one general journal  |
|Process unprocessed  |Run the processing upon transferring  |
|Post journal  |Post the journal upon transferring  |
|Transfer errors  |Works in combination with “Post journal”; during journal posting journal lines that contain errors are transferred into a new journal (works similarly as Post and transfer button in the journal)  |
|Allow duplicates  |Bank statement lines are transferred to the journal even if they have already been transferred to journal previously  |
|Customers-Posting profile |Select customer’s posting profile to post the transferred bank statement lines |
|Customers-Prepayment profile|Select a customer’s posting profile for posting transferred bank statement lines that have been marked as Prepayment. If prepayment profile is left empty, it will be read from setup Accounts receivable > Setup > Accounts receivable parameters > Ledger and sales tax > Payment > Posting profile with prepayment journal voucher. If there is no setup, general posting profile for customers is transferred (Accounts receivable > Setup > Accounts receivable parameters > Ledger and sales tax > General > Posting profile)  |
|Vendors-Posting profile |Select a vendor’s posting profile to post the transferred bank statement lines with|

Upon transferring, message with detailed results of transfer action and possible warnings/errors upon validation is displayed. Bank statement lines are updated with journal number and marked as Transferred.

Use View details to open the journal.
 
If bank statement lines were matched with vendor or customer payment journal lines, these lines are transferred from payment journal to general journal upon transfer and keep the voucher from payment journal. If all lines from payment journal are transferred to the general journal for bank statement posting, payment journal is automatically deleted.