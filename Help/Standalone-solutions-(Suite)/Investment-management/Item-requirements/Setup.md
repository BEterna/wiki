# Picking route status
---
In order for the Process item requirements job to do the automatic picking of items on exact product dimension values that are specified on item requirements, the Picking route status field must be set to Activated in the Accounts receivable parameters and in the Inventory and warehouse management parameters.

![IRSetup01.jpg](/.attachments/IRSetup01-051a4163-8f83-4781-a167-6a0993580d74.jpg)

![IRSetup02.jpg](/.attachments/IRSetup02-1eb187d6-7a17-430a-91ef-c3805463fbce.jpg)

# Warehouses
---
For terrain (and default) the warehouses following configuration is important: investment management type, manual item coverage, default receipt location, transit warehouse. Setup is described in the following paragraphs.

## Investment management type
For investment management, additional field Type is available in _Warehouse management > Setup > Warehouse > Warehouses_:
- **Default** - ordinary warehouse
- **Terrain** - warehouse on terrain (e.g. construction site)
- **Moving** – mobile warehouse (e.g. vehicle).

![IRSetup03.jpg](/.attachments/IRSetup03-aa782771-774d-44fc-8b12-3802502f0b2b.jpg)

Once the selection is saved on warehouse, it cannot be modified. Based on this configuration, system can know, when to create transfer orders automatically out of item requirements. This is the case when consumption warehouse and receiving warehouse differ, but consumption warehouse must be marked as terrain.
 
## Manual item coverage
All terrain and moving warehouses must have the **Manual** checkbox in the _Inventory management > Setup > Inventory breakdown > Warehouses > Master planning_ tab set to **Yes**. 

![IRSetup04.jpg](/.attachments/IRSetup04-16aed59e-aae1-4f87-9a99-df33b501fac8.jpg)

With this option set to Yes, master planning will not automatically create purchase orders for terrain (or moving) warehouses. Instead, automatic transfer orders will be generated from receiving warehouse to terrain (consumption) warehouse and master planning will create purchase orders only for receiving warehouse if no stock is available.

## Default receipt location
 _Inventory management > Setup > Inventory breakdown > Warehouses > Inventory and warehouse management tab > field Default receipt location_

![IRSetup05.jpg](/.attachments/IRSetup05-7b6fe514-2964-4020-a001-c208daa87570.jpg)

All terrain and moving warehouses must have only one location configured. Also, the Default receipt location must be defined for the purpose of auto-receiving items via automatically or manually created transfer orders. This is the location that will be used when on-hand inventory is registered during the inbound process. This location will also be used for transactions with items that use a storage dimension group with the active Location dimension.

## Transit warehouse
 _Inventory management > Setup > Inventory breakdown > Warehouses > General tab > field Transit warehouse_

![IRSetup06.jpg](/.attachments/IRSetup06-df582b7b-ce3c-40dd-a2e6-c6976a91f03b.jpg)

All warehouses of type Default (receiving WHS on item requirement) must have Transit warehouse defined, so that automatically created transfer orders can be processed correctly through transit warehouses.