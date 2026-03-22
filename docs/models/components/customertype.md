# CustomerType

## Example Usage

```ruby
require "spaire"

value = CustomerType::INDIVIDUAL

# Open enum: use .deserialize() to create instances from custom string values
custom = CustomerType.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `INDIVIDUAL` | individual   |
| `TEAM`       | team         |