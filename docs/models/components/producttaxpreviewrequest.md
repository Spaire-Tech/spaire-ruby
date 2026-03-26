# ProductTaxPreviewRequest

Request body for previewing tax on a product price.


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `amount`                                               | *::Integer*                                            | :heavy_check_mark:                                     | Amount in smallest currency unit (e.g. cents for USD). |
| `currency`                                             | *::String*                                             | :heavy_check_mark:                                     | ISO 4217 currency code (e.g. 'usd').                   |
| `country`                                              | *::String*                                             | :heavy_check_mark:                                     | ISO 3166-1 alpha-2 country code (e.g. 'AU').           |
| `quantity`                                             | *T.nilable(::Integer)*                                 | :heavy_minus_sign:                                     | Unit quantity for the preview calculation.             |
| `state`                                                | *T.nilable(::String)*                                  | :heavy_minus_sign:                                     | State/province code for US/CA (e.g. 'WA' or 'US-WA').  |