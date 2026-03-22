# ProductPriceSource

## Example Usage

```ruby
require "spaire"

value = ProductPriceSource::CATALOG

# Open enum: use .deserialize() to create instances from custom string values
custom = ProductPriceSource.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `CATALOG` | catalog   |
| `AD_HOC`  | ad_hoc    |