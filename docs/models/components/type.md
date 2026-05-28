# Type

Link type

## Example Usage

```ruby
require "spaire"

value = Type::STANDARD

# Open enum: use .deserialize() to create instances from custom string values
custom = Type.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `STANDARD` | standard   |
| `EMBEDDED` | embedded   |