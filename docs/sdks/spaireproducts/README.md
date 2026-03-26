# Products.Products

## Overview

### Available Operations

* [preview_tax](#preview_tax) - Preview Tax

## preview_tax

Estimate tax for a product price given a customer location and quantity.
Uses the configured tax provider (Stripe Tax) to calculate applicable taxes.

**Scopes**: `products:read` `products:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="products:products:preview_tax" method="post" path="/v1/products/tax-preview" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::ProductTaxPreviewRequest.new(
  amount: 428_098,
  currency: 'Kina',
  country: 'Guatemala'
)
res = s.products.products.preview_tax(request: req)

unless res.product_tax_preview_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                       | Type                                                                                            | Required                                                                                        | Description                                                                                     |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `request`                                                                                       | [Models::Components::ProductTaxPreviewRequest](../../models/shared/producttaxpreviewrequest.md) | :heavy_check_mark:                                                                              | The request object to use for the request.                                                      |

### Response

**[T.nilable(Models::Operations::ProductsProductsPreviewTaxResponse)](../../models/operations/productsproductspreviewtaxresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |