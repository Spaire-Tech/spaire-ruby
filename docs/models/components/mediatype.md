# MediaType

## Example Usage

```ruby
require "spaire"

value = MediaType::IMAGE

# Open enum: use .deserialize() to create instances from custom string values
custom = MediaType.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `IMAGE` | image   |
| `VIDEO` | video   |