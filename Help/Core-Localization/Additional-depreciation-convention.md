# Additional depreciation convention

This topic provides country/region-specific information about additional depreciation convention, added with a purpose to comply with the local legislation. According to the local accounting standards, depreciation calculation for fixed assets has to start with the first date of the following month after an asset has been put in use, or when it is available for use.

Localization feature offers an additional depreciation convention “Next month”, which enables automatic setup of depreciation calculation run date at the first date of the month after the fixed asset has been acquired (acquisition posting date is considered) or placed in service (placed in service date is considered). For example, if an asset has been acquired (or put in use) on the 10th of July, using this localized feature, the depreciation run date will be set on the first day of the following month (August 1st).

## **Setup**
---

### Depreciation convention
1. Go to Fixed assets > Setup > Fixed asset groups > Books > Depreciation convention.
2. Additional  Depreciation convention type »Next month« is added. 


### Create depreciation adjustment with basis adjustment setup on FA Book
This setup affects only transaction type Acquisition adjustment. 
1. If set to Yes: Next month convention is ignored. Transaction is included in calculation of base amount for depreciation in the month of transaction date (transaction posted on 1.1. will be included in depreciation calculation for january)   
2. If set to No: Next month convention is taken into account. Transaction is included in calculation of base amount for depreciation the next month after transaction date (transaction posted on 1.1. will be included in depreciation calculation for february)   

## **Usage**
---
When this type is set on a Fixed asset book, the depreciation run date will be set in the moment of acquisition posting and will be set to the following month. Placed in service month is determined by the acquisition posting date and the Depreciation run date will be set to the following month. 

The default setup of the Depreciation convention can be done on a general Asset book setup or directly on a fixed asset book:
   - Placed in service
   - Depreciation run date

Transactions taken into consideration: 
 - Acquisition
 - Acquisition adjustment
 - Write up adjustment
 - Write down adjustment

 

 

