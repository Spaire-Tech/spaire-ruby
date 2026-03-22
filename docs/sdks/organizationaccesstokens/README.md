# OrganizationAccessTokens

## Overview

### Available Operations

* [list](#list) - List
* [create](#create) - Create
* [delete](#delete) - Delete
* [update](#update) - Update

## list

List organization access tokens.

**Scopes**: `organization_access_tokens:read` `organization_access_tokens:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="organization_access_tokens:list" method="get" path="/v1/organization-access-tokens/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.organization_access_tokens.list(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737', page: 1, limit: 10)

unless res.list_resource_organization_access_token.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                                                                       | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/organizationaccesstokenslistqueryparamorganizationidfilter.md)                                 | :heavy_minus_sign:                                                                                                                                                      | Filter by organization ID.                                                                                                                                              |
| `page`                                                                                                                                                                  | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Page number, defaults to 1.                                                                                                                                             |
| `limit`                                                                                                                                                                 | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Size of a page, defaults to 10. Maximum is 100.                                                                                                                         |
| `sorting`                                                                                                                                                               | T::Array<[Models::Components::OrganizationAccessTokenSortProperty](../../models/shared/organizationaccesstokensortproperty.md)>                                         | :heavy_minus_sign:                                                                                                                                                      | Sorting criterion. Several criteria can be used simultaneously and will be applied in order. Add a minus sign `-` before the criteria name to sort by descending order. |

### Response

**[T.nilable(Models::Operations::OrganizationAccessTokensListResponse)](../../models/operations/organizationaccesstokenslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

**Scopes**: `organization_access_tokens:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="organization_access_tokens:create" method="post" path="/v1/organization-access-tokens/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::OrganizationAccessTokenCreate.new(
  comment: 'The Football Is Good For Training And Recreational Purposes',
  scopes: []
)
res = s.organization_access_tokens.create(request: req)

unless res.organization_access_token_create_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                 | Type                                                                                                      | Required                                                                                                  | Description                                                                                               |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                 | [Models::Components::OrganizationAccessTokenCreate](../../models/shared/organizationaccesstokencreate.md) | :heavy_check_mark:                                                                                        | The request object to use for the request.                                                                |

### Response

**[T.nilable(Models::Operations::OrganizationAccessTokensCreateResponse)](../../models/operations/organizationaccesstokenscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

**Scopes**: `organization_access_tokens:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="organization_access_tokens:delete" method="delete" path="/v1/organization-access-tokens/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.organization_access_tokens.delete(id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::OrganizationAccessTokensDeleteResponse)](../../models/operations/organizationaccesstokensdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

**Scopes**: `organization_access_tokens:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="organization_access_tokens:update" method="patch" path="/v1/organization-access-tokens/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.organization_access_tokens.update(id: '<value>', body: Models::Components::OrganizationAccessTokenUpdate.new)

unless res.organization_access_token.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                 | Type                                                                                                      | Required                                                                                                  | Description                                                                                               |
| --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                      | *::String*                                                                                                | :heavy_check_mark:                                                                                        | N/A                                                                                                       |
| `body`                                                                                                    | [Models::Components::OrganizationAccessTokenUpdate](../../models/shared/organizationaccesstokenupdate.md) | :heavy_check_mark:                                                                                        | N/A                                                                                                       |

### Response

**[T.nilable(Models::Operations::OrganizationAccessTokensUpdateResponse)](../../models/operations/organizationaccesstokensupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |