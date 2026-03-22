# CheckoutStatus

## Example Usage

```ruby
require "spaire"

value = CheckoutStatus::OPEN

# Open enum: use .deserialize() to create instances from custom string values
custom = CheckoutStatus.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `OPEN`      | open        |
| `EXPIRED`   | expired     |
| `CONFIRMED` | confirmed   |
| `SUCCEEDED` | succeeded   |
| `FAILED`    | failed      |