# BodyFormat

## Example Usage

```ruby
require "spaire"

value = BodyFormat::MARKDOWN

# Open enum: use .deserialize() to create instances from custom string values
custom = BodyFormat.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `MARKDOWN` | markdown   |
| `PLAIN`    | plain      |