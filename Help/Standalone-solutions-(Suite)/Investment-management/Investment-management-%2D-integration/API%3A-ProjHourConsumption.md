ProjHourConsumption API enables 3rd party systems to create staging transactions in D365FO from which hour project transactions are created by a D365FO batch job.

# Staging transactions
---
The staging transactions can be created or updated through ProjHourConsumption API in **Project hour consumption** staging table, located under **Project management and accounting > Inquiries and reports > Investment management > Project hour consumption (external)**. The API can insert records, when the External reference does not exist yet or update existing External reference with status None in staging table in the D365FO. 

After successful inserts or updates of records in the Project hour consumption staging table, an output is provided from D365FO to the 3rd party system. When inserts or updates fail, the error message is provided to the 3rd party system.

# Batch processing of staging transactions
---
The batch job for processing hour consumption in D365FO Investment management package is in **Project management and accounting > Periodic > Investment management > Timesheet generation**.

With batch processing, Project timesheets are created/updated.  

Batch job considers only records with status **None** (hours were transferred from the external system, but are not transferred to a timesheet yet). Status of the selected records changes to:
- **Transferred**: hours are transferred to a timesheet, but the timesheet is still not posted (hours transferred to the timesheet are considered approved from the 3rd party system and as such marked as approved),
- **Posted**: hours are transferred to a timesheet and the timesheet is posted.
- **Error**: there was an error while transferring hours to a timesheet. The Error message is shown in the Error message field.
- **Cancelled**: hours are not transferred to timesheets, because there are lines with identical information and such quantities that the total sum is 0 (e.g., there is one line with quantity 5 and additional line with the same information and quantity -5, for the same user, project and transaction date). Lines with negative quantities are provided from the external system to correct wrongly entered hours that were approved in the external system and sent to the D365FO.
-**Deleted**: hours that were trensferred to the timesheet were also deleted in the timesheet.

Field Transaction ID in the project hour consumption staging form is filled for each successfully processed line that was posted through a timesheet. 

Unsuccessfully processed staging transactions with an error can be reprocessed by manually:
- resetting their status (click button Reset status in the **Project hour consumption** staging form) 
- and triggering the timesheet generation (click button Timesheet generation) - this step can be omitted as the batch job always process all staging transactions in status None.
