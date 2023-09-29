ProjExpenseConsumption API enables 3rd party systems to create staging transactions in D365FO from which expense project transactions are created by a D365FO batch job.

# Staging transactions
---
The staging transactions can be created or updated through ProjExpenseConsumption API in **Project expense consumption** staging table, located under **Project management and accounting > Inquiries and reports > Investment management > Project expense consumption (external)**. The API can insert records, when the External reference does not exist yet or update existing External reference with status None in staging table in the D365FO. 

After successful inserts or updates of records in the Project expense consumption staging table, an output is provided from D365FO to the 3rd party system. When inserts or updates fail, the error message is provided to the 3rd party system.

The ProjExpenseConsumption API  enables two options to for passing expense consumption:
- either by defining the project category,
- or by defining technical asset ID and Unit of measure (in  this case the project category is calculated based on the Technical asset category relation setup).

# Batch processing of staging transactions
---
The batch job Process project expense consumption in D365FO Investment management package is in **Project management and accounting > Periodic > Investment management > Process project expense consumption**.

With batch processing, Expense journals are created in **Project management and accounting > Journals > Expense**. Which journal name will be created, is defined in **Project management and accounting parameters > IM Integration > Project consumption > Expense journal**. 

Batch job considers only records with status **None**. When records are available for processing, batch job checks setup for **Maximum line per journal**. Status of the selected records changes to **Transferred, Error or Posted**. Field Journal in the project expense consumption staging form is filled for each successfully processed line. Consequently, lines that are recorded in the same journal, have the same Journal number in the project expense consumption staging form. If possible, batch job posts created Expense journals. 

Depending on the result of batch processing, different outcomes are possible:
- **Posting is successful**, records included in the batch job with status Transferred:
  - Status of such records changes to Posted
  - Transaction ID is filled with ID of the project transaction that is created by posting the Expense journal
  - Journal number is filled in
- **Posting fails**, records included in the batch job with status Transferred:
  - Status stays Transferred as records exist in a created journal
  - Transaction ID is filled with ID of the project transaction that will be created with posting of the Expense journal
   - Journal number is filled in
   - For such cases, users have to review posting errors within journal and update data of record within journal (e.g. missing financial dimensions) or amend configuration (e.g. missing main account for a project category) 

If successfully created journal that was not yet posted due to some error is manually deleted after the batch processing, records that are linked to the deleted journal change status to None and the Journal field changes to blank value. If the journal created with batch processing is posted manually, records that are linked to this journal change status to Posted and Transaction ID is filled in.

Unsuccessfully processed staging transactions with an error can be reprocessed by manually resetting their status (click button Reset status in the **Project expense consumption** staging form).

By default the records shown in the form are filtered to those with a Date in the current month.
A cleanup function is provided for past records status Posted or Error (click button Delete transactions in the **Project expense consumption** staging form).

