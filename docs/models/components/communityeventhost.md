# CommunityEventHost

Lightweight host identity. The host is always the course owner
(an org-side User) — we surface the display name from the course's
`instructor_name` (set in course settings) and fall back to the
user's name/email if it's unset.


## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `user_id`             | *::String*            | :heavy_check_mark:    | N/A                   |
| `name`                | *::String*            | :heavy_check_mark:    | N/A                   |
| `avatar_url`          | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |