# CommunityEventPublicType

## Example Usage

```ruby
require "spaire"

value = CommunityEventPublicType::WORKSHOP

# Open enum: use .deserialize() to create instances from custom string values
custom = CommunityEventPublicType.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `WORKSHOP` | workshop   |
| `OFFICE`   | office     |
| `COHORT`   | cohort     |
| `GUEST`    | guest      |