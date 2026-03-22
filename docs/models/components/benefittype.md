# BenefitType

## Example Usage

```ruby
require "spaire"

value = BenefitType::CUSTOM

# Open enum: use .deserialize() to create instances from custom string values
custom = BenefitType.deserialize("custom_value")
```


## Values

| Name                | Value               |
| ------------------- | ------------------- |
| `CUSTOM`            | custom              |
| `DISCORD`           | discord             |
| `GITHUB_REPOSITORY` | github_repository   |
| `DOWNLOADABLES`     | downloadables       |
| `LICENSE_KEYS`      | license_keys        |
| `METER_CREDIT`      | meter_credit        |