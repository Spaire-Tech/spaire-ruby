# CustomerPortal.LicenseKeys

## Overview

### Available Operations

* [list](#list) - List License Keys
* [get](#get) - Get License Key
* [validate](#validate) - Validate License Key
* [activate](#activate) - Activate License Key
* [deactivate](#deactivate) - Deactivate License Key

## list

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:license_keys:list" method="get" path="/v1/customer-portal/license-keys/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.license_keys.list(security: Models::Operations::CustomerPortalLicenseKeysListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), page: 1, limit: 10)

unless res.list_resource_license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                    | [Models::Operations::CustomerPortalLicenseKeysListSecurity](../../models/operations/customerportallicensekeyslistsecurity.md) | :heavy_check_mark:                                                                                                            | The security requirements to use for the request.                                                                             |
| `benefit_id`                                                                                                                  | *T.nilable(::String)*                                                                                                         | :heavy_minus_sign:                                                                                                            | Filter by a specific benefit                                                                                                  |
| `page`                                                                                                                        | *T.nilable(::Integer)*                                                                                                        | :heavy_minus_sign:                                                                                                            | Page number, defaults to 1.                                                                                                   |
| `limit`                                                                                                                       | *T.nilable(::Integer)*                                                                                                        | :heavy_minus_sign:                                                                                                            | Size of a page, defaults to 10. Maximum is 100.                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysListResponse)](../../models/operations/customerportallicensekeyslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a license key.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:license_keys:get" method="get" path="/v1/customer-portal/license-keys/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.license_keys.get(security: Models::Operations::CustomerPortalLicenseKeysGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.license_key_with_activations.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                   | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                  | [Models::Operations::CustomerPortalLicenseKeysGetSecurity](../../models/operations/customerportallicensekeysgetsecurity.md) | :heavy_check_mark:                                                                                                          | The security requirements to use for the request.                                                                           |
| `id`                                                                                                                        | *::String*                                                                                                                  | :heavy_check_mark:                                                                                                          | N/A                                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysGetResponse)](../../models/operations/customerportallicensekeysgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## validate

Validate a license key.

> This endpoint doesn't require authentication and can be safely used on a public
> client, like a desktop application or a mobile app.
> If you plan to validate a license key on a server, use the `/v1/license-keys/validate`
> endpoint instead.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:license_keys:validate" method="post" path="/v1/customer-portal/license-keys/validate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::LicenseKeyValidate.new(
  key: '<key>',
  organization_id: '<value>'
)
res = s.customer_portal.license_keys.validate(request: req)

unless res.validated_license_key.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Components::LicenseKeyValidate](../../models/shared/licensekeyvalidate.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysValidateResponse)](../../models/operations/customerportallicensekeysvalidateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## activate

Activate a license key instance.

> This endpoint doesn't require authentication and can be safely used on a public
> client, like a desktop application or a mobile app.
> If you plan to validate a license key on a server, use the `/v1/license-keys/activate`
> endpoint instead.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:license_keys:activate" method="post" path="/v1/customer-portal/license-keys/activate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::LicenseKeyActivate.new(
  key: '<key>',
  organization_id: '<value>',
  label: '<value>'
)
res = s.customer_portal.license_keys.activate(request: req)

unless res.license_key_activation_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Components::LicenseKeyActivate](../../models/shared/licensekeyactivate.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysActivateResponse)](../../models/operations/customerportallicensekeysactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## deactivate

Deactivate a license key instance.

> This endpoint doesn't require authentication and can be safely used on a public
> client, like a desktop application or a mobile app.
> If you plan to validate a license key on a server, use the `/v1/license-keys/deactivate`
> endpoint instead.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:license_keys:deactivate" method="post" path="/v1/customer-portal/license-keys/deactivate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::LicenseKeyDeactivate.new(
  key: '<key>',
  organization_id: '<value>',
  activation_id: '<value>'
)
res = s.customer_portal.license_keys.deactivate(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `request`                                                                               | [Models::Components::LicenseKeyDeactivate](../../models/shared/licensekeydeactivate.md) | :heavy_check_mark:                                                                      | The request object to use for the request.                                              |

### Response

**[T.nilable(Models::Operations::CustomerPortalLicenseKeysDeactivateResponse)](../../models/operations/customerportallicensekeysdeactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |