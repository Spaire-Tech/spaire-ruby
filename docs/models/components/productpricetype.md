# ProductPriceType

## Example Usage

```ruby
require "spaire"

value = ProductPriceType::ONE_TIME

# Open enum: use .deserialize() to create instances from custom string values
custom = ProductPriceType.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `ONE_TIME`  | one_time    |
| `RECURRING` | recurring   |