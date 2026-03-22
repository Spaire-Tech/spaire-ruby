# RefundStatus

## Example Usage

```ruby
require "spaire"

value = RefundStatus::PENDING

# Open enum: use .deserialize() to create instances from custom string values
custom = RefundStatus.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `PENDING`   | pending     |
| `SUCCEEDED` | succeeded   |
| `FAILED`    | failed      |
| `CANCELED`  | canceled    |