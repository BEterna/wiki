
Mass asset lending functionality is used to automate and simplify the standard D365O Fixed asset lending. Functionality adds the Mass asset lending feature, which amongst others enables users to lend several fixed assets at once, based on the specified criterion.

## **Setup**
---

### Financial dimensions of the borrower

Fixed assets > Setup > Fixed asset parameters > Mass asset lending

Select Financial dimensions that need to be transferred from borrower to Fixed asset. 

## **Generate Mass asset lending**
---

Fixed assets > Periodic tasks > Mass asset lending

Specify the following parameters:


|**Parameter**| **Description** |
|--|--|
|Transfer date  |  |
|From worker  |ID of a worker (from the register) from which assets should be transferred (if left blank,  all the acquired fixed assets from the fixed asset register will be processed)  |
|To worker  |ID of the borrower (worker from the register)  |
|Financial dimensions of the borrower  |indicate whether financial dimensions from the borrower’s position should be transferred to the fixed asset book upon lending (only the dimensions selected in fixed asset parameters  |


It is also possible to filter assets to be processed by the: Fixed asset number, Fixed asset book status and Fixed asset group. When selected, click OK to run the mass asset lending.

NOTE: if no “From worker” is specified, fixed asset transfers will be created for all the acquired fixed assets. In this case a warning is displayed upon mass asset transfer generation.

## **Mass asset lending results**
---

When the processing is completed, an informational message with the details about the lent fixed asset(s) is available in the Action center.

Fixed assets > Fixed Assets > Fixed assets

Changes for all the lent fixed assets can be seen by clicking the “Lend” button on each of the fixed assets (standard feature). A new line is created in the “Lending” form of all the processed fixed assets. If a lending line for a fixed asset without the specified “Actual return date” existed, prior to generating the Mass asset lending, then the “Actual return date” is automatically set on the previous day of the newly generated lending line.

If financial dimensions from the borrower’s position were checked to be transferred when generating the Mass asset lending (and setup in Fixed asset parameters exists), then dimensions are transferred from the borrower’s position to all the fixed asset books (with enabled financial dimensions), connected to each of the lent fixed assets.