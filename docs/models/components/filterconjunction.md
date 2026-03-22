# FilterConjunction

## Example Usage

```ruby
require "spaire"

value = FilterConjunction::AND

# Open enum: use .deserialize() to create instances from custom string values
custom = FilterConjunction.deserialize("custom_value")
```


## Values

| Name  | Value |
| ----- | ----- |
| `AND` | and   |
| `OR`  | or    |