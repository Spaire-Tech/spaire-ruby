# CustomerPortalCommunity

## Overview

### Available Operations

* [list_customer_communities](#list_customer_communities) - List Communities Available to Customer
* [get_settings_customer](#get_settings_customer) - Get Community Settings (Customer Portal)
* [list_members_customer](#list_members_customer) - List Community Members
* [list_tags_customer](#list_tags_customer) - List Community Tags
* [list_feed_customer](#list_feed_customer) - List Community Feed (Customer Portal)
* [create_video_upload_customer](#create_video_upload_customer) - Create Community Post Video Upload
* [upload_post_image](#upload_post_image) - Upload Community Post Image
* [create_post_customer](#create_post_customer) - Create Community Post
* [delete_post_customer](#delete_post_customer) - Delete Own Community Post
* [list_comments_customer](#list_comments_customer) - List Community Post Comments
* [create_comment_customer](#create_comment_customer) - Create Comment on Community Post
* [delete_comment_customer](#delete_comment_customer) - Delete Own Comment
* [react_to_post_customer](#react_to_post_customer) - Toggle Reaction on Community Post
* [react_to_comment_customer](#react_to_comment_customer) - Toggle Reaction on Community Comment
* [list_activities_customer](#list_activities_customer) - List Community Activities (Customer Portal)
* [list_submissions_customer](#list_submissions_customer) - List Submissions for Activity (Customer Portal)
* [submit_activity_customer](#submit_activity_customer) - Submit to Community Activity
* [list_submission_comments_customer](#list_submission_comments_customer) - List Submission Comments (Customer Portal)
* [create_submission_comment_customer](#create_submission_comment_customer) - Comment on a Submission (Customer Portal)
* [list_events_customer](#list_events_customer) - List Community Events (Customer Portal)
* [rsvp_event_customer](#rsvp_event_customer) - RSVP to Community Event
* [unrsvp_event_customer](#unrsvp_event_customer) - Cancel RSVP to Community Event

## list_customer_communities

Powers the /portal/community picker. Returns one entry per
enrolled course with `community_enabled` flagged from
community_settings, so the picker UI can filter to courses whose
creator has actually turned the feed on.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_customer_communities" method="get" path="/v1/customer-portal/community/courses" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_customer_communities(security: Models::Operations::CustomerPortalCommunityListCustomerCommunitiesSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.response_customer_portal_community_list_customer_communities.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                       | Type                                                                                                                                                            | Required                                                                                                                                                        | Description                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                      | [Models::Operations::CustomerPortalCommunityListCustomerCommunitiesSecurity](../../models/operations/customerportalcommunitylistcustomercommunitiessecurity.md) | :heavy_check_mark:                                                                                                                                              | The security requirements to use for the request.                                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListCustomerCommunitiesResponse)](../../models/operations/customerportalcommunitylistcustomercommunitiesresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_settings_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:get_settings_customer" method="get" path="/v1/customer-portal/community/{course_id}/settings" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.get_settings_customer(security: Models::Operations::CustomerPortalCommunityGetSettingsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.community_settings_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCommunityGetSettingsCustomerSecurity](../../models/operations/customerportalcommunitygetsettingscustomersecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `course_id`                                                                                                                                             | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityGetSettingsCustomerResponse)](../../models/operations/customerportalcommunitygetsettingscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_members_customer

Members tab on the customer-portal community surface. Mirrors the
creator endpoint but gates on enrollment + community-enabled, so a
student visiting a disabled course can't list peers.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_members_customer" method="get" path="/v1/customer-portal/community/{course_id}/members" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_members_customer(security: Models::Operations::CustomerPortalCommunityListMembersCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.response_customer_portal_community_list_members_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCommunityListMembersCustomerSecurity](../../models/operations/customerportalcommunitylistmemberscustomersecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `course_id`                                                                                                                                             | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListMembersCustomerResponse)](../../models/operations/customerportalcommunitylistmemberscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_tags_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_tags_customer" method="get" path="/v1/customer-portal/community/{course_id}/tags" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_tags_customer(security: Models::Operations::CustomerPortalCommunityListTagsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.response_customer_portal_community_list_tags_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalCommunityListTagsCustomerSecurity](../../models/operations/customerportalcommunitylisttagscustomersecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |
| `course_id`                                                                                                                                       | *::String*                                                                                                                                        | :heavy_check_mark:                                                                                                                                | N/A                                                                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListTagsCustomerResponse)](../../models/operations/customerportalcommunitylisttagscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_feed_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_feed_customer" method="get" path="/v1/customer-portal/community/{course_id}/feed" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Operations::CustomerPortalCommunityListFeedCustomerRequest.new(
  course_id: '<value>'
)
res = s.customer_portal_community.list_feed_customer(request: req, security: Models::Operations::CustomerPortalCommunityListFeedCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.list_resource_with_cursor_pagination_community_post_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                         | [Models::Operations::CustomerPortalCommunityListFeedCustomerRequest](../../models/operations/customerportalcommunitylistfeedcustomerrequest.md)   | :heavy_check_mark:                                                                                                                                | The request object to use for the request.                                                                                                        |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalCommunityListFeedCustomerSecurity](../../models/operations/customerportalcommunitylistfeedcustomersecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListFeedCustomerResponse)](../../models/operations/customerportalcommunitylistfeedcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_video_upload_customer

Mint a Mux direct-upload URL for a video community post. The
composer creates the upload, PUTs the file bytes to `upload_url`
directly from the browser, then includes `upload_id` in the
POST /posts payload as a media entry with media_type='video'.
The Mux webhook handler in course/endpoints.py flips the media
row from 'waiting' to 'ready' (with playback id + duration) once
encoding completes.

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:create_video_upload_customer" method="post" path="/v1/customer-portal/community/{course_id}/media/mux-upload" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.create_video_upload_customer(security: Models::Operations::CustomerPortalCommunityCreateVideoUploadCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.community_post_video_upload_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                           | Type                                                                                                                                                                | Required                                                                                                                                                            | Description                                                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                          | [Models::Operations::CustomerPortalCommunityCreateVideoUploadCustomerSecurity](../../models/operations/customerportalcommunitycreatevideouploadcustomersecurity.md) | :heavy_check_mark:                                                                                                                                                  | The security requirements to use for the request.                                                                                                                   |
| `course_id`                                                                                                                                                         | *::String*                                                                                                                                                          | :heavy_check_mark:                                                                                                                                                  | N/A                                                                                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityCreateVideoUploadCustomerResponse)](../../models/operations/customerportalcommunitycreatevideouploadcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## upload_post_image

Server-proxied image upload for the composer. Students don't
carry an org-write scope and so can't use the standard
/v1/files/ presigned flow — the bytes go through the server,
land in the community-post bucket, and a File row is created
owned by the course's organization. The returned file_id is
passed back in the POST /posts payload's `media[]`.

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:upload_post_image" method="post" path="/v1/customer-portal/community/{course_id}/media/upload" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.upload_post_image(security: Models::Operations::CustomerPortalCommunityUploadPostImageSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', body: Models::Components::BodyCustomerPortalCommunityUploadPostImage.new(
  file: Models::Components::File.new(
    file_name: 'example.file',
    content: File.binread('example.file')
  )
))

unless res.community_post_image_upload_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                       | Type                                                                                                                                            | Required                                                                                                                                        | Description                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                      | [Models::Operations::CustomerPortalCommunityUploadPostImageSecurity](../../models/operations/customerportalcommunityuploadpostimagesecurity.md) | :heavy_check_mark:                                                                                                                              | The security requirements to use for the request.                                                                                               |
| `course_id`                                                                                                                                     | *::String*                                                                                                                                      | :heavy_check_mark:                                                                                                                              | N/A                                                                                                                                             |
| `body`                                                                                                                                          | [Models::Components::BodyCustomerPortalCommunityUploadPostImage](../../models/shared/bodycustomerportalcommunityuploadpostimage.md)             | :heavy_check_mark:                                                                                                                              | N/A                                                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityUploadPostImageResponse)](../../models/operations/customerportalcommunityuploadpostimageresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_post_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:create_post_customer" method="post" path="/v1/customer-portal/community/{course_id}/posts" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.create_post_customer(security: Models::Operations::CustomerPortalCommunityCreatePostCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', body: Models::Components::CommunityPostCreate.new(
  body: '<value>'
))

unless res.community_post_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                            | [Models::Operations::CustomerPortalCommunityCreatePostCustomerSecurity](../../models/operations/customerportalcommunitycreatepostcustomersecurity.md) | :heavy_check_mark:                                                                                                                                    | The security requirements to use for the request.                                                                                                     |
| `course_id`                                                                                                                                           | *::String*                                                                                                                                            | :heavy_check_mark:                                                                                                                                    | N/A                                                                                                                                                   |
| `body`                                                                                                                                                | [Models::Components::CommunityPostCreate](../../models/shared/communitypostcreate.md)                                                                 | :heavy_check_mark:                                                                                                                                    | N/A                                                                                                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityCreatePostCustomerResponse)](../../models/operations/customerportalcommunitycreatepostcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_post_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:delete_post_customer" method="delete" path="/v1/customer-portal/community/{course_id}/posts/{post_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.delete_post_customer(security: Models::Operations::CustomerPortalCommunityDeletePostCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', post_id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                            | [Models::Operations::CustomerPortalCommunityDeletePostCustomerSecurity](../../models/operations/customerportalcommunitydeletepostcustomersecurity.md) | :heavy_check_mark:                                                                                                                                    | The security requirements to use for the request.                                                                                                     |
| `course_id`                                                                                                                                           | *::String*                                                                                                                                            | :heavy_check_mark:                                                                                                                                    | N/A                                                                                                                                                   |
| `post_id`                                                                                                                                             | *::String*                                                                                                                                            | :heavy_check_mark:                                                                                                                                    | N/A                                                                                                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityDeletePostCustomerResponse)](../../models/operations/customerportalcommunitydeletepostcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_comments_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_comments_customer" method="get" path="/v1/customer-portal/community/{course_id}/posts/{post_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_comments_customer(security: Models::Operations::CustomerPortalCommunityListCommentsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', post_id: '<value>')

unless res.response_customer_portal_community_list_comments_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                 | Type                                                                                                                                                      | Required                                                                                                                                                  | Description                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                | [Models::Operations::CustomerPortalCommunityListCommentsCustomerSecurity](../../models/operations/customerportalcommunitylistcommentscustomersecurity.md) | :heavy_check_mark:                                                                                                                                        | The security requirements to use for the request.                                                                                                         |
| `course_id`                                                                                                                                               | *::String*                                                                                                                                                | :heavy_check_mark:                                                                                                                                        | N/A                                                                                                                                                       |
| `post_id`                                                                                                                                                 | *::String*                                                                                                                                                | :heavy_check_mark:                                                                                                                                        | N/A                                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListCommentsCustomerResponse)](../../models/operations/customerportalcommunitylistcommentscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_comment_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:create_comment_customer" method="post" path="/v1/customer-portal/community/{course_id}/posts/{post_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.create_comment_customer(security: Models::Operations::CustomerPortalCommunityCreateCommentCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', post_id: '<value>', body: Models::Components::CommunityCommentCreate.new(
  content: '<value>'
))

unless res.community_comment_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                   | Type                                                                                                                                                        | Required                                                                                                                                                    | Description                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                  | [Models::Operations::CustomerPortalCommunityCreateCommentCustomerSecurity](../../models/operations/customerportalcommunitycreatecommentcustomersecurity.md) | :heavy_check_mark:                                                                                                                                          | The security requirements to use for the request.                                                                                                           |
| `course_id`                                                                                                                                                 | *::String*                                                                                                                                                  | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |
| `post_id`                                                                                                                                                   | *::String*                                                                                                                                                  | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |
| `body`                                                                                                                                                      | [Models::Components::CommunityCommentCreate](../../models/shared/communitycommentcreate.md)                                                                 | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityCreateCommentCustomerResponse)](../../models/operations/customerportalcommunitycreatecommentcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_comment_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:delete_comment_customer" method="delete" path="/v1/customer-portal/community/{course_id}/comments/{comment_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.delete_comment_customer(security: Models::Operations::CustomerPortalCommunityDeleteCommentCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', comment_id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                   | Type                                                                                                                                                        | Required                                                                                                                                                    | Description                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                  | [Models::Operations::CustomerPortalCommunityDeleteCommentCustomerSecurity](../../models/operations/customerportalcommunitydeletecommentcustomersecurity.md) | :heavy_check_mark:                                                                                                                                          | The security requirements to use for the request.                                                                                                           |
| `course_id`                                                                                                                                                 | *::String*                                                                                                                                                  | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |
| `comment_id`                                                                                                                                                | *::String*                                                                                                                                                  | :heavy_check_mark:                                                                                                                                          | N/A                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityDeleteCommentCustomerResponse)](../../models/operations/customerportalcommunitydeletecommentcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## react_to_post_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:react_to_post_customer" method="post" path="/v1/customer-portal/community/{course_id}/posts/{post_id}/react" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.react_to_post_customer(security: Models::Operations::CustomerPortalCommunityReactToPostCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', post_id: '<value>', body: Models::Components::CommunityReactionToggle.new(
  emoji: Models::Components::CommunityReactionToggleEmoji::FIRE
))

unless res.community_reaction_toggle_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCommunityReactToPostCustomerSecurity](../../models/operations/customerportalcommunityreacttopostcustomersecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `course_id`                                                                                                                                             | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |
| `post_id`                                                                                                                                               | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |
| `body`                                                                                                                                                  | [Models::Components::CommunityReactionToggle](../../models/shared/communityreactiontoggle.md)                                                           | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityReactToPostCustomerResponse)](../../models/operations/customerportalcommunityreacttopostcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## react_to_comment_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:react_to_comment_customer" method="post" path="/v1/customer-portal/community/{course_id}/comments/{comment_id}/react" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.react_to_comment_customer(security: Models::Operations::CustomerPortalCommunityReactToCommentCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', comment_id: '<value>', body: Models::Components::CommunityReactionToggle.new(
  emoji: Models::Components::CommunityReactionToggleEmoji::CLAP
))

unless res.community_reaction_toggle_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                     | Type                                                                                                                                                          | Required                                                                                                                                                      | Description                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                    | [Models::Operations::CustomerPortalCommunityReactToCommentCustomerSecurity](../../models/operations/customerportalcommunityreacttocommentcustomersecurity.md) | :heavy_check_mark:                                                                                                                                            | The security requirements to use for the request.                                                                                                             |
| `course_id`                                                                                                                                                   | *::String*                                                                                                                                                    | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |
| `comment_id`                                                                                                                                                  | *::String*                                                                                                                                                    | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |
| `body`                                                                                                                                                        | [Models::Components::CommunityReactionToggle](../../models/shared/communityreactiontoggle.md)                                                                 | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityReactToCommentCustomerResponse)](../../models/operations/customerportalcommunityreacttocommentcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_activities_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_activities_customer" method="get" path="/v1/customer-portal/community/{course_id}/activities" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_activities_customer(security: Models::Operations::CustomerPortalCommunityListActivitiesCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.response_customer_portal_community_list_activities_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                     | Type                                                                                                                                                          | Required                                                                                                                                                      | Description                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                    | [Models::Operations::CustomerPortalCommunityListActivitiesCustomerSecurity](../../models/operations/customerportalcommunitylistactivitiescustomersecurity.md) | :heavy_check_mark:                                                                                                                                            | The security requirements to use for the request.                                                                                                             |
| `course_id`                                                                                                                                                   | *::String*                                                                                                                                                    | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListActivitiesCustomerResponse)](../../models/operations/customerportalcommunitylistactivitiescustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_submissions_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_submissions_customer" method="get" path="/v1/customer-portal/community/{course_id}/activities/{activity_id}/submissions" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_submissions_customer(security: Models::Operations::CustomerPortalCommunityListSubmissionsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', activity_id: '<value>')

unless res.response_customer_portal_community_list_submissions_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                       | Type                                                                                                                                                            | Required                                                                                                                                                        | Description                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                      | [Models::Operations::CustomerPortalCommunityListSubmissionsCustomerSecurity](../../models/operations/customerportalcommunitylistsubmissionscustomersecurity.md) | :heavy_check_mark:                                                                                                                                              | The security requirements to use for the request.                                                                                                               |
| `course_id`                                                                                                                                                     | *::String*                                                                                                                                                      | :heavy_check_mark:                                                                                                                                              | N/A                                                                                                                                                             |
| `activity_id`                                                                                                                                                   | *::String*                                                                                                                                                      | :heavy_check_mark:                                                                                                                                              | N/A                                                                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListSubmissionsCustomerResponse)](../../models/operations/customerportalcommunitylistsubmissionscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## submit_activity_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:submit_activity_customer" method="post" path="/v1/customer-portal/community/{course_id}/activities/{activity_id}/submissions" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.submit_activity_customer(security: Models::Operations::CustomerPortalCommunitySubmitActivityCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', activity_id: '<value>', body: Models::Components::CommunityActivitySubmissionCreate.new(
  submission_type: Models::Components::CommunityActivitySubmissionCreateSubmissionType::TEXT
))

unless res.community_activity_submission_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                     | Type                                                                                                                                                          | Required                                                                                                                                                      | Description                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                    | [Models::Operations::CustomerPortalCommunitySubmitActivityCustomerSecurity](../../models/operations/customerportalcommunitysubmitactivitycustomersecurity.md) | :heavy_check_mark:                                                                                                                                            | The security requirements to use for the request.                                                                                                             |
| `course_id`                                                                                                                                                   | *::String*                                                                                                                                                    | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |
| `activity_id`                                                                                                                                                 | *::String*                                                                                                                                                    | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |
| `body`                                                                                                                                                        | [Models::Components::CommunityActivitySubmissionCreate](../../models/shared/communityactivitysubmissioncreate.md)                                             | :heavy_check_mark:                                                                                                                                            | N/A                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunitySubmitActivityCustomerResponse)](../../models/operations/customerportalcommunitysubmitactivitycustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_submission_comments_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_submission_comments_customer" method="get" path="/v1/customer-portal/community/{course_id}/activities/{activity_id}/submissions/{submission_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_submission_comments_customer(security: Models::Operations::CustomerPortalCommunityListSubmissionCommentsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', activity_id: '<value>', submission_id: '<value>')

unless res.response_customer_portal_community_list_submission_comments_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                     | Type                                                                                                                                                                          | Required                                                                                                                                                                      | Description                                                                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                    | [Models::Operations::CustomerPortalCommunityListSubmissionCommentsCustomerSecurity](../../models/operations/customerportalcommunitylistsubmissioncommentscustomersecurity.md) | :heavy_check_mark:                                                                                                                                                            | The security requirements to use for the request.                                                                                                                             |
| `course_id`                                                                                                                                                                   | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |
| `activity_id`                                                                                                                                                                 | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |
| `submission_id`                                                                                                                                                               | *::String*                                                                                                                                                                    | :heavy_check_mark:                                                                                                                                                            | N/A                                                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListSubmissionCommentsCustomerResponse)](../../models/operations/customerportalcommunitylistsubmissioncommentscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_submission_comment_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:create_submission_comment_customer" method="post" path="/v1/customer-portal/community/{course_id}/activities/{activity_id}/submissions/{submission_id}/comments" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.create_submission_comment_customer(security: Models::Operations::CustomerPortalCommunityCreateSubmissionCommentCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', activity_id: '<value>', submission_id: '<value>', body: Models::Components::CommunityActivitySubmissionCommentCreate.new(
  body: '<value>'
))

unless res.community_activity_submission_comment_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                       | Type                                                                                                                                                                            | Required                                                                                                                                                                        | Description                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                      | [Models::Operations::CustomerPortalCommunityCreateSubmissionCommentCustomerSecurity](../../models/operations/customerportalcommunitycreatesubmissioncommentcustomersecurity.md) | :heavy_check_mark:                                                                                                                                                              | The security requirements to use for the request.                                                                                                                               |
| `course_id`                                                                                                                                                                     | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `activity_id`                                                                                                                                                                   | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `submission_id`                                                                                                                                                                 | *::String*                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |
| `body`                                                                                                                                                                          | [Models::Components::CommunityActivitySubmissionCommentCreate](../../models/shared/communityactivitysubmissioncommentcreate.md)                                                 | :heavy_check_mark:                                                                                                                                                              | N/A                                                                                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityCreateSubmissionCommentCustomerResponse)](../../models/operations/customerportalcommunitycreatesubmissioncommentcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_events_customer

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:list_events_customer" method="get" path="/v1/customer-portal/community/{course_id}/events" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.list_events_customer(security: Models::Operations::CustomerPortalCommunityListEventsCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>')

unless res.response_customer_portal_community_list_events_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                            | [Models::Operations::CustomerPortalCommunityListEventsCustomerSecurity](../../models/operations/customerportalcommunitylisteventscustomersecurity.md) | :heavy_check_mark:                                                                                                                                    | The security requirements to use for the request.                                                                                                     |
| `course_id`                                                                                                                                           | *::String*                                                                                                                                            | :heavy_check_mark:                                                                                                                                    | N/A                                                                                                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityListEventsCustomerResponse)](../../models/operations/customerportalcommunitylisteventscustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## rsvp_event_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:rsvp_event_customer" method="post" path="/v1/customer-portal/community/{course_id}/events/{event_id}/rsvp" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.rsvp_event_customer(security: Models::Operations::CustomerPortalCommunityRsvpEventCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', event_id: '<value>')

unless res.community_event_rsvp_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                           | Type                                                                                                                                                | Required                                                                                                                                            | Description                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                          | [Models::Operations::CustomerPortalCommunityRsvpEventCustomerSecurity](../../models/operations/customerportalcommunityrsvpeventcustomersecurity.md) | :heavy_check_mark:                                                                                                                                  | The security requirements to use for the request.                                                                                                   |
| `course_id`                                                                                                                                         | *::String*                                                                                                                                          | :heavy_check_mark:                                                                                                                                  | N/A                                                                                                                                                 |
| `event_id`                                                                                                                                          | *::String*                                                                                                                                          | :heavy_check_mark:                                                                                                                                  | N/A                                                                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityRsvpEventCustomerResponse)](../../models/operations/customerportalcommunityrsvpeventcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## unrsvp_event_customer

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_community:unrsvp_event_customer" method="delete" path="/v1/customer-portal/community/{course_id}/events/{event_id}/rsvp" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_community.unrsvp_event_customer(security: Models::Operations::CustomerPortalCommunityUnrsvpEventCustomerSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), course_id: '<value>', event_id: '<value>')

unless res.community_event_rsvp_result.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCommunityUnrsvpEventCustomerSecurity](../../models/operations/customerportalcommunityunrsvpeventcustomersecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `course_id`                                                                                                                                             | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |
| `event_id`                                                                                                                                              | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCommunityUnrsvpEventCustomerResponse)](../../models/operations/customerportalcommunityunrsvpeventcustomerresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |