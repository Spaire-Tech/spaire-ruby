# CommunityPostSortProperty

Feed sort options surfaced as the left-rail "Sort" list. Not a
free-form column sort — these are pre-baked queries the repository
knows how to apply.

## Example Usage

```ruby
require "spaire"

value = CommunityPostSortProperty::RECENT
```


## Values

| Name         | Value        |
| ------------ | ------------ |
| `RECENT`     | recent       |
| `TOP_WEEK`   | top_week     |
| `UNANSWERED` | unanswered   |