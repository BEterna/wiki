Fixed assets management package offers users a set of functionalities which simplify processes for users in case of a large number of fixed assets. Following functionalities are available as part of this package: 
- Fixed assets counting
- Mass asset lending transfer
- Partial asset Write-off

-----

#Fixed assets counting

Purpose of Fixed assets counting functionality is automation of Fixed assets counting process. With standard functionality this process is performed manually, while with this features it is possible to generate filtered counting lists, export them (to use with readers), later import the results and later perform needed actions (write off, reallocation).

Feature enables users to perform fixed asset counting. Fixed asset counting list (a list of assets from D365 to be counted), a list of counting locations (from D365 fixed asset locations register) and list of counting users (list of responsible person for all fixed assets from D365 register) can be exported from D365O as a TXT file. After scanning procedure is done, a list of scanned fixed assets can be imported from the reader back to D365 and adequately processed.

Upon the import, information about the counting user, time, location, fixed asset name and bar code are transferred to each fixed asset from the counting list. Additionally, surpluses and assets checked for write-off are automatically marked, while missing assets have to be marked manually. Lines can also be added manually, while imported lines can also still be edited, while in adequate status. When counting status is completed, locations from the scanned locations of each fixed asset are updated on D365O fixed asset register for each fixed asset. Additionally when in status “Completed”, write-off journal can be created automatically from fixed asset counting list. Assets marked either as “Missing” or “Write off” will be automatically added to the write off journal.


Feature is part of a custom development in scope of the AdactaSuiteFixedAssetManagement AdSuite D365O extension packet.

[Detailed documentation](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Suite%20documentation/D365_AdSuite_Fixed%20asset%20counting.docx?d=w6ca968eef9b94595b2c5fa979754adcf&csf=1&e=ItvlZI)

-----

#Mass asset lending transfer


-----

#Partial asset Write-off