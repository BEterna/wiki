# API: getInventory
---
GetInventory API **returns the OnHand inventory data** breaked down by:
- **Storage dimensions**: Site, Warehouse, Location
- **Tracking dimensions**: Batch, Serial, Project allocation

The API provides the retrieval of all OnHand Inventory data or just the ones that were modified after a selected date. Due to the possible large amount of data, the service is designed so that it **returns only the first 500 records**. Therefore to retrieve all OnHand data that were modified after a selected date, the **API call must be repeated with a new selected date which must be the Modified date time of the last returned respond**.

Response of this API includes the following relevant data that are part of each OnHand Inventory record:
- Attribute values – When attribute values are available, they are listed with additional relevant data:
  - Name
  - Attribute type
  - Data type – types of data: TrueFalse, DateTime, Decimal, Integer, Text
  - Currency – currency value
  - Currency – currency code
  - Referenced attribute – to which existing attribute is referenced to
  - Boolean – attribute value, when the attribute data type is Boolean (possible values are True, False)
  - DateTime – attribute value, when the attribute data type is DateTime
  - Float – attribute value, when the attribute data type is Decimal (numerical data with decimal values)
  - Integer value – attribute value, when the attribute data type is Integer (numerical data without decimal)
  - Text – attribute value, when the attribute data type is Text
  - Unit of measure
- Batch number (Tracking dimension)
- Inventory dimension ID
- Warehouse (Storage dimension)
- Serial number (Tracking dimension)
- Site (Storage dimension)
- Item number
- Modified date and time
- On order*
- Ordered in total*
- Physical inventory*
- Picked*
- Ordered reserved*
- Physical reserved – when inventory is reserved through Sales order, correlation to the project and belonging quantity is exposed:
  - Project ID – project that reserves the inventory
  - Quantity – quantity that is reserved for a specific project (marked with the opposite sign
- Project allocation (Tracking dimension)
- Location (Storage dimension)

*More detailed description about OnHand Inventory is explained in Microsoft documentation (https://docs.microsoft.com/en-us/dynamics365/supply-chain/inventory/inventory-on-hand-list).

