# LinksPosition

DEPRECATED — use block_order. Where to show the links section relative to products. Kept so existing rows still validate.

## Example Usage

```ruby
require "spaire"

value = LinksPosition::BEFORE_PRODUCTS

# Open enum: use .deserialize() to create instances from custom string values
custom = LinksPosition.deserialize("custom_value")
```


## Values

| Name              | Value             |
| ----------------- | ----------------- |
| `BEFORE_PRODUCTS` | before_products   |
| `AFTER_PRODUCTS`  | after_products    |