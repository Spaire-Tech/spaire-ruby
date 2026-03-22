# LicenseKeyStatus

## Example Usage

```ruby
require "spaire"

value = LicenseKeyStatus::GRANTED

# Open enum: use .deserialize() to create instances from custom string values
custom = LicenseKeyStatus.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `GRANTED`  | granted    |
| `REVOKED`  | revoked    |
| `DISABLED` | disabled   |