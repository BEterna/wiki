The functionality offers creating new fixed assets, as well as choosing already created fixed assets. Please note that more than one fixed asset can be created/adjusted within the same proposal.

# Create new fixed assets
---
To create new fixed assets in the Project activation proposal document, click the Create assets button in the Fixed assets fast tab.

Define the data about new fixed assets that are going to be created. Mandatory fields are Number of assets and Fixed asset group. In the Item number field, items added through project transactions can be selected. If one of the offered items is selected, item information will be added to the new fixed asset line (e.g. Name and Long Name of fixed asset will get Item Search Name). In the Value models select Books that new fixed assets must have. In the Financial dimensions, fill financial dimensions that will be transferred to FA books (if required). 

![Items (3).png](/.attachments/Items%20(3)-b17899b2-192f-452b-8e1b-a3600a2ec1c1.png)

After entering all needed information, press OK to create new fixed assets.

New fixed assets are added in the Fixed assets fast tab. All fixed assets that have been created have transaction type set to Acquisition. Fixed asset information can be added/edited in the lines.

Fixed asset information from the proposal line is transferred to the fixed asset entity after posting Project activation proposal. Fixed asset fields in the proposal are mapped to the following fields in the fixed asset:
- 	Asset: Fixed assets/General fast tab/Number
- 	Book: Fixed assets/Books
- 	Name: Fixed assets/General fast tab/Name
- 	Long name: Fixed assets/General fast tab/Long name
- 	Quantity: Fixed assets/General fast tab/Quantity
- 	Unit of measure: Fixed assets/General fast tab/Unit of Measure
- 	Assigned person: Fixed assets/Lend/Loaned to
- 	Item number: Fixed assets/Technical information fast tab/Item number
- 	Serial number: Fixed assets/Technical information fast tab/Serial number
- 	Manufacturer: Fixed assets/Technical information fast tab/Manufacturer
- 	Physical location (Location if standard locations are used): Fixed assets/Location fast tab/Physical location (Location) and Fixed assets/Lend/Physical location (Location)
- 	Property group: Fixed assets/General fast tab/Property group
- 	Asset activity code: Fixed assets/General fast tab/Asset activity code
- 	Transaction type: Fixed assets/Books/Transactions/Transaction type
- 	Reason code: Fixed assets/Books/Transactions/General tab/Reason code
- 	Reason comment: Fixed assets/Books/Transactions/General tab/Reason comment
- 	Distributed amount: Fixed assets/Books/Transactions/Amount

# Select existing fixed assets
---
Another option to add fixed assets on Project activation proposal is to choose already existing fixed assets. In order to do so, click Add line button in the Fixed assets fast tab and then choose the Fixed asset. Other required information can be also added in the lines. If the chosen fixed asset is already acquired, Transaction type will be set to Write up adjustment. For not yet acquired fixed asset, transaction type will be acquisition.

![Items (4).png](/.attachments/Items%20(4)-5f59c2a9-cd28-428a-a725-7934912eb172.png)

Note that fields Assigned person and Physical location (Location) for existing fixed assets are non-editable fields. If Assigned person and/or Physical location (Location) must be changed, it can be done via Mass asset lending functionality or directly on fixed asset.

If chosen fixed asset has book status Closed, transaction type will be set to Write up adjustment. After posting the Activation proposal, following changes will be made on a fixed asset:
1. Book status will be changed from Closed to Open.
2. Write up adjustment transaction will be posted to the fixed asset.
3. Date when depreciation was last run will be changed based on the depreciation convention on fixed asset book and Write up transaction date. Possibilities are following:
   - Depreciation convention None - Date when depreciation was last run will be one day before Write up adjustment transaction date.
   - Depreciation convention Half year - Date when depreciation was last run will be the last day of the previous month in which Write up adjustment transaction occurred (e.g. Write up in May, date when depreciation last run 30.04.).
   - Depreciation convention Full month - Date when depreciation was last run will be the last day of the previous month in which Write up adjustment transaction occurred (e.g. Write up in May, date when depreciation last run 30.04.).
   - Depreciation convention Mid quarter - Date when depreciation was last run will be the last day of the previous month in which Write up adjustment transaction occurred (e.g. Write up in May, date when depreciation last run 30.04.).
   - Depreciation convention Mid month (1st of month) - If Write up adjustment transaction is in the first 15 days of the Month, then the Date when depreciation was last run will be the last day of the previous month, otherwise the last day of the month when the Write up adjustment transaction occurred (e.g. write up 10.04. – depreciation last run 31.03.; write up 20.04. – depreciation last run 30.04.).
   - Depreciation convention Mid month (15th of month) - Date when depreciation was last run will be the last day of the previous month in which Write up adjustment transaction occurred (e.g. Write up in May, date when depreciation last run 30.04.).
   - Depreciation convention Half year (start of year) - If Write up adjustment transaction occurred in the first half of the year, then the Date when depreciation was last run will be the last day of the previous year in which the Write up adjustment transaction occurred, otherwise the last day of the first half of the year in which the Write up adjustment transaction occurred (e.g. Write up 10.04.2020 - depreciation last run 31.12.2019; write up 20.09.2020 - depreciation last run 30.06.2020).
   - Depreciation convention Half year (next year) - If Write up adjustment transaction occurred in the first half of the year, then the Date when depreciation was last run will be the last day of the previous year in which the Write up adjustment transaction occurred, otherwise the last day of the year in which the Write up adjustment transaction occurred (e.g. Write up 10.04.2020 - depreciation last run 31.12.2019; write up 20.09.2020 - depreciation last run 31.12.2020).
   - Depreciation convention Next month (this depreciation convention is a part of the AdLoc package) - Date when depreciation was last run will be the last day of the month in which Write up adjustment transaction occurred (e.g. Write up in May, date when depreciation last run 31.05.).
4. If depreciation method is Straight line life remaining, value from the field Depreciation periods will be copied to the field Depreciation periods remaining. This step will be skipped for the depreciation method Straight line service life, since field Depreciation periods are used for the calculation of depreciation amount in this method.

