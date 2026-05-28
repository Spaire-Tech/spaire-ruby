# FeaturedMode

How to choose which products appear on the storefront. 'curated' (default) shows only the products the creator explicitly added via featured_product_ids. 'all' is a legacy mode that auto-shows every active product; kept so existing rows still validate.

## Example Usage

```ruby
require "spaire"

value = FeaturedMode::ALL

# Open enum: use .deserialize() to create instances from custom string values
custom = FeaturedMode.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `ALL`     | all       |
| `CURATED` | curated   |