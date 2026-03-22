# CustomerPortal.Organizations

## Overview

### Available Operations

* [get](#get) - Get Organization

## get

Get a customer portal's organization by slug.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:organizations:get" method="get" path="/v1/customer-portal/organizations/{slug}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.organizations.get(slug: '<value>')

unless res.customer_organization_data.nil?
  # handle response
end

```

### Parameters

| Parameter              | Type                   | Required               | Description            |
| ---------------------- | ---------------------- | ---------------------- | ---------------------- |
| `slug`                 | *::String*             | :heavy_check_mark:     | The organization slug. |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrganizationsGetResponse)](../../models/operations/customerportalorganizationsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |