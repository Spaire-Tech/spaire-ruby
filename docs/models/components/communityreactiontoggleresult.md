# CommunityReactionToggleResult

Returned by the toggle endpoint so optimistic clients have a
server-confirmed state to settle on.

`reactions` is the authoritative per-emoji breakdown for this
target after the toggle — clients should replace their cached
`reactions` array with this value rather than mutating it in
place. `count` is the sum of `reactions[].count` and matches
`community_posts.reaction_count` for post targets.


## Fields

| Field                                                                                                               | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `emoji`                                                                                                             | [Models::Components::CommunityReactionToggleResultEmoji](../../models/shared/communityreactiontoggleresultemoji.md) | :heavy_check_mark:                                                                                                  | N/A                                                                                                                 |
| `active`                                                                                                            | *T::Boolean*                                                                                                        | :heavy_check_mark:                                                                                                  | N/A                                                                                                                 |
| `count`                                                                                                             | *::Integer*                                                                                                         | :heavy_check_mark:                                                                                                  | N/A                                                                                                                 |
| `reactions`                                                                                                         | T::Array<[Models::Components::CommunityReactionSummaryEntry](../../models/shared/communityreactionsummaryentry.md)> | :heavy_minus_sign:                                                                                                  | N/A                                                                                                                 |