# CommunityAuthorStudent

Enrolled-student author. `enrollment_id` is the stable identity in
the community context; we don't surface customer_id here so the API
stays customer-PII-light.


## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `kind`                | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `enrollment_id`       | *::String*            | :heavy_check_mark:    | N/A                   |
| `name`                | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `avatar_url`          | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |