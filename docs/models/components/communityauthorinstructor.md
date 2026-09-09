# CommunityAuthorInstructor

Creator/admin-side author. `user_id` is included so the client can
pair posts authored under the same instructor identity, e.g. to badge
them as "Instructor".


## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `kind`                | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `user_id`             | *::String*            | :heavy_check_mark:    | N/A                   |
| `name`                | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `avatar_url`          | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |