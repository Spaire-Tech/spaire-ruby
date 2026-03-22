# TokenType

## Example Usage

```ruby
require "spaire"

value = TokenType::ACCESS_TOKEN

# Open enum: use .deserialize() to create instances from custom string values
custom = TokenType.deserialize("custom_value")
```


## Values

| Name            | Value           |
| --------------- | --------------- |
| `ACCESS_TOKEN`  | access_token    |
| `REFRESH_TOKEN` | refresh_token   |