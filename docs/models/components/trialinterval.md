# TrialInterval

## Example Usage

```ruby
require "spaire"

value = TrialInterval::DAY

# Open enum: use .deserialize() to create instances from custom string values
custom = TrialInterval.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `DAY`   | day     |
| `WEEK`  | week    |
| `MONTH` | month   |
| `YEAR`  | year    |