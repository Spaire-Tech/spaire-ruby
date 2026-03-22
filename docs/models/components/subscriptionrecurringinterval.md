# SubscriptionRecurringInterval

## Example Usage

```ruby
require "spaire"

value = SubscriptionRecurringInterval::DAY

# Open enum: use .deserialize() to create instances from custom string values
custom = SubscriptionRecurringInterval.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `DAY`   | day     |
| `WEEK`  | week    |
| `MONTH` | month   |
| `YEAR`  | year    |