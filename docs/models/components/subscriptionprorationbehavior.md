# SubscriptionProrationBehavior

## Example Usage

```ruby
require "spaire"

value = SubscriptionProrationBehavior::INVOICE

# Open enum: use .deserialize() to create instances from custom string values
custom = SubscriptionProrationBehavior.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `INVOICE` | invoice   |
| `PRORATE` | prorate   |