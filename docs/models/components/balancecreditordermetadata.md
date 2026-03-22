# BalanceCreditOrderMetadata


## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `order_id`            | *::String*            | :heavy_check_mark:    | N/A                   |
| `product_id`          | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `subscription_id`     | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `amount`              | *::Integer*           | :heavy_check_mark:    | N/A                   |
| `currency`            | *::String*            | :heavy_check_mark:    | N/A                   |
| `tax_amount`          | *::Integer*           | :heavy_check_mark:    | N/A                   |
| `tax_state`           | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `tax_country`         | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `fee`                 | *::Integer*           | :heavy_check_mark:    | N/A                   |