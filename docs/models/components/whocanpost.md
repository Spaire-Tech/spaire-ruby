# WhoCanPost

## Example Usage

```ruby
require "spaire"

value = WhoCanPost::EVERYONE

# Open enum: use .deserialize() to create instances from custom string values
custom = WhoCanPost.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `EVERYONE` | everyone   |
| `APPROVED` | approved   |