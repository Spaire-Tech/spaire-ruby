# Meters

## Overview

### Available Operations

* [list](#list) - List Meters
* [create](#create) - Create Meter
* [get](#get) - Get Meter
* [update](#update) - Update Meter
* [quantities](#quantities) - Get Meter Quantities

## list

List meters.

**Scopes**: `meters:read` `meters:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="meters:list" method="get" path="/v1/meters/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::MetersListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.meters.list(request: req)

unless res.list_resource_meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::MetersListRequest](../../models/operations/meterslistrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::MetersListResponse)](../../models/operations/meterslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a meter.

**Scopes**: `meters:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="meters:create" method="post" path="/v1/meters/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::MeterCreate.new(
  name: '<value>',
  filter: Models::Components::Filter.new(
    conjunction: Models::Components::FilterConjunction::OR,
    clauses: []
  ),
  aggregation: Models::Components::CountAggregation.new,
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.meters.create(request: req)

unless res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `request`                                                             | [Models::Components::MeterCreate](../../models/shared/metercreate.md) | :heavy_check_mark:                                                    | The request object to use for the request.                            |

### Response

**[T.nilable(Models::Operations::MetersCreateResponse)](../../models/operations/meterscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a meter by ID.

**Scopes**: `meters:read` `meters:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="meters:get" method="get" path="/v1/meters/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.meters.get(id: '<value>')

unless res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The meter ID.      |

### Response

**[T.nilable(Models::Operations::MetersGetResponse)](../../models/operations/metersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a meter.

**Scopes**: `meters:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="meters:update" method="patch" path="/v1/meters/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.meters.update(id: '<value>', body: Models::Components::MeterUpdate.new)

unless res.meter.nil?
  # handle response
end

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *::String*                                                            | :heavy_check_mark:                                                    | The meter ID.                                                         |
| `body`                                                                | [Models::Components::MeterUpdate](../../models/shared/meterupdate.md) | :heavy_check_mark:                                                    | N/A                                                                   |

### Response

**[T.nilable(Models::Operations::MetersUpdateResponse)](../../models/operations/metersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## quantities

Get quantities of a meter over a time period.

**Scopes**: `meters:read` `meters:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="meters:quantities" method="get" path="/v1/meters/{id}/quantities" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::MetersQuantitiesRequest.new(
  id: '<value>',
  start_timestamp: DateTime.iso8601('2026-11-25T04:37:16.823Z'),
  end_timestamp: DateTime.iso8601('2026-11-26T17:06:00.727Z'),
  interval: Models::Components::TimeInterval::DAY
)
res = s.meters.quantities(request: req)

unless res.meter_quantities.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `request`                                                                                         | [Models::Operations::MetersQuantitiesRequest](../../models/operations/metersquantitiesrequest.md) | :heavy_check_mark:                                                                                | The request object to use for the request.                                                        |

### Response

**[T.nilable(Models::Operations::MetersQuantitiesResponse)](../../models/operations/metersquantitiesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |