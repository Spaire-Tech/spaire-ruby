# CustomerPortal.BenefitGrants

## Overview

### Available Operations

* [list](#list) - List Benefit Grants
* [get](#get) - Get Benefit Grant
* [update](#update) - Update Benefit Grant

## list

List benefits grants of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:benefit-grants:list" method="get" path="/v1/customer-portal/benefit-grants/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Operations::CustomerPortalBenefitGrantsListRequest.new
res = s.customer_portal.benefit_grants.list(request: req, security: Models::Operations::CustomerPortalBenefitGrantsListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.list_resource_customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                         | Type                                                                                                                              | Required                                                                                                                          | Description                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                         | [Models::Operations::CustomerPortalBenefitGrantsListRequest](../../models/operations/customerportalbenefitgrantslistrequest.md)   | :heavy_check_mark:                                                                                                                | The request object to use for the request.                                                                                        |
| `security`                                                                                                                        | [Models::Operations::CustomerPortalBenefitGrantsListSecurity](../../models/operations/customerportalbenefitgrantslistsecurity.md) | :heavy_check_mark:                                                                                                                | The security requirements to use for the request.                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsListResponse)](../../models/operations/customerportalbenefitgrantslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a benefit grant by ID for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:benefit-grants:get" method="get" path="/v1/customer-portal/benefit-grants/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.benefit_grants.get(security: Models::Operations::CustomerPortalBenefitGrantsGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                       | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                      | [Models::Operations::CustomerPortalBenefitGrantsGetSecurity](../../models/operations/customerportalbenefitgrantsgetsecurity.md) | :heavy_check_mark:                                                                                                              | The security requirements to use for the request.                                                                               |
| `id`                                                                                                                            | *::String*                                                                                                                      | :heavy_check_mark:                                                                                                              | The benefit grant ID.                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsGetResponse)](../../models/operations/customerportalbenefitgrantsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a benefit grant for the authenticated customer.

**Scopes**: `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:benefit-grants:update" method="patch" path="/v1/customer-portal/benefit-grants/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.benefit_grants.update(security: Models::Operations::CustomerPortalBenefitGrantsUpdateSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>', body: Models::Components::CustomerBenefitGrantLicenseKeysUpdate.new(
  benefit_type: 'license_keys'
))

unless res.customer_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                                                                                                                                                                  | Type                                                                                                                                                                                                                                                                                                                                                                                                                       | Required                                                                                                                                                                                                                                                                                                                                                                                                                   | Description                                                                                                                                                                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                                                                                                                                                                                                                                                                 | [Models::Operations::CustomerPortalBenefitGrantsUpdateSecurity](../../models/operations/customerportalbenefitgrantsupdatesecurity.md)                                                                                                                                                                                                                                                                                      | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                                         | The security requirements to use for the request.                                                                                                                                                                                                                                                                                                                                                                          |
| `id`                                                                                                                                                                                                                                                                                                                                                                                                                       | *::String*                                                                                                                                                                                                                                                                                                                                                                                                                 | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                                         | The benefit grant ID.                                                                                                                                                                                                                                                                                                                                                                                                      |
| `body`                                                                                                                                                                                                                                                                                                                                                                                                                     | [T.any(Models::Components::CustomerBenefitGrantDiscordUpdate, Models::Components::CustomerBenefitGrantGitHubRepositoryUpdate, Models::Components::CustomerBenefitGrantDownloadablesUpdate, Models::Components::CustomerBenefitGrantLicenseKeysUpdate, Models::Components::CustomerBenefitGrantCustomUpdate, Models::Components::CustomerBenefitGrantMeterCreditUpdate)](../../models/shared/customerbenefitgrantupdate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                                                                         | N/A                                                                                                                                                                                                                                                                                                                                                                                                                        |

### Response

**[T.nilable(Models::Operations::CustomerPortalBenefitGrantsUpdateResponse)](../../models/operations/customerportalbenefitgrantsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |