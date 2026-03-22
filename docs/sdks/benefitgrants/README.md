# BenefitGrants

## Overview

### Available Operations

* [list](#list) - List Benefit Grants

## list

List benefit grants across all benefits for the authenticated organization.

**Scopes**: `benefits:read` `benefits:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="benefit-grants:list" method="get" path="/v1/benefit-grants/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::BenefitGrantsListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.benefit_grants.list(request: req)

unless res.list_resource_benefit_grant.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `request`                                                                                           | [Models::Operations::BenefitGrantsListRequest](../../models/operations/benefitgrantslistrequest.md) | :heavy_check_mark:                                                                                  | The request object to use for the request.                                                          |

### Response

**[T.nilable(Models::Operations::BenefitGrantsListResponse)](../../models/operations/benefitgrantslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |