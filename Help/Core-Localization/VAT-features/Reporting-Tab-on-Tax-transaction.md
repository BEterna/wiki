

As part of localization, an additional “Reporting” tab is added to Tax transactions. It displays information, such as Customer/Vendor, Address, Tax exempt number, Document, Document date, and Document receipt date. This information is used for VAT reporting.

## **Reporting Tab data sources**
----
Go to Tax > Inquiries and reports > Sales tax inquiries > Posted sales tax > Reporting tab

Following information, needed for VAT reporting purposes is added to the tab:

**Customer/Vendor** 


|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  | Vendor/Customer in the document header |
| Journal with Vendor/Customer line | Customer/Vendor field on journal line |



 **Address** 

|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  | Vendor/Customer in the document header |
| Journal with Vendor/Customer line | Address field on journal line |

 
 
**Tax exempt number**: 

|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  |Tax exempt number from the original document |
| Journal with Vendor/Customer line | Tax exempt number field on journal line |

 

**Document** 

|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  | |
| Journal with Vendor/Customer line |Document field if fields Invoice and Document are populated / Invoice field if only field Invoice is populated on the journal line. |

  

 **Document date** 
|Source document| Source field |
|--|--|
| Vendor Invoice, Sales Invoice, Free text invoice, and Project Invoice  |Invoice date on the original document |
| Journal with Vendor/Customer line | Invoice date field on journal line |



**Document receipt date** 

|Source document| Source field |
|--|--|
| Vendor Invoice |Document receipt date on the original document|
| Journal with Vendor/Customer line | Document receipt field on journal line |


