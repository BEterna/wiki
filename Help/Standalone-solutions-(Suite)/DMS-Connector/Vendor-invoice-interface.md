# **Vendor invoice interface**

The header of a pending vendor invoice can be created with OData call using the entity VendorInvoiceHeaders. External DMS ID must be provided within the OData call, if we expect that the process of the invoice, after it was created in D365FO, should be tracked also by the external DMS. In these cases DMS ID must be unique within D365FO. It enables mapping of the invoice document in D365FO and the invoice document in external document management system.

Check [Postman collection examples](https://documenter.getpostman.com/view/11980146/2sA3Qv7Vjc)