# Orders

## Overview

### Available Operations

* [list](#list) - List Orders
* [export](#export) - Export Subscriptions
* [get](#get) - Get Order
* [update](#update) - Update Order
* [invoice](#invoice) - Get Order Invoice

## list

List orders.

**Scopes**: `orders:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="orders:list" method="get" path="/v1/orders/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::OrdersListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.orders.list(request: req)

unless res.list_resource_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Operations::OrdersListRequest](../../models/operations/orderslistrequest.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::OrdersListResponse)](../../models/operations/orderslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## export

Export orders as a CSV file.

**Scopes**: `orders:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="orders:export" method="get" path="/v1/orders/export" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.orders.export(organization_id: nil)

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                               | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                       | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/ordersexportqueryparamorganizationidfilter.md) | :heavy_minus_sign:                                                                                                      | Filter by organization ID.                                                                                              |
| `product_id`                                                                                                            | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/ordersexportqueryparamproductidfilter.md)      | :heavy_minus_sign:                                                                                                      | Filter by product ID.                                                                                                   |

### Response

**[T.nilable(Models::Operations::OrdersExportResponse)](../../models/operations/ordersexportresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an order by ID.

**Scopes**: `orders:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="orders:get" method="get" path="/v1/orders/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.orders.get(id: '<value>')

unless res.order.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The order ID.      |

### Response

**[T.nilable(Models::Operations::OrdersGetResponse)](../../models/operations/ordersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an order.

**Scopes**: `orders:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="orders:update" method="patch" path="/v1/orders/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.orders.update(id: '<value>', body: Models::Components::OrderUpdate.new(
  billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  )
))

unless res.order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *::String*                                                            | :heavy_check_mark:                                                    | The order ID.                                                         |
| `body`                                                                | [Models::Components::OrderUpdate](../../models/shared/orderupdate.md) | :heavy_check_mark:                                                    | N/A                                                                   |

### Response

**[T.nilable(Models::Operations::OrdersUpdateResponse)](../../models/operations/ordersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## invoice

Get an order's invoice data.

**Scopes**: `orders:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="orders:invoice" method="get" path="/v1/orders/{id}/invoice" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.orders.invoice(id: '<value>')

unless res.order_invoice.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The order ID.      |

### Response

**[T.nilable(Models::Operations::OrdersInvoiceResponse)](../../models/operations/ordersinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |