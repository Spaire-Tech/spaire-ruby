# CustomerPortal.CustomerSession

## Overview

### Available Operations

* [introspect](#introspect) - Introspect Customer Session
* [get_authenticated_user](#get_authenticated_user) - Get Authenticated Portal User

## introspect

Introspect the current session and return its information.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer-session:introspect" method="get" path="/v1/customer-portal/customer-session/introspect" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_session.introspect(security: Models::Operations::CustomerPortalCustomerSessionIntrospectSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_customer_session.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalCustomerSessionIntrospectSecurity](../../models/operations/customerportalcustomersessionintrospectsecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerSessionIntrospectResponse)](../../models/operations/customerportalcustomersessionintrospectresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_authenticated_user

Get information about the currently authenticated portal user.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customer-session:get_authenticated_user" method="get" path="/v1/customer-portal/customer-session/user" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customer_session.get_authenticated_user(security: Models::Operations::CustomerPortalCustomerSessionGetAuthenticatedUserSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.portal_authenticated_user.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                             | Type                                                                                                                                                                  | Required                                                                                                                                                              | Description                                                                                                                                                           |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                            | [Models::Operations::CustomerPortalCustomerSessionGetAuthenticatedUserSecurity](../../models/operations/customerportalcustomersessiongetauthenticatedusersecurity.md) | :heavy_check_mark:                                                                                                                                                    | The security requirements to use for the request.                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomerSessionGetAuthenticatedUserResponse)](../../models/operations/customerportalcustomersessiongetauthenticateduserresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |