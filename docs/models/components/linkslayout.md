# LinksLayout

Visual layout for the links section

## Example Usage

```ruby
require "spaire"

value = LinksLayout::CLASSIC

# Open enum: use .deserialize() to create instances from custom string values
custom = LinksLayout.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `CLASSIC`    | classic      |
| `CAROUSEL`   | carousel     |
| `IMAGE_GRID` | image_grid   |
| `CARD`       | card         |