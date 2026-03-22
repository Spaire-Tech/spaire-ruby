# PaymentStatus

## Example Usage

```ruby
require "spaire"

value = PaymentStatus::PENDING

# Open enum: use .deserialize() to create instances from custom string values
custom = PaymentStatus.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `PENDING`   | pending     |
| `SUCCEEDED` | succeeded   |
| `FAILED`    | failed      |