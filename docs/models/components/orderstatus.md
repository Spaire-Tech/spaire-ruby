# OrderStatus

## Example Usage

```ruby
require "spaire"

value = OrderStatus::PENDING

# Open enum: use .deserialize() to create instances from custom string values
custom = OrderStatus.deserialize("custom_value")
```


## Values

| Name                 | Value                |
| -------------------- | -------------------- |
| `PENDING`            | pending              |
| `PAID`               | paid                 |
| `REFUNDED`           | refunded             |
| `PARTIALLY_REFUNDED` | partially_refunded   |