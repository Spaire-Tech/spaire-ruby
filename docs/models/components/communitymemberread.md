# CommunityMemberRead

One row in the Members tab. The instructor is included as a
synthetic first entry (kind='instructor', id=user_id). Students are
one-per-enrollment, keyed by enrollment_id.


## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `id`                                                                                          | *::String*                                                                                    | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `kind`                                                                                        | [Models::Components::CommunityMemberReadKind](../../models/shared/communitymemberreadkind.md) | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `name`                                                                                        | *T.nilable(::String)*                                                                         | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `avatar_url`                                                                                  | *T.nilable(::String)*                                                                         | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `joined_at`                                                                                   | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)                          | :heavy_check_mark:                                                                            | N/A                                                                                           |