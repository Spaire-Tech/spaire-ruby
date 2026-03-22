# LicenseKeys

## Overview

### Available Operations

* [list](#list) - List License Keys
* [get](#get) - Get License Key
* [update](#update) - Update License Key
* [get_activation](#get_activation) - Get Activation
* [validate](#validate) - Validate License Key
* [activate](#activate) - Activate License Key
* [deactivate](#deactivate) - Deactivate License Key

## list

Get license keys connected to the given organization & filters.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:list" method="get" path="/v1/license-keys/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.license_keys.list(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737', page: 1, limit: 10)

unless res.list_resource_license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                  | Type                                                                                                                       | Required                                                                                                                   | Description                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                          | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/licensekeyslistqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                         | Filter by organization ID.                                                                                                 |
| `benefit_id`                                                                                                               | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/queryparambenefitidfilter.md)                     | :heavy_minus_sign:                                                                                                         | Filter by benefit ID.                                                                                                      |
| `page`                                                                                                                     | *T.nilable(::Integer)*                                                                                                     | :heavy_minus_sign:                                                                                                         | Page number, defaults to 1.                                                                                                |
| `limit`                                                                                                                    | *T.nilable(::Integer)*                                                                                                     | :heavy_minus_sign:                                                                                                         | Size of a page, defaults to 10. Maximum is 100.                                                                            |

### Response

**[T.nilable(Models::Operations::LicenseKeysListResponse)](../../models/operations/licensekeyslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a license key.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:get" method="get" path="/v1/license-keys/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.license_keys.get(id: '<value>')

unless res.license_key_with_activations.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::LicenseKeysGetResponse)](../../models/operations/licensekeysgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a license key.

**Scopes**: `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:update" method="patch" path="/v1/license-keys/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.license_keys.update(id: '<value>', body: Models::Components::LicenseKeyUpdate.new)

unless res.license_key_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                       | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `id`                                                                            | *::String*                                                                      | :heavy_check_mark:                                                              | N/A                                                                             |
| `body`                                                                          | [Models::Components::LicenseKeyUpdate](../../models/shared/licensekeyupdate.md) | :heavy_check_mark:                                                              | N/A                                                                             |

### Response

**[T.nilable(Models::Operations::LicenseKeysUpdateResponse)](../../models/operations/licensekeysupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_activation

Get a license key activation.

**Scopes**: `license_keys:read` `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:get_activation" method="get" path="/v1/license-keys/{id}/activations/{activation_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.license_keys.get_activation(id: '<value>', activation_id: '<value>')

unless res.license_key_activation_read.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |
| `activation_id`    | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::LicenseKeysGetActivationResponse)](../../models/operations/licensekeysgetactivationresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::Unauthorized        | 401                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## validate

Validate a license key.

**Scopes**: `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:validate" method="post" path="/v1/license-keys/validate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::LicenseKeyValidate.new(
  key: '<key>',
  organization_id: '<value>'
)
res = s.license_keys.validate(request: req)

unless res.validated_license_key.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Components::LicenseKeyValidate](../../models/shared/licensekeyvalidate.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::LicenseKeysValidateResponse)](../../models/operations/licensekeysvalidateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## activate

Activate a license key instance.

**Scopes**: `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:activate" method="post" path="/v1/license-keys/activate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::LicenseKeyActivate.new(
  key: '<key>',
  organization_id: '<value>',
  label: '<value>'
)
res = s.license_keys.activate(request: req)

unless res.license_key_activation_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                           | Type                                                                                | Required                                                                            | Description                                                                         |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `request`                                                                           | [Models::Components::LicenseKeyActivate](../../models/shared/licensekeyactivate.md) | :heavy_check_mark:                                                                  | The request object to use for the request.                                          |

### Response

**[T.nilable(Models::Operations::LicenseKeysActivateResponse)](../../models/operations/licensekeysactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## deactivate

Deactivate a license key instance.

**Scopes**: `license_keys:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="license_keys:deactivate" method="post" path="/v1/license-keys/deactivate" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::LicenseKeyDeactivate.new(
  key: '<key>',
  organization_id: '<value>',
  activation_id: '<value>'
)
res = s.license_keys.deactivate(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `request`                                                                               | [Models::Components::LicenseKeyDeactivate](../../models/shared/licensekeydeactivate.md) | :heavy_check_mark:                                                                      | The request object to use for the request.                                              |

### Response

**[T.nilable(Models::Operations::LicenseKeysDeactivateResponse)](../../models/operations/licensekeysdeactivateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |