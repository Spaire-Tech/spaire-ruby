# TaxBehaviorOption

## Example Usage

```ruby
require "spaire"

value = TaxBehaviorOption::LOCATION

# Open enum: use .deserialize() to create instances from custom string values
custom = TaxBehaviorOption.deserialize("custom_value")
```


## Values

| Name        | Value       |
| ----------- | ----------- |
| `LOCATION`  | location    |
| `INCLUSIVE` | inclusive   |
| `EXCLUSIVE` | exclusive   |