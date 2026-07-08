# CommunityEventRsvpResult

Returned from POST/DELETE /events/{id}/rsvp — the new state plus
the updated counter so the UI doesn't need a second fetch.


## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `going`            | *T::Boolean*       | :heavy_check_mark: | N/A                |
| `rsvp_count`       | *::Integer*        | :heavy_check_mark: | N/A                |