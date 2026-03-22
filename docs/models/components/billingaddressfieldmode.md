# BillingAddressFieldMode

## Example Usage

```ruby
require "spaire"

value = BillingAddressFieldMode::REQUIRED

# Open enum: use .deserialize() to create instances from custom string values
custom = BillingAddressFieldMode.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `REQUIRED` | required   |
| `OPTIONAL` | optional   |
| `DISABLED` | disabled   |