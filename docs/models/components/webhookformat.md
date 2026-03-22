# WebhookFormat

## Example Usage

```ruby
require "spaire"

value = WebhookFormat::RAW

# Open enum: use .deserialize() to create instances from custom string values
custom = WebhookFormat.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `RAW`     | raw       |
| `DISCORD` | discord   |
| `SLACK`   | slack     |