# DiscountDuration

## Example Usage

```ruby
require "spaire"

value = DiscountDuration::ONCE

# Open enum: use .deserialize() to create instances from custom string values
custom = DiscountDuration.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `ONCE`      | once        |
| `FOREVER`   | forever     |
| `REPEATING` | repeating   |