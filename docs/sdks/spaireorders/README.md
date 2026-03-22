# CustomerPortal.Orders

## Overview

### Available Operations

* [list](#list) - List Orders
* [get](#get) - Get Order
* [update](#update) - Update Order
* [invoice](#invoice) - Get Order Invoice
* [get_payment_status](#get_payment_status) - Get Order Payment Status
* [confirm_retry_payment](#confirm_retry_payment) - Confirm Retry Payment

## list

List orders of the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:list" method="get" path="/v1/customer-portal/orders/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Operations::CustomerPortalOrdersListRequest.new
res = s.customer_portal.orders.list(request: req, security: Models::Operations::CustomerPortalOrdersListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.list_resource_customer_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                           | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                           | [Models::Operations::CustomerPortalOrdersListRequest](../../models/operations/customerportalorderslistrequest.md)   | :heavy_check_mark:                                                                                                  | The request object to use for the request.                                                                          |
| `security`                                                                                                          | [Models::Operations::CustomerPortalOrdersListSecurity](../../models/operations/customerportalorderslistsecurity.md) | :heavy_check_mark:                                                                                                  | The security requirements to use for the request.                                                                   |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersListResponse)](../../models/operations/customerportalorderslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an order by ID for the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:get" method="get" path="/v1/customer-portal/orders/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.orders.get(security: Models::Operations::CustomerPortalOrdersGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                         | Type                                                                                                              | Required                                                                                                          | Description                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                        | [Models::Operations::CustomerPortalOrdersGetSecurity](../../models/operations/customerportalordersgetsecurity.md) | :heavy_check_mark:                                                                                                | The security requirements to use for the request.                                                                 |
| `id`                                                                                                              | *::String*                                                                                                        | :heavy_check_mark:                                                                                                | The order ID.                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersGetResponse)](../../models/operations/customerportalordersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an order for the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:update" method="patch" path="/v1/customer-portal/orders/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.orders.update(security: Models::Operations::CustomerPortalOrdersUpdateSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>', body: Models::Components::CustomerOrderUpdate.new(
  billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  )
))

unless res.customer_order.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                               | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                              | [Models::Operations::CustomerPortalOrdersUpdateSecurity](../../models/operations/customerportalordersupdatesecurity.md) | :heavy_check_mark:                                                                                                      | The security requirements to use for the request.                                                                       |
| `id`                                                                                                                    | *::String*                                                                                                              | :heavy_check_mark:                                                                                                      | The order ID.                                                                                                           |
| `body`                                                                                                                  | [Models::Components::CustomerOrderUpdate](../../models/shared/customerorderupdate.md)                                   | :heavy_check_mark:                                                                                                      | N/A                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersUpdateResponse)](../../models/operations/customerportalordersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## invoice

Get an order's invoice data.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:invoice" method="get" path="/v1/customer-portal/orders/{id}/invoice" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.orders.invoice(security: Models::Operations::CustomerPortalOrdersInvoiceSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_order_invoice.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                 | Type                                                                                                                      | Required                                                                                                                  | Description                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                | [Models::Operations::CustomerPortalOrdersInvoiceSecurity](../../models/operations/customerportalordersinvoicesecurity.md) | :heavy_check_mark:                                                                                                        | The security requirements to use for the request.                                                                         |
| `id`                                                                                                                      | *::String*                                                                                                                | :heavy_check_mark:                                                                                                        | The order ID.                                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersInvoiceResponse)](../../models/operations/customerportalordersinvoiceresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_payment_status

Get the current payment status for an order.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:get_payment_status" method="get" path="/v1/customer-portal/orders/{id}/payment-status" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.orders.get_payment_status(security: Models::Operations::CustomerPortalOrdersGetPaymentStatusSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_order_payment_status.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                   | Type                                                                                                                                        | Required                                                                                                                                    | Description                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                  | [Models::Operations::CustomerPortalOrdersGetPaymentStatusSecurity](../../models/operations/customerportalordersgetpaymentstatussecurity.md) | :heavy_check_mark:                                                                                                                          | The security requirements to use for the request.                                                                                           |
| `id`                                                                                                                                        | *::String*                                                                                                                                  | :heavy_check_mark:                                                                                                                          | The order ID.                                                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersGetPaymentStatusResponse)](../../models/operations/customerportalordersgetpaymentstatusresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## confirm_retry_payment

Confirm a retry payment using a Stripe confirmation token.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:orders:confirm_retry_payment" method="post" path="/v1/customer-portal/orders/{id}/confirm-payment" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.orders.confirm_retry_payment(security: Models::Operations::CustomerPortalOrdersConfirmRetryPaymentSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>', body: Models::Components::CustomerOrderConfirmPayment.new)

unless res.customer_order_payment_confirmation.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalOrdersConfirmRetryPaymentSecurity](../../models/operations/customerportalordersconfirmretrypaymentsecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |
| `id`                                                                                                                                              | *::String*                                                                                                                                        | :heavy_check_mark:                                                                                                                                | The order ID.                                                                                                                                     |
| `body`                                                                                                                                            | [Models::Components::CustomerOrderConfirmPayment](../../models/shared/customerorderconfirmpayment.md)                                             | :heavy_check_mark:                                                                                                                                | N/A                                                                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalOrdersConfirmRetryPaymentResponse)](../../models/operations/customerportalordersconfirmretrypaymentresponse.md)**

### Errors

| Error Type                               | Status Code                              | Content Type                             |
| ---------------------------------------- | ---------------------------------------- | ---------------------------------------- |
| Models::Errors::ResourceNotFound         | 404                                      | application/json                         |
| Models::Errors::PaymentAlreadyInProgress | 409                                      | application/json                         |
| Models::Errors::OrderNotEligibleForRetry | 422                                      | application/json                         |
| Errors::APIError                         | 4XX, 5XX                                 | \*/\*                                    |