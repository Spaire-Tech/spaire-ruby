# SubType

## Example Usage

```ruby
require "spaire"

value = SubType::USER

# Open enum: use .deserialize() to create instances from custom string values
custom = SubType.deserialize("custom_value")
```


## Values

| Name           | Value          |
| -------------- | -------------- |
| `USER`         | user           |
| `ORGANIZATION` | organization   |