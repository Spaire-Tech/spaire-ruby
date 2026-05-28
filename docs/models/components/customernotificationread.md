# CustomerNotificationRead


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  |
| `payload`                                                            | T::Hash[Symbol, *::Object*]                                          | :heavy_check_mark:                                                   | N/A                                                                  |
| `read_at`                                                            | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_minus_sign:                                                   | N/A                                                                  |