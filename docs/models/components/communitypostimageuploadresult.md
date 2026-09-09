# CommunityPostImageUploadResult

Returned by the image upload endpoint so the composer can stash
the file_id alongside the local image preview, then include it in
the post create payload.


## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `file_id`          | *::String*         | :heavy_check_mark: | N/A                |
| `public_url`       | *::String*         | :heavy_check_mark: | N/A                |
| `size`             | *::Integer*        | :heavy_check_mark: | N/A                |
| `mime_type`        | *::String*         | :heavy_check_mark: | N/A                |