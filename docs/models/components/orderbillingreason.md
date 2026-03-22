# OrderBillingReason

## Example Usage

```ruby
require "spaire"

value = OrderBillingReason::PURCHASE

# Open enum: use .deserialize() to create instances from custom string values
custom = OrderBillingReason.deserialize("custom_value")
```


## Values

| Name                  | Value                 |
| --------------------- | --------------------- |
| `PURCHASE`            | purchase              |
| `SUBSCRIPTION_CREATE` | subscription_create   |
| `SUBSCRIPTION_CYCLE`  | subscription_cycle    |
| `SUBSCRIPTION_UPDATE` | subscription_update   |
| `CLIENT_INVOICE`      | client_invoice        |