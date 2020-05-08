
Mass asset lending functionality is used to automate and simplify the standard D365O Fixed asset lending. Functionality adds the Mass asset lending feature, which amongst others enables users to lend several fixed assets at once, based on the specified criterion.

With the new lending functionallity, responsible employee and/or location can be added/changed, and the last open lending record is closed. In addition, it is also possible to transfer financial dimension values of newly assigned employee to the fixed asset. It is important to emphasize that based on the setup in the system, this functionality can use physical locations (additional feature) instead of standard locations. 

## **Setup**
---

### Physical locations 
Mass asset lending functionality can use either standard or physical locations. To use physical locations:
1. Go to **Fixed assets > Setup > Fixed assets parameters > Fixed assets** tab 
1. Set **Activate physical locations** to Yes. If this option is set to No, standard locations will be used.

### Mass asset lending dimension attributes

With this setup user defines financial dimensions that will be transferred from employee to fixed asset when mass asset lending action is performed. 

1. Go to **Fixed assets > Setup > Fixed asset parameters > Mass asset lending**
1. From the list of available dimensions (attributes) **select attributes** that will be transferred **from employee to fixed asset**. On the left side, there is a list of all available attributes, while on the right side is the list of selected attributes, which will be transferred during mass asset lending, if the **Financial dimensions of the borrower option is set to Yes** when running the Mass asset lending job.
 

## **Perform Mass asset lending**
---

<br>

1. Go to **Fixed assets > Periodic tasks > Mass asset lending** 
1. Specify the following **parameters**:


|**Parameter**| **Description** |
|--|--|
|**Transfer date**  | Date that will be assigned to a new lending record as Lending date. Transfer date also affects the Actual return date of the previous opened lending record. Actual return date is recorded as one day prior to the Transfer date.  New lending cannot be created for fixed assets that have open lending with a later date in comparison to transfer date. If a fixed asset fulfils all filtering criteria, but has an open lending with the later date then the transfer date, Error message will appear. Transfer date must be at least 1 day after the current open lending.|
|**From worker**  |ID of a worker (from the register) from which assets should be transferred. If left blank,  all acquired fixed assets from the fixed asset register will be processed, unless one of the other filters is selected. In this case a warning is displayed upon mass asset transfer generation. All active and inactive workers are availabe for selection.   |
|**To worker**  |ID of the borrowing worker. Only active workers are available for selection. If the field is left empty, new lending record will be generated with the worker from previous borrowing employee. In this case field To location can not be epty, otherways error will occur.|
|**Financial dimensions of the borrower**  |indicate whether financial dimensions from the borrower’s position should be transferred to the fixed asset book upon lending (only the dimensions selected in fixed asset parameters  |

When multiple filters are defined (eg. From worker and From location), only corresponding fixed assets that match all criteria will be processed. 
It is also possible to filter assets to be processed by the: Fixed asset number, Fixed asset book status and Fixed asset group. When selected, click OK to run the mass asset lending.

NOTE: if no “From worker” is specified, fixed asset transfers will be created for all the acquired fixed assets. In this case a warning is displayed upon mass asset transfer generation.

## **Mass asset lending results**
---

When the processing is completed, an informational message with the details about the lent fixed asset(s) is available in the Action center.

Fixed assets > Fixed Assets > Fixed assets

Changes for all the lent fixed assets can be seen by clicking the “Lend” button on each of the fixed assets (standard feature). A new line is created in the “Lending” form of all the processed fixed assets. If a lending line for a fixed asset without the specified “Actual return date” existed, prior to generating the Mass asset lending, then the “Actual return date” is automatically set on the previous day of the newly generated lending line.

If financial dimensions from the borrower’s position were checked to be transferred when generating the Mass asset lending (and setup in Fixed asset parameters exists), then dimensions are transferred from the borrower’s position to all the fixed asset books (with enabled financial dimensions), connected to each of the lent fixed assets.