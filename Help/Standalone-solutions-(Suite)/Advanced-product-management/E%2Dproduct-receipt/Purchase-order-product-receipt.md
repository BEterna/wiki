## Export
____
A new button »Export« has been added to the Purchase order product receipt form . Upon clicking the button, a template in an excel format gets downloaded to the computer including the data from the purchase orders (Vendor account, Purchase order no., Line number, Storage dimensions if they were specified on the PO).

See columns supported in the template.

- If a line has an item followed by a serial tracking dimension and a quantity > 1, such a line in the export file is split into several lines with a quantity of 1.
- If a row has an item followed by serial or/and batch number, additional three columns are exported for the technical attributes (Attribute type name, Attribute name, Attribute value). Attribute type name and attribute name get filled out with values based on the set up in the procurement category. The third column is to be filled in with value of the attribute.

## Import
___
A new button »Import« has been added to the Purchase order product receipt form. 

Upon import of previously exported template system performs complete registration of the imported lines.

- When importing data all the controls that apply during standard registration are also performed.
- Successfully imported template is then added to the document as an attachment.
- If the template contains batches, they get automatically created in the system.

### Controls upon import: 
- Standard controls that apply to manual entry are performed. 
- In case of entering dimensions by which the product is not tracked -  the value is ignored.
- If the user manually adds columns for attributes (required or non-required), import of such values is ignored.
- Under and overdelivery is allowed based on the item set up. 
- If error is presented upon import of the template, no data is imported. 

