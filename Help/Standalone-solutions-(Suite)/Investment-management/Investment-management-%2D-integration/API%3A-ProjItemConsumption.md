ProjItemConsumption API enables 3rd party systems to create staging transactions in D365FO from which item project transactions are created by a D365FO batch job.

# Staging transactions
---
The staging transactions can be created or updated through ProjItemConsumption API in **Project item consumption** staging table, located under **Project management and accounting > Inquiries and reports > Investment management > Project item consumption (external)**. The API can insert records, when the External reference does not exist yet or update existing External reference with status None in staging table in the D365FO. 

After successful inserts or updates of records in the Project expense consumption staging table, an output is provided from D365FO to the 3rd party system. When inserts or updates fail, the error message is provided to the 3rd party system.

# Batch processing of staging transactions
---
The batch job Process project item consumption in D365FO Investment management package is in **Project management and accounting > Periodic > Investment management > Process project item consumption**.

With batch processing three use case scenarios are supported:
- When there is one or several existing open item requirements with a reserved physical inventory item that complies with the staging transaction, packing slips for these Item requirements are posted.
- When there are no open item requirements with a reserved physical inventory item, but there is an available inventory item that complies with the staging transaction, an Item journal is created in **Project management and accounting > Journals > Item**. Which journal name will be created, is defined in **Project management and accounting parameters > IM Integration > Project consumption > Item journal**. In this case the batch job applies the **Maximum line per journal** setup.
- When the staging transaction has a negative quantity Item returns of type Reverse are created in **Project management and accounting > Item tasks > Item returns**. 

When Item journals or Item returns are created, financial dimensions are defaulted from staging form **Project item consumption (external)**. If additional financial dimensions exist on project (for Item journals) or on original project transaction (for Item return), they are merged i the following way:

|  Dimesion value| Project/ Project transaction dimension value | Input dimension value |Dimension value in Item journal  |
|--|--|--|--|
| Dim1 |  A| D |D  | 
| Dim2 |  |  F|  F| 
| Dim3 |  |  |  | 
| Dim4 |  B|  |  B| 
| Dim5 |  |  S|  S| 
| Dim6 | K |  |  K| 

With batch processing several project transactions can be created for a single staging transaction. All created item project transaction ID are available in **Project item consumption** staging form (the lower half of the form shows all created project transactions related to the staging transaction that is selected in the upper half of the form).. 

Batch job considers only records with status **None**. Status of the selected records changes to **Transferred, Error or Posted**.  

Unsuccessfully processed staging transactions with an error can be reprocessed by manually resetting their status (click button Reset status in the **Project item consumption** staging form).

During the batch processing, Project category is validated. It can be defaulted first from Item and then from Default category setup located in **Project management and accounting > Setup > Project management and accounting parameters > Journals**. If not, the processing of Item consumption fails.
