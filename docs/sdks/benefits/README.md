# Benefits

## Overview

### Available Operations

* [list](#list) - List Benefits
* [create](#create) - Create Benefit
* [get](#get) - Get Benefit
* [delete](#delete) - Delete Benefit
* [update](#update) - Update Benefit
* [grants](#grants) - List Benefit Grants

## list

List benefits.

**Scopes**: `benefits:read` `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:list" method="get" path="/v1/benefits/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::BenefitsListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.benefits.list(request: req)

unless res.list_resource_benefit.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `request`                                                                                 | [Models::Operations::BenefitsListRequest](../../models/operations/benefitslistrequest.md) | :heavy_check_mark:                                                                        | The request object to use for the request.                                                |

### Response

**[T.nilable(Models::Operations::BenefitsListResponse)](../../models/operations/benefitslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a benefit.

**Scopes**: `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:create" method="post" path="/v1/benefits/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::BenefitLicenseKeysCreate.new(
  type: 'license_keys',
  description: 'mature emergent at outside arrogantly gadzooks zealous equatorial notwithstanding',
  properties: Models::Components::BenefitLicenseKeysCreateProperties.new
)
res = s.benefits.create(request: req)

unless res.benefit.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                                                                       | Type                                                                                                                                                                                                                                                                                                                            | Required                                                                                                                                                                                                                                                                                                                        | Description                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                                                                                                                                                       | [T.any(Models::Components::BenefitCustomCreate, Models::Components::BenefitDiscordCreate, Models::Components::BenefitGitHubRepositoryCreate, Models::Components::BenefitDownloadablesCreate, Models::Components::BenefitLicenseKeysCreate, Models::Components::BenefitMeterCreditCreate)](../../models/shared/benefitcreate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                                                                              | The request object to use for the request.                                                                                                                                                                                                                                                                                      |

### Response

**[T.nilable(Models::Operations::BenefitsCreateResponse)](../../models/operations/benefitscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a benefit by ID.

**Scopes**: `benefits:read` `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:get" method="get" path="/v1/benefits/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.benefits.get(id: '<value>')

unless res.benefit.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::BenefitsGetResponse)](../../models/operations/benefitsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a benefit.

> [!WARNING]
> Every grants associated with the benefit will be revoked.
> Users will lose access to the benefit.

**Scopes**: `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:delete" method="delete" path="/v1/benefits/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.benefits.delete(id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::BenefitsDeleteResponse)](../../models/operations/benefitsdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a benefit.

**Scopes**: `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:update" method="patch" path="/v1/benefits/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.benefits.update(id: '<value>', body: Models::Components::BenefitMeterCreditUpdate.new(
  type: 'meter_credit'
))

unless res.benefit.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                                                                                         | Type                                                                                                                                                                                                                                                                                                                                              | Required                                                                                                                                                                                                                                                                                                                                          | Description                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                                                                                                                                                                                                                                              | *::String*                                                                                                                                                                                                                                                                                                                                        | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                | N/A                                                                                                                                                                                                                                                                                                                                               |
| `body`                                                                                                                                                                                                                                                                                                                                            | [T.any(Models::Components::BenefitCustomUpdate, Models::Components::BenefitDiscordUpdate, Models::Components::BenefitGitHubRepositoryUpdate, Models::Components::BenefitDownloadablesUpdate, Models::Components::BenefitLicenseKeysUpdate, Models::Components::BenefitMeterCreditUpdate)](../../models/operations/benefitsupdatebenefitupdate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                | N/A                                                                                                                                                                                                                                                                                                                                               |

### Response

**[T.nilable(Models::Operations::BenefitsUpdateResponse)](../../models/operations/benefitsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## grants

List the individual grants for a benefit.

It's especially useful to check if a user has been granted a benefit.

**Scopes**: `benefits:read` `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefits:grants" method="get" path="/v1/benefits/{id}/grants" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::BenefitsGrantsRequest.new(
  id: '<value>'
)
res = s.benefits.grants(request: req)

unless res.list_resource_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `request`                                                                                     | [Models::Operations::BenefitsGrantsRequest](../../models/operations/benefitsgrantsrequest.md) | :heavy_check_mark:                                                                            | The request object to use for the request.                                                    |

### Response

**[T.nilable(Models::Operations::BenefitsGrantsResponse)](../../models/operations/benefitsgrantsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |