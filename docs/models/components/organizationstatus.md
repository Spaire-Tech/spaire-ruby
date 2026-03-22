# OrganizationStatus

## Example Usage

```ruby
require "spaire"

value = OrganizationStatus::CREATED

# Open enum: use .deserialize() to create instances from custom string values
custom = OrganizationStatus.deserialize("custom_value")
```


## Values

| Name                 | Value                |
| -------------------- | -------------------- |
| `CREATED`            | created              |
| `ONBOARDING_STARTED` | onboarding_started   |
| `INITIAL_REVIEW`     | initial_review       |
| `ONGOING_REVIEW`     | ongoing_review       |
| `DENIED`             | denied               |
| `ACTIVE`             | active               |