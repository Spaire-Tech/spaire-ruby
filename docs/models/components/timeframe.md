# Timeframe

## Example Usage

```ruby
require "spaire"

value = Timeframe::YEAR

# Open enum: use .deserialize() to create instances from custom string values
custom = Timeframe.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `YEAR`  | year    |
| `MONTH` | month   |
| `DAY`   | day     |