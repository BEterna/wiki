# Tax depreciation report 

This topic provides country/region-specific information about additional Tax depreciation reports, added with a purpose to comply with the Serbian legislation. 

This localization feature enables the preparation of an annual fixed asset depreciation report. Old form, valid until 31.12.2019 and new one (POA), valid from 1.1.2020 are available. Additionally, analytical report by Fixed asset is also added. 

## **Setup**
---

### Depreciation profile

There should be as many depreciation profiles as there are tax depreciation groups. A fixed asset depreciation profile should be related to the appropriate tax depreciation group. Localized field Asset accounting type (tax depreciation group) is added to the form for reporting purposes.

1. Open Fixed asset - Setup - Depreciation profiles.
2. Choose Asset account type: Type 2.
 
### Asset Book (standard)

There should be one Asset Book that will be used for calculating tax depreciation with the following settings (all the fields are standard, no localization setup added).

1. Open Fixed assets - Setup - Books.
   - Calculate depreciation: set field to Yes.
   - Depreciation profile: field can be blank, in order to be able to select proper information on each fixed asset, depending on the tax depreciation group belongs.
   - Post to general ledger: set field to No.
   - Posting layer: choose option None.

### Tax depreciation book on fixed asset (standard)

It is necessary to define parameters for the Asset Book which will be used for tax purposes, for each fixed asset. 

All the fields are standard, no localization fields added:
   - Depreciation profile
   - Depreciation run date (the year when the OS is put into use)
   - Service Life = reconcile Service life with Percent of depreciation
 
NOTE: Depreciation convention for fixed assets put in use in the first half of the year can be set to Half year (start of year).

### Accounting and Tax asset book link

1. Open Fixed assets - Setup - Books.
2. It is recommended to set up Tax depreciation book as one of the derived books on accounting books. This way tax depreciation will be calculated together with accounting depreciation. 

Book|Transaction Type
-|-
PORESKA-T|Acquisition 
PORESKA-T|Acquisition adjustment
PORESKA-T|Write up adjustment

## **Generate report**
---

1. The report can be generated on the following path: Fixed assets > Inquiries and reports > Serbia > Tax depreciation calculation repot
2. Report parameters:
   - Date from and Date to – entered period should be one fiscal year long
   - Book – select Asset book used for tax depreciation
   - Average salary – Five times multiplied average salary amount 
3. Click OK and the report will be created.
 
