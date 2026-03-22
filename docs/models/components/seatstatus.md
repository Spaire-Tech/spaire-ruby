# SeatStatus

## Example Usage

```ruby
require "spaire"

value = SeatStatus::PENDING

# Open enum: use .deserialize() to create instances from custom string values
custom = SeatStatus.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `PENDING` | pending   |
| `CLAIMED` | claimed   |
| `REVOKED` | revoked   |