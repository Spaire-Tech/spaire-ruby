# Visibility

## Example Usage

```ruby
require "spaire"

value = Visibility::COHORT

# Open enum: use .deserialize() to create instances from custom string values
custom = Visibility.deserialize("custom_value")
```


## Values

| Name     | Value    |
| -------- | -------- |
| `COHORT` | cohort   |
| `ALL`    | all      |
| `INSTR`  | instr    |