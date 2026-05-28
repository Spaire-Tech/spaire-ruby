# StorefrontLink


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `id`                                                                | *::String*                                                          | :heavy_check_mark:                                                  | Unique identifier for the link                                      |
| `url`                                                               | *::String*                                                          | :heavy_check_mark:                                                  | The URL of the link                                                 |
| `title`                                                             | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Display title for the link                                          |
| `description`                                                       | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Short description shown on the card                                 |
| `image_url`                                                         | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Thumbnail image URL for the link card                               |
| `type`                                                              | [T.nilable(Models::Components::Type)](../../models/shared/type.md)  | :heavy_minus_sign:                                                  | Link type                                                           |
| `platform`                                                          | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Detected platform (youtube, spotify, tiktok, soundcloud, instagram) |