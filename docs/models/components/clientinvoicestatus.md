# ClientInvoiceStatus

## Example Usage

```ruby
require "spaire"

value = ClientInvoiceStatus::DRAFT

# Open enum: use .deserialize() to create instances from custom string values
custom = ClientInvoiceStatus.deserialize("custom_value")
```


## Values

| Name            | Value           |
| --------------- | --------------- |
| `DRAFT`         | draft           |
| `OPEN`          | open            |
| `PAID`          | paid            |
| `VOID`          | void            |
| `UNCOLLECTIBLE` | uncollectible   |