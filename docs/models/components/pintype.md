# PinType

## Example Usage

```ruby
require "spaire"

value = PinType::ANNOUNCEMENT

# Open enum: use .deserialize() to create instances from custom string values
custom = PinType.deserialize("custom_value")
```


## Values

| Name             | Value            |
| ---------------- | ---------------- |
| `ANNOUNCEMENT`   | announcement     |
| `PROMPT_OF_WEEK` | prompt_of_week   |
| `ACTIVITY`       | activity         |