# Products

## Overview

### Available Operations

* [list](#list) - List Products
* [create](#create) - Create Product
* [get](#get) - Get Product
* [update](#update) - Update Product
* [update_benefits](#update_benefits) - Update Product Benefits

## list

List products.

**Scopes**: `products:read` `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:list" method="get" path="/v1/products/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::ProductsListRequest.new(
  organization_id: nil
)
res = s.products.list(request: req)

unless res.list_resource_product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `request`                                                                                 | [Models::Operations::ProductsListRequest](../../models/operations/productslistrequest.md) | :heavy_check_mark:                                                                        | The request object to use for the request.                                                |

### Response

**[T.nilable(Models::Operations::ProductsListResponse)](../../models/operations/productslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a product.

**Scopes**: `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:create" method="post" path="/v1/products/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::ProductCreateOneTime.new(
  name: '<value>',
  prices: [
    Models::Components::ProductPriceCustomCreate.new(
      amount_type: 'custom',
      minimum_amount: 50
    ),
  ],
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.products.create(request: req)

unless res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                           | Type                                                                                                                                | Required                                                                                                                            | Description                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                           | [T.any(Models::Components::ProductCreateRecurring, Models::Components::ProductCreateOneTime)](../../models/shared/productcreate.md) | :heavy_check_mark:                                                                                                                  | The request object to use for the request.                                                                                          |

### Response

**[T.nilable(Models::Operations::ProductsCreateResponse)](../../models/operations/productscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a product by ID.

**Scopes**: `products:read` `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:get" method="get" path="/v1/products/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.products.get(id: '<value>')

unless res.product.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ProductsGetResponse)](../../models/operations/productsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a product.

**Scopes**: `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:update" method="patch" path="/v1/products/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.products.update(id: '<value>', body: Models::Components::ProductUpdate.new)

unless res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id`                                                                      | *::String*                                                                | :heavy_check_mark:                                                        | N/A                                                                       |
| `body`                                                                    | [Models::Components::ProductUpdate](../../models/shared/productupdate.md) | :heavy_check_mark:                                                        | N/A                                                                       |

### Response

**[T.nilable(Models::Operations::ProductsUpdateResponse)](../../models/operations/productsupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_benefits

Update benefits granted by a product.

**Scopes**: `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:update_benefits" method="post" path="/v1/products/{id}/benefits" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.products.update_benefits(id: '<value>', body: Models::Components::ProductBenefitsUpdate.new(
  benefits: [
    '<value 1>',
    '<value 2>',
    '<value 3>',
  ]
))

unless res.product.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `id`                                                                                      | *::String*                                                                                | :heavy_check_mark:                                                                        | N/A                                                                                       |
| `body`                                                                                    | [Models::Components::ProductBenefitsUpdate](../../models/shared/productbenefitsupdate.md) | :heavy_check_mark:                                                                        | N/A                                                                                       |

### Response

**[T.nilable(Models::Operations::ProductsUpdateBenefitsResponse)](../../models/operations/productsupdatebenefitsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::NotPermitted        | 403                                 | application/json                    |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |