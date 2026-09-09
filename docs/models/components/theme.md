# Theme

Color theme for the public storefront

## Example Usage

```ruby
require "spaire"

value = Theme::LIGHT

# Open enum: use .deserialize() to create instances from custom string values
custom = Theme.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `LIGHT` | light   |
| `DARK`  | dark    |