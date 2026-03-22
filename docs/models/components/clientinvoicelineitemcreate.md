# ClientInvoiceLineItemCreate


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `description`                                          | *::String*                                             | :heavy_check_mark:                                     | Line item description shown on the invoice.            |
| `quantity`                                             | *T.nilable(::Integer)*                                 | :heavy_minus_sign:                                     | Quantity.                                              |
| `unit_amount`                                          | *::Integer*                                            | :heavy_check_mark:                                     | Unit price in the smallest currency unit (e.g. cents). |