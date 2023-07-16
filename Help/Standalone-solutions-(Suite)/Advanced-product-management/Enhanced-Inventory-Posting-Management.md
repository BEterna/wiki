Enhanced inventory posting management _(Inventory management > Setup > Posting > Posting)_ is part of UIM solution, _Adacta Suite Product and Inventory Management_. 

The purpose of Enhanced inventory posting management is to enable setting up a **detailed posting definition** in case a separate account is needed when posting inventory transactions to a certain **Warehouse** or **Project allocation** (project). 

# Use of Enhanced Inventory posting management
---
When posting an inventory transaction that has detailed settings for posting project inventory in addition to the standard settings, the amount is not posted to the standard accounts, but the system uses the account defined within the additional settings. 

If the above setting exists, the order of priority is taken into account, posting rules from more detailed to less apply:
- Project allocation
- Warehouse
- Standard account

# Setup
---
In the inventory posting settings _(Inventory management> Setup> Posting> Posting)_, a new tab for four inventory areas: _sales order, purchase order, inventory _and_ production,_ has been added, where it is possible to define:

a detailed posting set up (Posting definition detail type) for the:
- Project allocation
- Warehouse 

Value:
- Value of project allocation or
- Warehouse

Main account:
- Account for posting.

# Data entity
---
Invent posting details (InventPostingDetailStaging_AdPIM)