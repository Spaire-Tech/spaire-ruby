# CustomerCancellationReason

## Example Usage

```ruby
require "spaire"

value = CustomerCancellationReason::CUSTOMER_SERVICE

# Open enum: use .deserialize() to create instances from custom string values
custom = CustomerCancellationReason.deserialize("custom_value")
```


## Values

| Name               | Value              |
| ------------------ | ------------------ |
| `CUSTOMER_SERVICE` | customer_service   |
| `LOW_QUALITY`      | low_quality        |
| `MISSING_FEATURES` | missing_features   |
| `SWITCHED_SERVICE` | switched_service   |
| `TOO_COMPLEX`      | too_complex        |
| `TOO_EXPENSIVE`    | too_expensive      |
| `UNUSED`           | unused             |
| `OTHER`            | other              |