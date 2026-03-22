# Files

## Overview

### Available Operations

* [list](#list) - List Files
* [create](#create) - Create File
* [uploaded](#uploaded) - Complete File Upload
* [delete](#delete) - Delete File
* [update](#update) - Update File

## list

List files.

**Scopes**: `files:read` `files:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="files:list" method="get" path="/v1/files/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.files.list(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737', page: 1, limit: 10)

unless res.list_resource_file_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                    | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/fileslistqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                   | Filter by organization ID.                                                                                           |
| `ids`                                                                                                                | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/fileidfilter.md)                            | :heavy_minus_sign:                                                                                                   | Filter by file ID.                                                                                                   |
| `page`                                                                                                               | *T.nilable(::Integer)*                                                                                               | :heavy_minus_sign:                                                                                                   | Page number, defaults to 1.                                                                                          |
| `limit`                                                                                                              | *T.nilable(::Integer)*                                                                                               | :heavy_minus_sign:                                                                                                   | Size of a page, defaults to 10. Maximum is 100.                                                                      |

### Response

**[T.nilable(Models::Operations::FilesListResponse)](../../models/operations/fileslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a file.

**Scopes**: `files:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="files:create" method="post" path="/v1/files/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::DownloadableFileCreate.new(
  name: '<value>',
  mime_type: '<value>',
  size: 612_128,
  upload: Models::Components::S3FileCreateMultipart.new(
    parts: []
  ),
  service: 'downloadable'
)
res = s.files.create(request: req)

unless res.file_upload.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                            | Type                                                                                                                                                                                 | Required                                                                                                                                                                             | Description                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                            | [T.any(Models::Components::DownloadableFileCreate, Models::Components::ProductMediaFileCreate, Models::Components::OrganizationAvatarFileCreate)](../../models/shared/filecreate.md) | :heavy_check_mark:                                                                                                                                                                   | The request object to use for the request.                                                                                                                                           |

### Response

**[T.nilable(Models::Operations::FilesCreateResponse)](../../models/operations/filescreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## uploaded

Complete a file upload.

**Scopes**: `files:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="files:uploaded" method="post" path="/v1/files/{id}/uploaded" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.files.uploaded(id: '<value>', body: Models::Components::FileUploadCompleted.new(
  id: '<id>',
  path: '/boot',
  parts: [
    Models::Components::S3FileUploadCompletedPart.new(
      number: 979_613,
      checksum_etag: '<value>',
      checksum_sha256_base64: '<value>'
    ),
  ]
))

unless res.response_files_uploaded.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `id`                                                                                  | *::String*                                                                            | :heavy_check_mark:                                                                    | The file ID.                                                                          |
| `body`                                                                                | [Models::Components::FileUploadCompleted](../../models/shared/fileuploadcompleted.md) | :heavy_check_mark:                                                                    | N/A                                                                                   |

### Response

**[T.nilable(Models::Operations::FilesUploadedResponse)](../../models/operations/filesuploadedresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a file.

**Scopes**: `files:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="files:delete" method="delete" path="/v1/files/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.files.delete(id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::FilesDeleteResponse)](../../models/operations/filesdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a file.

**Scopes**: `files:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="files:update" method="patch" path="/v1/files/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.files.update(id: '<value>', body: Models::Components::FilePatch.new)

unless res.response_files_update.nil?
  # handle response
end

```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `id`                                                              | *::String*                                                        | :heavy_check_mark:                                                | The file ID.                                                      |
| `body`                                                            | [Models::Components::FilePatch](../../models/shared/filepatch.md) | :heavy_check_mark:                                                | N/A                                                               |

### Response

**[T.nilable(Models::Operations::FilesUpdateResponse)](../../models/operations/filesupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |