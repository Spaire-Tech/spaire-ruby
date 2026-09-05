# Kind

What `id` refers to: a product, a storefront_links entry, or a form.

## Example Usage

```ruby
require "spaire"

value = Kind::PRODUCT

# Open enum: use .deserialize() to create instances from custom string values
custom = Kind.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `PRODUCT` | product   |
| `LINK`    | link      |
| `FORM`    | form      |