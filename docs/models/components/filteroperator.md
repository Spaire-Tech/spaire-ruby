# FilterOperator

## Example Usage

```ruby
require "spaire"

value = FilterOperator::EQ

# Open enum: use .deserialize() to create instances from custom string values
custom = FilterOperator.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `EQ`       | eq         |
| `NE`       | ne         |
| `GT`       | gt         |
| `GTE`      | gte        |
| `LT`       | lt         |
| `LTE`      | lte        |
| `LIKE`     | like       |
| `NOT_LIKE` | not_like   |