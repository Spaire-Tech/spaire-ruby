# MemberSessions

## Overview

### Available Operations

* [create](#create) - Create Member Session

## create

Create a member session.

This endpoint is only available for organizations with `member_model_enabled`
and `seat_based_pricing_enabled` feature flags enabled.

**Scopes**: `member_sessions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="member-sessions:create" method="post" path="/v1/member-sessions/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::MemberSessionCreate.new(
  member_id: '<value>',
  return_url: 'https://example.com/account'
)
res = s.member_sessions.create(request: req)

unless res.member_session.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Components::MemberSessionCreate](../../models/shared/membersessioncreate.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::MemberSessionsCreateResponse)](../../models/operations/membersessionscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |