# MetricType

## Example Usage

```ruby
require "spaire"

value = MetricType::SCALAR

# Open enum: use .deserialize() to create instances from custom string values
custom = MetricType.deserialize("custom_value")
```


## Values

| Name                | Value               |
| ------------------- | ------------------- |
| `SCALAR`            | scalar              |
| `CURRENCY`          | currency            |
| `CURRENCY_SUB_CENT` | currency_sub_cent   |
| `PERCENTAGE`        | percentage          |