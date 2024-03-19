This functionality can be found in Account payable – Inquiries and reports – Product receipt. The report uses purchase prices from vendor invoices and charges (feature charges codes must be used) and calculates sales prices. This helps us to calculate cost per unit and compare it with retail price. Based on this, return on investment (ROI) is calculated for every received item. This function was primarily developed for tracking ROI from retailors in HR region. 

**ROI (in %)= (Retail price – item price)/ item price*100**

Item price= item price on invoice + charges

Retail price= sales price from trade agreement

## **SETUP**
---
**Trade agreement**

*Activate price/discount*
1.	Open Sales and marketing > Setup > Activate price/discounts 
2.	Here you can activate the exact types and combinations of trade agreements you would like to enable. Usually, it is best to enable everything unless there is a specific reason not to.

*Charges codes*
1.	Open Accounts payable > Setup > Charges setup > Charges codes
2.	Open new charge code
3.	Define posting setup for Debit/Credit:
-	Type: Item, ledger account, Customer/vendor
-	Posting: define relevant posting 
-	Account: define relevant account to which charges will be posted
4.	If foreign trade is applied there is additional option to enable Intrastat invoice value and Intrastat statistical value

## **USE CASE SCENARIO**
---
1.	Release new product 
2.	Go to specific release product details and in action pane go to Sell > Trade agreements
3.	Create trade agreement 
4.	Activate price/discounts
5.	Here go to lines and fulfill all fields that are relevant to specific trade agreement
6.	Post trade agreement journal
7.	Go to Accounts payable > Purchase orders > All purchase orders and create a new purchase order with previously created item
8.	If applicable, add charges under tab Purchase > Charges > Maintain charges. When charges are applied, allocate it on purchase order lines.
9.	Generate and post product receipt
10.	Generate and post invoice
11.	Go to Accounts payable > Inquiries and reports > Product receipt and choose retail price calculation. Here, calculation for every product receipt can be seen. On the form, two fields are visible. Under Retail price calculation the all items for specific product receipt are listed and under Charges all the charges applied to these items are listed. 
Here, also different price groups can be set up. Setup is created in module Retail and commerce > Pricing and discounts > All price groups
