# EventType


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the object.                                                |
| `name`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | The name of the event type.                                          |
| `label`                                                              | *::String*                                                           | :heavy_check_mark:                                                   | The label for the event type.                                        |
| `label_property_selector`                                            | *T.nilable(::String)*                                                | :heavy_minus_sign:                                                   | Property path to extract dynamic label from event metadata.          |
| `organization_id`                                                    | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the organization owning the event type.                    |