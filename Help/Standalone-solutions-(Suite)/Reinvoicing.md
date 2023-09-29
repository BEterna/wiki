Reinvoicing is a very common transaction, which consists in shifting the costs incurred by the company onto another entity. The purpose of Reinvoicing is to transfer the costs incurred by the reinvoicing entity onto the entity that actually used the given services. 

The "re-invoice" is therefore a simple VAT invoice issued by an intermediary between the relevant service provider and the actual buyer of this service.

## **Setup**
---
### Allocation keys

With this functionality users can create allocation keys and distribute re-invoiced amount to customers according to predefined allocation key template.

On the allocation key default template, user can create and name a new template and then under **Allocation percentage** chooses **Percentage amount** and related **Customer account** for chosen percent.

If a user chooses the option for default template, when a particular template will be selected under Template name, lines will be applied automatically based on the setup created on the template.

Allocation template setup can be accessed in a few ways: 
1. **Accounts receivable > Setup > Allocation key default template**: 
   - Create a new Allocation percentage by distributing percentage amount to customer account.  
   - Click New and enter allocation rules - select Customer account and specify Amount/Percent (% in case that value Percent was selected or amount in case that value Amount was selected in Percentage/Amount field). 
   - Total percent of allocated amount is displayed below.

2. **Accounts payable > Setup > Allocation key default template** 
   - Create a new Allocation percentage by distributing percentage amount to customer account.  
   - Click New and enter allocation rules - select Customer account and specify Amount/Percent (% in case that value Percent was selected or amount in case that value Amount was selected in Percentage/Amount field). 
   - Total percent of allocated amount is displayed below.

## **Processing re-invoicing**
---
### OPTION 1: Allocate Pending vendor invoice (not posted invoices) to one or multiple Sales orders
1. Create new Pending Vendor invoice in **Accounts payable > Invoices > Pending Vendor invoices** or select existing not posted one. At least invoice number and lines must be applied.
2. Select option **Create sales order** in Action Pane.
3. New form with Lines from the invoice will open. 
4. Mark the lines which should be re-invoiced (column 'Include'). One or multiple lines can be selected.
5. Select option **Allocation key** at the top. NOTE: In case that the lines were already allocated the system will show warning 'Sales line for this invoice already exists.' 
6. Select the value in **Distributed by** field: this value defines how the line will be allocated – by percentage (x% of the value) or Amount (fixed amount can be entered eg. 500€)
7. Select the value under **Field**: this value defines which value will be split – Quantity (eg. 10h) or Amount (500€).
8. If the options **Distributed by: Percent** and **Field: Amount** are selected, user has additional option - **Template name**. This option enables user to choose a predefined allocation key template. 
   - Allocation template setup can be accessed in three ways: 
       - Accounts receivable > Setup > **Allocation key default template**
       - Accounts payable > Setup > **Allocation key default template** or
       - Right click on the template name drop down and select option **View details** 
    - If a user chooses the option for default template, when a particular template will be         selected under Template name, lines will be applied automatically based on the setup created   on the template.
9. In the options **Distributed by: Percentage** and **Field: Quantity** are selected, as a result, user has an option to manually allocate quantity to customers. 
e.g. 40% of the quantity will be reinvoiced to the customer DE-012, 35% of the quantity to the customer DE-011 and 25% to the customer DE-010.
10. Click OK. Allocated lines are created according to defined allocation key. 
11. Select the lines with value in Customer account field and click **Validate**. All lines will be validated, and Message will be returned. In case of validation errors, all errors should be corrected before continuing to next step. 
12. Click OK. As result, one or multiple Sales orders will be created. Message with Sales orders numbers will appear. In cases where intercompany customer will be selected, related Purchase order will also be created.
13. In case of related intercompany Purchase orders project ID needs to be selected on the purchase order header: 
   - Go to Accounts payable > Purchase orders > All purchase orders and select purchase order.
   - Select function **Change project ID** under Purchase order tab.
   - Enter project ID to which costs should be posted.


### OPTION 2: Allocate Invoice journal (posted invoices) to one or multiple Sales orders
