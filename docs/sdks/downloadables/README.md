# CustomerPortal.Downloadables

## Overview

### Available Operations

* [list](#list) - List Downloadables

## list

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:downloadables:list" method="get" path="/v1/customer-portal/downloadables/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.downloadables.list(security: Models::Operations::CustomerPortalDownloadablesListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), page: 1, limit: 10)

unless res.list_resource_downloadable_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                             | Type                                                                                                                                  | Required                                                                                                                              | Description                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                            | [Models::Operations::CustomerPortalDownloadablesListSecurity](../../models/operations/customerportaldownloadableslistsecurity.md)     | :heavy_check_mark:                                                                                                                    | The security requirements to use for the request.                                                                                     |
| `benefit_id`                                                                                                                          | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/customerportaldownloadableslistqueryparambenefitidfilter.md) | :heavy_minus_sign:                                                                                                                    | Filter by benefit ID.                                                                                                                 |
| `page`                                                                                                                                | *T.nilable(::Integer)*                                                                                                                | :heavy_minus_sign:                                                                                                                    | Page number, defaults to 1.                                                                                                           |
| `limit`                                                                                                                               | *T.nilable(::Integer)*                                                                                                                | :heavy_minus_sign:                                                                                                                    | Size of a page, defaults to 10. Maximum is 100.                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalDownloadablesListResponse)](../../models/operations/customerportaldownloadableslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |