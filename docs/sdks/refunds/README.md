# Refunds

## Overview

### Available Operations

* [list](#list) - List Refunds
* [create](#create) - Create Refund

## list

List refunds.

**Scopes**: `refunds:read` `refunds:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="refunds:list" method="get" path="/v1/refunds/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::RefundsListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.refunds.list(request: req)

unless res.list_resource_refund.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                               | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `request`                                                                               | [Models::Operations::RefundsListRequest](../../models/operations/refundslistrequest.md) | :heavy_check_mark:                                                                      | The request object to use for the request.                                              |

### Response

**[T.nilable(Models::Operations::RefundsListResponse)](../../models/operations/refundslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a refund.

**Scopes**: `refunds:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="refunds:create" method="post" path="/v1/refunds/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::RefundCreate.new(
  order_id: '<value>',
  reason: Models::Components::RefundReason::SERVICE_DISRUPTION,
  amount: 90
)
res = s.refunds.create(request: req)

unless res.refund.nil?
  # handle response
end

```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [Models::Components::RefundCreate](../../models/shared/refundcreate.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |

### Response

**[T.nilable(Models::Operations::RefundsCreateResponse)](../../models/operations/refundscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::RefundedAlready     | 403                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |