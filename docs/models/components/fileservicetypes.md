# FileServiceTypes

## Example Usage

```ruby
require "spaire"

value = FileServiceTypes::DOWNLOADABLE

# Open enum: use .deserialize() to create instances from custom string values
custom = FileServiceTypes.deserialize("custom_value")
```


## Values

| Name                  | Value                 |
| --------------------- | --------------------- |
| `DOWNLOADABLE`        | downloadable          |
| `PRODUCT_MEDIA`       | product_media         |
| `ORGANIZATION_AVATAR` | organization_avatar   |
| `STOREFRONT_HEADER`   | storefront_header     |