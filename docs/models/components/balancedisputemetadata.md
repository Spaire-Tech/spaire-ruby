# BalanceDisputeMetadata


## Fields

| Field                  | Type                   | Required               | Description            |
| ---------------------- | ---------------------- | ---------------------- | ---------------------- |
| `transaction_id`       | *::String*             | :heavy_check_mark:     | N/A                    |
| `dispute_id`           | *::String*             | :heavy_check_mark:     | N/A                    |
| `order_id`             | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `order_created_at`     | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `product_id`           | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `subscription_id`      | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `amount`               | *::Integer*            | :heavy_check_mark:     | N/A                    |
| `currency`             | *::String*             | :heavy_check_mark:     | N/A                    |
| `presentment_amount`   | *::Integer*            | :heavy_check_mark:     | N/A                    |
| `presentment_currency` | *::String*             | :heavy_check_mark:     | N/A                    |
| `tax_amount`           | *::Integer*            | :heavy_check_mark:     | N/A                    |
| `tax_state`            | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `tax_country`          | *T.nilable(::String)*  | :heavy_minus_sign:     | N/A                    |
| `fee`                  | *::Integer*            | :heavy_check_mark:     | N/A                    |