# Metrics

## Overview

### Available Operations

* [get](#get) - Get Metrics
* [limits](#limits) - Get Metrics Limits

## get

Get metrics about your orders and subscriptions.

Currency values are output in cents.

**Scopes**: `metrics:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="metrics:get" method="get" path="/v1/metrics/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::MetricsGetRequest.new(
  start_date: Date.parse('2026-03-14'),
  end_date: Date.parse('2026-03-18'),
  interval: Models::Components::TimeInterval::HOUR,
  organization_id: nil
)
res = s.metrics.get(request: req)

unless res.metrics_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::MetricsGetRequest](../../models/operations/metricsgetrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::MetricsGetResponse)](../../models/operations/metricsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## limits

Get the interval limits for the metrics endpoint.

**Scopes**: `metrics:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="metrics:limits" method="get" path="/v1/metrics/limits" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.metrics.limits

unless res.metrics_limits.nil?
  # handle response
end

```

### Response

**[T.nilable(Models::Operations::MetricsLimitsResponse)](../../models/operations/metricslimitsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |