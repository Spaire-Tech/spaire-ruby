# CommunityReactionSummaryEntry

One emoji's row on a post or comment. `mine` is true when the
current viewer has reacted with this emoji.


## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `emoji`                                                   | [Models::Components::Emoji](../../models/shared/emoji.md) | :heavy_check_mark:                                        | N/A                                                       |
| `count`                                                   | *::Integer*                                               | :heavy_check_mark:                                        | N/A                                                       |
| `mine`                                                    | *T.nilable(T::Boolean)*                                   | :heavy_minus_sign:                                        | N/A                                                       |