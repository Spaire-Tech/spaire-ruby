# CommunityPostVideoUploadResult

Returned by the Mux direct-upload endpoint. The browser PUTs
bytes straight to `upload_url`; the upload_id is what gets passed
back into the post-create payload. The Mux webhook later flips the
media row's mux_status to 'ready' and fills in playback details.


## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `upload_id`        | *::String*         | :heavy_check_mark: | N/A                |
| `upload_url`       | *::String*         | :heavy_check_mark: | N/A                |