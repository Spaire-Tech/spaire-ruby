# EventSource

## Example Usage

```ruby
require "spaire"

value = EventSource::SYSTEM

# Open enum: use .deserialize() to create instances from custom string values
custom = EventSource.deserialize("custom_value")
```


## Values

| Name     | Value    |
| -------- | -------- |
| `SYSTEM` | system   |
| `USER`   | user     |