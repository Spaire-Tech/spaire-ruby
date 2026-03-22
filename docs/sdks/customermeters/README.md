# CustomerMeters

## Overview

### Available Operations

* [list](#list) - List Customer Meters
* [get](#get) - Get Customer Meter

## list

List customer meters.

**Scopes**: `customer_meters:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_meters:list" method="get" path="/v1/customer-meters/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::CustomerMetersListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.customer_meters.list(request: req)

unless res.list_resource_customer_meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `request`                                                                                             | [Models::Operations::CustomerMetersListRequest](../../models/operations/customermeterslistrequest.md) | :heavy_check_mark:                                                                                    | The request object to use for the request.                                                            |

### Response

**[T.nilable(Models::Operations::CustomerMetersListResponse)](../../models/operations/customermeterslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a customer meter by ID.

**Scopes**: `customer_meters:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_meters:get" method="get" path="/v1/customer-meters/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_meters.get(id: '<value>')

unless res.customer_meter.nil?
  # handle response
end

```

### Parameters

| Parameter              | Type                   | Required               | Description            |
| ---------------------- | ---------------------- | ---------------------- | ---------------------- |
| `id`                   | *::String*             | :heavy_check_mark:     | The customer meter ID. |

### Response

**[T.nilable(Models::Operations::CustomerMetersGetResponse)](../../models/operations/customermetersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |