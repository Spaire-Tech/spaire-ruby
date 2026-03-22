# Members

## Overview

### Available Operations

* [list_members](#list_members) - List Members
* [create_member](#create_member) - Create Member
* [get_member](#get_member) - Get Member
* [delete_member](#delete_member) - Delete Member
* [update_member](#update_member) - Update Member

## list_members

List members with optional customer ID filter.

**Scopes**: `members:read` `members:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="members:list_members" method="get" path="/v1/members/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::MembersListMembersRequest.new
res = s.members.list_members(request: req)

unless res.list_resource_member.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `request`                                                                                             | [Models::Operations::MembersListMembersRequest](../../models/operations/memberslistmembersrequest.md) | :heavy_check_mark:                                                                                    | The request object to use for the request.                                                            |

### Response

**[T.nilable(Models::Operations::MembersListMembersResponse)](../../models/operations/memberslistmembersresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_member

Create a new member for a customer.

Only B2B customers with the member management feature enabled can add members.
The authenticated user or organization must have access to the customer's organization.

**Scopes**: `members:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="members:create_member" method="post" path="/v1/members/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::MemberCreate.new(
  customer_id: '<value>',
  email: 'member@example.com',
  name: 'Jane Doe',
  external_id: 'usr_1337'
)
res = s.members.create_member(request: req)

unless res.member.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [Models::Components::MemberCreate](../../models/shared/membercreate.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[T.nilable(Models::Operations::MembersCreateMemberResponse)](../../models/operations/memberscreatememberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_member

Get a member by ID.

The authenticated user or organization must have access to the member's organization.

**Scopes**: `members:read` `members:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="members:get_member" method="get" path="/v1/members/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.members.get_member(id: '572bebad-ee17-4d04-a50f-6596a7d92cf3')

unless res.member.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::MembersGetMemberResponse)](../../models/operations/membersgetmemberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_member

Delete a member.

The authenticated user or organization must have access to the member's organization.

**Scopes**: `members:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="members:delete_member" method="delete" path="/v1/members/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.members.delete_member(id: '913247e9-8f2b-4bd1-a47e-9842d173a7cb')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::MembersDeleteMemberResponse)](../../models/operations/membersdeletememberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_member

Update a member.

Only name and role can be updated.
The authenticated user or organization must have access to the member's organization.

**Scopes**: `members:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="members:update_member" method="patch" path="/v1/members/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.members.update_member(id: 'ab9b628a-6dbd-4f07-bcd6-163a8b5b7de4', body: Models::Components::MemberUpdate.new(
  name: 'Jane Doe'
))

unless res.member.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `id`                                                                    | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     |
| `body`                                                                  | [Models::Components::MemberUpdate](../../models/shared/memberupdate.md) | :heavy_check_mark:                                                      | N/A                                                                     |

### Response

**[T.nilable(Models::Operations::MembersUpdateMemberResponse)](../../models/operations/membersupdatememberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |