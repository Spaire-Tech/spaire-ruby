# CommunityEventReadType

## Example Usage

```ruby
require "spaire"

value = CommunityEventReadType::WORKSHOP

# Open enum: use .deserialize() to create instances from custom string values
custom = CommunityEventReadType.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `WORKSHOP` | workshop   |
| `OFFICE`   | office     |
| `COHORT`   | cohort     |
| `GUEST`    | guest      |