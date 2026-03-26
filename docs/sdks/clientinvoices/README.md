# ClientInvoices

## Overview

### Available Operations

* [list_client_invoices](#list_client_invoices) - List Client Invoices
* [create_client_invoice](#create_client_invoice) - Create Client Invoice
* [preview_client_invoice_pdf](#preview_client_invoice_pdf) - Preview Client Invoice PDF
* [get_client_invoice](#get_client_invoice) - Get Client Invoice
* [download_client_invoice_pdf](#download_client_invoice_pdf) - Download Client Invoice PDF
* [finalize_client_invoice](#finalize_client_invoice) - Finalize Client Invoice
* [send_client_invoice](#send_client_invoice) - Send Client Invoice
* [mark_client_invoice_paid](#mark_client_invoice_paid) - Mark Client Invoice as Paid
* [void_client_invoice](#void_client_invoice) - Void Client Invoice

## list_client_invoices

List client invoices for the authenticated organization.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:list_client_invoices" method="get" path="/v1/client-invoices/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.list_client_invoices(page: 1, limit: 10)

unless res.list_resource_client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `page`                                                                                                                                                                  | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Page number, defaults to 1.                                                                                                                                             |
| `limit`                                                                                                                                                                 | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Size of a page, defaults to 10. Maximum is 100.                                                                                                                         |
| `sorting`                                                                                                                                                               | T::Array<[Models::Components::ClientInvoiceSortProperty](../../models/shared/clientinvoicesortproperty.md)>                                                             | :heavy_minus_sign:                                                                                                                                                      | Sorting criterion. Several criteria can be used simultaneously and will be applied in order. Add a minus sign `-` before the criteria name to sort by descending order. |

### Response

**[T.nilable(Models::Operations::ClientInvoicesListClientInvoicesResponse)](../../models/operations/clientinvoiceslistclientinvoicesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_client_invoice

Create a new draft client invoice. Tax is calculated automatically.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:create_client_invoice" method="post" path="/v1/client-invoices/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::ClientInvoiceCreate.new(
  customer_id: '<value>',
  currency: 'Gibraltar Pound',
  line_items: []
)
res = s.client_invoices.create_client_invoice(request: req)

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                             | Type                                                                                  | Required                                                                              | Description                                                                           |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `request`                                                                             | [Models::Components::ClientInvoiceCreate](../../models/shared/clientinvoicecreate.md) | :heavy_check_mark:                                                                    | The request object to use for the request.                                            |

### Response

**[T.nilable(Models::Operations::ClientInvoicesCreateClientInvoiceResponse)](../../models/operations/clientinvoicescreateclientinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## preview_client_invoice_pdf

Generate a real PDF preview from form data without creating anything.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:preview_client_invoice_pdf" method="post" path="/v1/client-invoices/preview-pdf" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::ClientInvoicePreviewRequest.new(
  organization_id: '<value>',
  currency: 'Baht',
  line_items: []
)
res = s.client_invoices.preview_client_invoice_pdf(request: req)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `request`                                                                                             | [Models::Components::ClientInvoicePreviewRequest](../../models/shared/clientinvoicepreviewrequest.md) | :heavy_check_mark:                                                                                    | The request object to use for the request.                                                            |

### Response

**[T.nilable(Models::Operations::ClientInvoicesPreviewClientInvoicePdfResponse)](../../models/operations/clientinvoicespreviewclientinvoicepdfresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_client_invoice

Get a client invoice by ID.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:get_client_invoice" method="get" path="/v1/client-invoices/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.get_client_invoice(id: '<value>')

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesGetClientInvoiceResponse)](../../models/operations/clientinvoicesgetclientinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## download_client_invoice_pdf

Generate and download a PDF for the given client invoice.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:download_client_invoice_pdf" method="get" path="/v1/client-invoices/{id}/pdf" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.download_client_invoice_pdf(id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesDownloadClientInvoicePdfResponse)](../../models/operations/clientinvoicesdownloadclientinvoicepdfresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## finalize_client_invoice

Finalize a draft invoice (generates PDF) without sending the email.
Status moves from draft → open. Use this to preview the invoice before sending.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:finalize_client_invoice" method="post" path="/v1/client-invoices/{id}/finalize" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.finalize_client_invoice(id: '<value>')

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesFinalizeClientInvoiceResponse)](../../models/operations/clientinvoicesfinalizeclientinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## send_client_invoice

Finalize and send a draft invoice to the customer via Stripe.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:send_client_invoice" method="post" path="/v1/client-invoices/{id}/send" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.send_client_invoice(id: '<value>')

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesSendClientInvoiceResponse)](../../models/operations/clientinvoicessendclientinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## mark_client_invoice_paid

Mark a draft or open invoice as paid manually without going through Stripe.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:mark_client_invoice_paid" method="post" path="/v1/client-invoices/{id}/mark-paid" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.mark_client_invoice_paid(id: '<value>')

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesMarkClientInvoicePaidResponse)](../../models/operations/clientinvoicesmarkclientinvoicepaidresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## void_client_invoice

Void a draft or open invoice.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="client_invoices:void_client_invoice" method="post" path="/v1/client-invoices/{id}/void" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.client_invoices.void_client_invoice(id: '<value>')

unless res.client_invoice_schema.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::ClientInvoicesVoidClientInvoiceResponse)](../../models/operations/clientinvoicesvoidclientinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |