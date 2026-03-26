# ClientInvoiceLineItemPreview

Relaxed line item for preview — allows zero amounts for in-progress editing.


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `description`                                | *T.nilable(::String)*                        | :heavy_minus_sign:                           | Line item description.                       |
| `quantity`                                   | *T.nilable(::Integer)*                       | :heavy_minus_sign:                           | Quantity.                                    |
| `unit_amount`                                | *T.nilable(::Integer)*                       | :heavy_minus_sign:                           | Unit price in cents (0 allowed for preview). |