# CustomerPortal.Members

## Overview

### Available Operations

* [list_members](#list_members) - List Members
* [add_member](#add_member) - Add Member
* [remove_member](#remove_member) - Remove Member
* [update_member](#update_member) - Update Member

## list_members

List all members of the customer's team.

Only available to owners and billing managers of team customers.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:members:list_members" method="get" path="/v1/customer-portal/members" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_portal.members.list_members

unless res.response_customer_portal_members_list_members.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::CustomerPortalMembersListMembersResponse)](../../models/operations/customerportalmemberslistmembersresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## add_member

Add a new member to the customer's team.

Only available to owners and billing managers of team customers.

Rules:
- Cannot add a member with the owner role (there must be exactly one owner)
- If a member with this email already exists, the existing member is returned

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:members:add_member" method="post" path="/v1/customer-portal/members" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::CustomerPortalMemberCreate.new(
  email: 'Domenica.Schamberger@yahoo.com'
)
res = s.customer_portal.members.add_member(request: req)

unless res.customer_portal_member.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `request`                                                                                           | [Models::Components::CustomerPortalMemberCreate](../../models/shared/customerportalmembercreate.md) | :heavy_check_mark:                                                                                  | The request object to use for the request.                                                          |

### Response

**[T.nilable(Models::Operations::CustomerPortalMembersAddMemberResponse)](../../models/operations/customerportalmembersaddmemberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## remove_member

Remove a member from the team.

Only available to owners and billing managers of team customers.

Rules:
- Cannot remove yourself
- Cannot remove the only owner

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:members:remove_member" method="delete" path="/v1/customer-portal/members/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_portal.members.remove_member(id: 'b61c5e87-cda5-4b14-93ee-71a695f42d9d')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CustomerPortalMembersRemoveMemberResponse)](../../models/operations/customerportalmembersremovememberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_member

Update a member's role.

Only available to owners and billing managers of team customers.

Rules:
- Cannot modify your own role (to prevent self-demotion)
- Customer must have exactly one owner at all times

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:members:update_member" method="patch" path="/v1/customer-portal/members/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_portal.members.update_member(id: '8319ae11-ed5f-4642-81e4-4b40731df195', body: Models::Components::CustomerPortalMemberUpdate.new)

unless res.customer_portal_member.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `id`                                                                                                | *::String*                                                                                          | :heavy_check_mark:                                                                                  | N/A                                                                                                 |
| `body`                                                                                              | [Models::Components::CustomerPortalMemberUpdate](../../models/shared/customerportalmemberupdate.md) | :heavy_check_mark:                                                                                  | N/A                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalMembersUpdateMemberResponse)](../../models/operations/customerportalmembersupdatememberresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |