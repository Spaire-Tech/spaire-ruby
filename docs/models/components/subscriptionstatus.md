# SubscriptionStatus

## Example Usage

```ruby
require "spaire"

value = SubscriptionStatus::INCOMPLETE

# Open enum: use .deserialize() to create instances from custom string values
custom = SubscriptionStatus.deserialize("custom_value")
```


## Values

| Name                 | Value                |
| -------------------- | -------------------- |
| `INCOMPLETE`         | incomplete           |
| `INCOMPLETE_EXPIRED` | incomplete_expired   |
| `TRIALING`           | trialing             |
| `ACTIVE`             | active               |
| `PAST_DUE`           | past_due             |
| `CANCELED`           | canceled             |
| `UNPAID`             | unpaid               |