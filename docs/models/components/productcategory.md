# ProductCategory

## Example Usage

```ruby
require "spaire"

value = ProductCategory::EBOOK

# Open enum: use .deserialize() to create instances from custom string values
custom = ProductCategory.deserialize("custom_value")
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `EBOOK`      | ebook        |
| `TEMPLATE`   | template     |
| `ASSETS`     | assets       |
| `COURSE`     | course       |
| `GUIDE`      | guide        |
| `MUSIC`      | music        |
| `VIDEO`      | video        |
| `PHOTO`      | photo        |
| `SOFTWARE`   | software     |
| `COACHING`   | coaching     |
| `MEMBERSHIP` | membership   |
| `OTHER`      | other        |