# DiscountType

## Example Usage

```ruby
require "spaire"

value = DiscountType::FIXED

# Open enum: use .deserialize() to create instances from custom string values
custom = DiscountType.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `FIXED`      | fixed        |
| `PERCENTAGE` | percentage   |