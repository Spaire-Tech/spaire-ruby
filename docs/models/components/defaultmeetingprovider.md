# DefaultMeetingProvider

## Example Usage

```ruby
require "spaire"

value = DefaultMeetingProvider::ZOOM

# Open enum: use .deserialize() to create instances from custom string values
custom = DefaultMeetingProvider.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `ZOOM`  | zoom    |
| `MEET`  | meet    |
| `TEAMS` | teams   |
| `WEBEX` | webex   |
| `OTHER` | other   |