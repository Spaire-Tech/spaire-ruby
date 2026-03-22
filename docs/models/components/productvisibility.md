# ProductVisibility

## Example Usage

```ruby
require "spaire"

value = ProductVisibility::DRAFT

# Open enum: use .deserialize() to create instances from custom string values
custom = ProductVisibility.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `DRAFT`   | draft     |
| `PRIVATE` | private   |
| `PUBLIC`  | public    |