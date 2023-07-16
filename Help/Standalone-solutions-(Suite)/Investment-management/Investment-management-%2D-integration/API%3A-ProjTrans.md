ProjTrans API provides the retrieval of all posted project transaction or posted project transaction for specific project that were modified after a selected date. The list of posted project transaction in D365FO is located in _Project management and accounting > Transactions > Posted project transaction_. Response of this API includes the following relevant data that are part of each posted project transaction:
- Transaction Id - Posted project transaction id
- Modified date and time
- Transaction description
- Accounting currency
- Total cost amount in accounting currency
- Transaction sales currency
- Total sales amount in transaction currency
- Total sales amount in accounting currency
- Line property Id
- Project ID
- Total cost amount in transaction currency
- Project transaction external reference ID - Unique ID of project transaction record from the 3rd party system and it is populated only for transactions of type item, cost or hour. It is taken from staging tables for item, cost and hour consumption located in _Project management and accounting > Inquiries and reports > Investment management_
- Financial dimensions
- Project category Id
- Transaction cost currency
- Transaction invoice status 
- Transaction type
- Date
- Quantity

Some data in the output are populated according to transaction type:
1. Transaction type = Hour
- Worker Personnel Number
- Worker name and surname
2. Transaction type = Item
- Item number
- Item serial number
3. Transaction type = Cost (Expense)
- Technical asset - It is taken from staging table for item, located in _Project management and accounting > Inquiries and reports > Investment management > Project item consumption (external)_

