# SubscriptionCanceledMetadata


## Fields

| Field                           | Type                            | Required                        | Description                     |
| ------------------------------- | ------------------------------- | ------------------------------- | ------------------------------- |
| `subscription_id`               | *::String*                      | :heavy_check_mark:              | N/A                             |
| `product_id`                    | *T.nilable(::String)*           | :heavy_minus_sign:              | N/A                             |
| `amount`                        | *::Integer*                     | :heavy_check_mark:              | N/A                             |
| `currency`                      | *::String*                      | :heavy_check_mark:              | N/A                             |
| `recurring_interval`            | *::String*                      | :heavy_check_mark:              | N/A                             |
| `recurring_interval_count`      | *::Integer*                     | :heavy_check_mark:              | N/A                             |
| `customer_cancellation_reason`  | *T.nilable(::String)*           | :heavy_minus_sign:              | N/A                             |
| `customer_cancellation_comment` | *T.nilable(::String)*           | :heavy_minus_sign:              | N/A                             |
| `canceled_at`                   | *::String*                      | :heavy_check_mark:              | N/A                             |
| `ends_at`                       | *T.nilable(::String)*           | :heavy_minus_sign:              | N/A                             |
| `cancel_at_period_end`          | *T.nilable(T::Boolean)*         | :heavy_minus_sign:              | N/A                             |