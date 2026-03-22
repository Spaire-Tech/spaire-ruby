# RefundReason

## Example Usage

```ruby
require "spaire"

value = RefundReason::DUPLICATE

# Open enum: use .deserialize() to create instances from custom string values
custom = RefundReason.deserialize("custom_value")
```


## Values

| Name                     | Value                    |
| ------------------------ | ------------------------ |
| `DUPLICATE`              | duplicate                |
| `FRAUDULENT`             | fraudulent               |
| `CUSTOMER_REQUEST`       | customer_request         |
| `SERVICE_DISRUPTION`     | service_disruption       |
| `SATISFACTION_GUARANTEE` | satisfaction_guarantee   |
| `DISPUTE_PREVENTION`     | dispute_prevention       |
| `OTHER`                  | other                    |