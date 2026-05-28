# CommunityPostMediaCreate

One attachment on a new post.

Image branch: client uploaded a File via the
  community_post_image service first, passes the file_id here.
  Up to 4 image rows per post, positioned 0..3.

Video branch (Phase 3A): client created a Mux direct upload via
  POST /media/mux-upload, the browser PUT the bytes to Mux, then
  passes `mux_upload_id` here. Exactly one video per post.


## Fields

| Field                                                                                                                        | Type                                                                                                                         | Required                                                                                                                     | Description                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `media_type`                                                                                                                 | [T.nilable(Models::Components::CommunityPostMediaCreateMediaType)](../../models/shared/communitypostmediacreatemediatype.md) | :heavy_minus_sign:                                                                                                           | N/A                                                                                                                          |
| `file_id`                                                                                                                    | *T.nilable(::String)*                                                                                                        | :heavy_minus_sign:                                                                                                           | N/A                                                                                                                          |
| `mux_upload_id`                                                                                                              | *T.nilable(::String)*                                                                                                        | :heavy_minus_sign:                                                                                                           | N/A                                                                                                                          |
| `position`                                                                                                                   | *T.nilable(::Integer)*                                                                                                       | :heavy_minus_sign:                                                                                                           | N/A                                                                                                                          |