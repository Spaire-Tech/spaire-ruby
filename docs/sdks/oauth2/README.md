# Oauth2

## Overview

### Available Operations

* [authorize](#authorize) - Authorize
* [token](#token) - Request Token
* [revoke](#revoke) - Revoke Token
* [introspect](#introspect) - Introspect Token
* [userinfo](#userinfo) - Get User Info

## authorize

Authorize

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:authorize" method="get" path="/v1/oauth2/authorize" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.oauth2.authorize

unless res.response_oauth2_authorize.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::Oauth2AuthorizeResponse)](../../models/operations/oauth2authorizeresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## token

Request an access token using a valid grant.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:request_token" method="post" path="/v1/oauth2/token" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::AuthorizationCodeTokenRequest.new(
  grant_type: 'authorization_code',
  client_id: '<id>',
  client_secret: '<value>',
  code: '<value>',
  redirect_uri: 'https://memorable-season.name'
)
res = s.oauth2.token(request: req)

unless res.token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                          | Type                                                                                                                                                                                               | Required                                                                                                                                                                                           | Description                                                                                                                                                                                        |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                          | [T.any(Models::Components::AuthorizationCodeTokenRequest, Models::Components::RefreshTokenRequest, Models::Components::WebTokenRequest)](../../models/operations/oauth2requesttokenrequestbody.md) | :heavy_check_mark:                                                                                                                                                                                 | The request object to use for the request.                                                                                                                                                         |

### Response

**[T.nilable(Models::Operations::Oauth2RequestTokenResponse)](../../models/operations/oauth2requesttokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## revoke

Revoke an access token or a refresh token.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:revoke_token" method="post" path="/v1/oauth2/revoke" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::RevokeTokenRequest.new(
  token: '<value>',
  client_id: '<id>',
  client_secret: '<value>'
)
res = s.oauth2.revoke(request: req)

unless res.revoke_token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Components::RevokeTokenRequest](../../models/shared/revoketokenrequest.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::Oauth2RevokeTokenResponse)](../../models/operations/oauth2revoketokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## introspect

Get information about an access token.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:introspect_token" method="post" path="/v1/oauth2/introspect" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::IntrospectTokenRequest.new(
  token: '<value>',
  client_id: '<id>',
  client_secret: '<value>'
)
res = s.oauth2.introspect(request: req)

unless res.introspect_token_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Components::IntrospectTokenRequest](../../models/shared/introspecttokenrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::Oauth2IntrospectTokenResponse)](../../models/operations/oauth2introspecttokenresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## userinfo

Get information about the authenticated user.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:userinfo" method="get" path="/v1/oauth2/userinfo" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.oauth2.userinfo

unless res.response_oauth2_userinfo.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::Oauth2UserinfoResponse)](../../models/operations/oauth2userinforesponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |