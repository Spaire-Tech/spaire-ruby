# DisputeStatus

## Example Usage

```ruby
require "spaire"

value = DisputeStatus::PREVENTED

# Open enum: use .deserialize() to create instances from custom string values
custom = DisputeStatus.deserialize("custom_value")
```


## Values

| Name             | Value            |
| ---------------- | ---------------- |
| `PREVENTED`      | prevented        |
| `EARLY_WARNING`  | early_warning    |
| `NEEDS_RESPONSE` | needs_response   |
| `UNDER_REVIEW`   | under_review     |
| `LOST`           | lost             |
| `WON`            | won              |