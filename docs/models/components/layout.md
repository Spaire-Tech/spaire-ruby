# Layout

## Example Usage

```ruby
require "spaire"

value = Layout::CLASSIC

# Open enum: use .deserialize() to create instances from custom string values
custom = Layout.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `CLASSIC`    | classic      |
| `CAROUSEL`   | carousel     |
| `IMAGE_GRID` | image_grid   |
| `CARD`       | card         |