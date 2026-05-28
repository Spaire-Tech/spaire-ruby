# CommunityCourseSummary

One row in the customer-portal picker. `community_enabled` is
false when the creator hasn't enabled the feed for this course yet
(or the settings row doesn't exist at all).


## Fields

| Field                              | Type                               | Required                           | Description                        |
| ---------------------------------- | ---------------------------------- | ---------------------------------- | ---------------------------------- |
| `course_id`                        | *::String*                         | :heavy_check_mark:                 | N/A                                |
| `course_title`                     | *T.nilable(::String)*              | :heavy_check_mark:                 | N/A                                |
| `course_thumbnail_url`             | *T.nilable(::String)*              | :heavy_check_mark:                 | N/A                                |
| `course_thumbnail_object_position` | *T.nilable(::String)*              | :heavy_check_mark:                 | N/A                                |
| `community_enabled`                | *T::Boolean*                       | :heavy_check_mark:                 | N/A                                |