## Export
___
A new button **»Export«** has been added to the Arrival overview journal (_Action pane> Functions > Export_). Upon clicking the button, a template in an excel format gets downloaded to the computer including the data from the purchase orders (Vendor account, Journal number, Line number, Storage dimensions if they were specified on the PO).

See columns supported in the template.

- If a line has an item followed by a serial tracking dimension and a quantity > 1, such a line in the export file is split into several lines with a quantity of 1.
- If a row has an item followed by serial or/and batch number, additional three columns are exported for the technical attributes (Attribute type name, Attribute name, Attribute value). Attribute type name and attribute name get filled out with values based on the set up in the procurement category. The third column is to be filled in with value of the attribute.

## Import
___
A new button **»Import«** has been added to the Arrival overview journal (_Action pane> Functions >Import_). 

Importing lines on the arrival overwiev performs only import of the data, journal has to be posted for lines to be regiters.
- Successfully imported templated is then added to the document as an attachment.
- If template contains batches, they get automatically created in the system.

### Controls upon import: 
- Standard controls that apply to manual entry are performed. 
- In case of entering dimensions by which the product is not tracked -  the value is ignored.
- If the user manually adds columns for attributes (required or non-required), import of such values is ignored.
- Under and overdelivery is allowed based on the item set up. 

