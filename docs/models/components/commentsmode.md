# CommentsMode

## Example Usage

```ruby
require "spaire"

value = CommentsMode::VISIBLE

# Open enum: use .deserialize() to create instances from custom string values
custom = CommentsMode.deserialize("custom_value")
```


## Values

| Name      | Value     |
| --------- | --------- |
| `VISIBLE` | visible   |
| `HIDDEN`  | hidden    |
| `LOCKED`  | locked    |