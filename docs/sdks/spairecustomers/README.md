# CustomerPortal.Customers

## Overview

### Available Operations

* [get](#get) - Get Customer
* [update](#update) - Update Customer
* [list_payment_methods](#list_payment_methods) - List Customer Payment Methods
* [add_payment_method](#add_payment_method) - Add Customer Payment Method
* [confirm_payment_method](#confirm_payment_method) - Confirm Customer Payment Method
* [delete_payment_method](#delete_payment_method) - Delete Customer Payment Method

## get

Get authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:get" method="get" path="/v1/customer-portal/customers/me" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customers.get(security: Models::Operations::CustomerPortalCustomersGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_portal_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                               | Type                                                                                                                    | Required                                                                                                                | Description                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                              | [Models::Operations::CustomerPortalCustomersGetSecurity](../../models/operations/customerportalcustomersgetsecurity.md) | :heavy_check_mark:                                                                                                      | The security requirements to use for the request.                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersGetResponse)](../../models/operations/customerportalcustomersgetresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update

Update authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:update" method="patch" path="/v1/customer-portal/customers/me" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::CustomerPortalCustomerUpdate.new(
  billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  )
)
res = s.customer_portal.customers.update(request: req, security: Models::Operations::CustomerPortalCustomersUpdateSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_portal_customer.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                     | [Models::Components::CustomerPortalCustomerUpdate](../../models/shared/customerportalcustomerupdate.md)                       | :heavy_check_mark:                                                                                                            | The request object to use for the request.                                                                                    |
| `security`                                                                                                                    | [Models::Operations::CustomerPortalCustomersUpdateSecurity](../../models/operations/customerportalcustomersupdatesecurity.md) | :heavy_check_mark:                                                                                                            | The security requirements to use for the request.                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersUpdateResponse)](../../models/operations/customerportalcustomersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_payment_methods

Get saved payment methods of the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:list_payment_methods" method="get" path="/v1/customer-portal/customers/me/payment-methods" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customers.list_payment_methods(security: Models::Operations::CustomerPortalCustomersListPaymentMethodsSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), page: 1, limit: 10)

unless res.list_resource_customer_payment_method.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                            | [Models::Operations::CustomerPortalCustomersListPaymentMethodsSecurity](../../models/operations/customerportalcustomerslistpaymentmethodssecurity.md) | :heavy_check_mark:                                                                                                                                    | The security requirements to use for the request.                                                                                                     |
| `page`                                                                                                                                                | *T.nilable(::Integer)*                                                                                                                                | :heavy_minus_sign:                                                                                                                                    | Page number, defaults to 1.                                                                                                                           |
| `limit`                                                                                                                                               | *T.nilable(::Integer)*                                                                                                                                | :heavy_minus_sign:                                                                                                                                    | Size of a page, defaults to 10. Maximum is 100.                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersListPaymentMethodsResponse)](../../models/operations/customerportalcustomerslistpaymentmethodsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## add_payment_method

Add a payment method to the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:add_payment_method" method="post" path="/v1/customer-portal/customers/me/payment-methods" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::CustomerPaymentMethodCreate.new(
  confirmation_token_id: '<id>',
  set_default: false,
  return_url: 'https://yearly-custom.net/'
)
res = s.customer_portal.customers.add_payment_method(request: req, security: Models::Operations::CustomerPortalCustomersAddPaymentMethodSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_payment_method_create_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                         | Type                                                                                                                                              | Required                                                                                                                                          | Description                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                         | [Models::Components::CustomerPaymentMethodCreate](../../models/shared/customerpaymentmethodcreate.md)                                             | :heavy_check_mark:                                                                                                                                | The request object to use for the request.                                                                                                        |
| `security`                                                                                                                                        | [Models::Operations::CustomerPortalCustomersAddPaymentMethodSecurity](../../models/operations/customerportalcustomersaddpaymentmethodsecurity.md) | :heavy_check_mark:                                                                                                                                | The security requirements to use for the request.                                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersAddPaymentMethodResponse)](../../models/operations/customerportalcustomersaddpaymentmethodresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## confirm_payment_method

Confirm a payment method for the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:confirm_payment_method" method="post" path="/v1/customer-portal/customers/me/payment-methods/confirm" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::CustomerPaymentMethodConfirm.new(
  setup_intent_id: '<id>',
  set_default: true
)
res = s.customer_portal.customers.confirm_payment_method(request: req, security: Models::Operations::CustomerPortalCustomersConfirmPaymentMethodSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_payment_method_create_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                 | Type                                                                                                                                                      | Required                                                                                                                                                  | Description                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                 | [Models::Components::CustomerPaymentMethodConfirm](../../models/shared/customerpaymentmethodconfirm.md)                                                   | :heavy_check_mark:                                                                                                                                        | The request object to use for the request.                                                                                                                |
| `security`                                                                                                                                                | [Models::Operations::CustomerPortalCustomersConfirmPaymentMethodSecurity](../../models/operations/customerportalcustomersconfirmpaymentmethodsecurity.md) | :heavy_check_mark:                                                                                                                                        | The security requirements to use for the request.                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersConfirmPaymentMethodResponse)](../../models/operations/customerportalcustomersconfirmpaymentmethodresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::CustomerNotReady    | 400                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_payment_method

Delete a payment method from the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:customers:delete_payment_method" method="delete" path="/v1/customer-portal/customers/me/payment-methods/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.customers.delete_payment_method(security: Models::Operations::CustomerPortalCustomersDeletePaymentMethodSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                               | Type                                                                                                                                                    | Required                                                                                                                                                | Description                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                              | [Models::Operations::CustomerPortalCustomersDeletePaymentMethodSecurity](../../models/operations/customerportalcustomersdeletepaymentmethodsecurity.md) | :heavy_check_mark:                                                                                                                                      | The security requirements to use for the request.                                                                                                       |
| `id`                                                                                                                                                    | *::String*                                                                                                                                              | :heavy_check_mark:                                                                                                                                      | N/A                                                                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalCustomersDeletePaymentMethodResponse)](../../models/operations/customerportalcustomersdeletepaymentmethodresponse.md)**

### Errors

| Error Type                                             | Status Code                                            | Content Type                                           |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| Models::Errors::PaymentMethodInUseByActiveSubscription | 400                                                    | application/json                                       |
| Models::Errors::ResourceNotFound                       | 404                                                    | application/json                                       |
| Models::Errors::HTTPValidationError                    | 422                                                    | application/json                                       |
| Errors::APIError                                       | 4XX, 5XX                                               | \*/\*                                                  |