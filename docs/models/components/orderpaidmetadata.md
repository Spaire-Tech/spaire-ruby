# OrderPaidMetadata


## Fields

| Field                      | Type                       | Required                   | Description                |
| -------------------------- | -------------------------- | -------------------------- | -------------------------- |
| `order_id`                 | *::String*                 | :heavy_check_mark:         | N/A                        |
| `product_id`               | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `billing_type`             | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `amount`                   | *::Integer*                | :heavy_check_mark:         | N/A                        |
| `currency`                 | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `net_amount`               | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |
| `tax_amount`               | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |
| `applied_balance_amount`   | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |
| `discount_amount`          | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |
| `discount_id`              | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `platform_fee`             | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |
| `subscription_id`          | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `recurring_interval`       | *T.nilable(::String)*      | :heavy_minus_sign:         | N/A                        |
| `recurring_interval_count` | *T.nilable(::Integer)*     | :heavy_minus_sign:         | N/A                        |