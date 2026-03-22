# MemberRole

## Example Usage

```ruby
require "spaire"

value = MemberRole::OWNER

# Open enum: use .deserialize() to create instances from custom string values
custom = MemberRole.deserialize("custom_value")
```


## Values

| Name              | Value             |
| ----------------- | ----------------- |
| `OWNER`           | owner             |
| `BILLING_MANAGER` | billing_manager   |
| `MEMBER`          | member            |