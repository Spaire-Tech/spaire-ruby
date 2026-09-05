# SubmissionType

## Example Usage

```ruby
require "spaire"

value = SubmissionType::PHOTO

# Open enum: use .deserialize() to create instances from custom string values
custom = SubmissionType.deserialize("custom_value")
```


## Values

| Name    | Value   |
| ------- | ------- |
| `PHOTO` | photo   |
| `VIDEO` | video   |
| `TEXT`  | text    |
| `LINK`  | link    |