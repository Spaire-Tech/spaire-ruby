# Status

## Example Usage

```ruby
require "spaire"

value = Status::ACTIVE

# Open enum: use .deserialize() to create instances from custom string values
custom = Status.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `ACTIVE`   | active     |
| `TRIALING` | trialing   |