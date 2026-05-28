# CommunityMemberReadKind

## Example Usage

```ruby
require "spaire"

value = CommunityMemberReadKind::INSTRUCTOR

# Open enum: use .deserialize() to create instances from custom string values
custom = CommunityMemberReadKind.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `INSTRUCTOR` | instructor   |
| `STUDENT`    | student      |