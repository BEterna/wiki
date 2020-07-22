Low value asset functionality can be used when low value assets are managed through inventory. In that case, companies can track issues, transfers, returns, and write-offs of low value assets in a clear and transparent way.  


# **Setup**
---

## **Posting**

1. Go to **Inventory management > Setup > Posting > Posting** 
2. Select **transaction type**. Posting setup is expanded to include new section Low value assets, where it is possible to define postings for the following transaction types:
   - Issue
   - In use
   - Depreciation
   - Correction
3. Setup for Issue and Depreciation types is **mandatory**. Setup for other types is optional and depends on process specifics. 

## **Journal names**

1. Go to **Inventory management > Setup > Journal names > Inventory**
2. Create a **new journal name** for each journal type and specify the needed parameters. Inventory journals include **additional journal types**:
   - Low value asset – Release
   - Low value asset – Return
   - Low value asset – Transfer

Selection in field **New voucher** by has been **expanded** to include additional option: Worker (waiting for extension point!).

If the journal is of Low value asset – Return type, **additional tab Low value asset** is displayed, where it is possible to set up the **default value for Write-off** (Yes or No). This value is defaulted to Low value asset – Return journal line. If value is set to **Yes**, Low value asset write-off transaction will be generated at the moment of posting transaction with this journal. If value is set to **No** write-of transaction will not be generated. 