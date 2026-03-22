# Checkouts

## Overview

### Available Operations

* [list](#list) - List Checkout Sessions
* [create](#create) - Create Checkout Session
* [get](#get) - Get Checkout Session
* [client_get](#client_get) - Get Checkout Session from Client

## list

List checkout sessions.

**Scopes**: `checkouts:read` `checkouts:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="checkouts:list" method="get" path="/v1/checkouts/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::CheckoutsListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.checkouts.list(request: req)

unless res.list_resource_checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Operations::CheckoutsListRequest](../../models/operations/checkoutslistrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::CheckoutsListResponse)](../../models/operations/checkoutslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a checkout session.

**Scopes**: `checkouts:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="checkouts:create" method="post" path="/v1/checkouts/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::CheckoutCreate.new(
  locale: 'en',
  customer_name: 'John Doe',
  customer_billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  ),
  products: [
    '<value 1>',
    '<value 2>',
    '<value 3>',
  ]
)
res = s.checkouts.create(request: req)

unless res.checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `request`                                                                   | [Models::Components::CheckoutCreate](../../models/shared/checkoutcreate.md) | :heavy_check_mark:                                                          | The request object to use for the request.                                  |

### Response

**[T.nilable(Models::Operations::CheckoutsCreateResponse)](../../models/operations/checkoutscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a checkout session by ID.

**Scopes**: `checkouts:read` `checkouts:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="checkouts:get" method="get" path="/v1/checkouts/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.checkouts.get(id: '<value>')

unless res.checkout.nil?
  # handle response
end

```

### Parameters

| Parameter                | Type                     | Required                 | Description              |
| ------------------------ | ------------------------ | ------------------------ | ------------------------ |
| `id`                     | *::String*               | :heavy_check_mark:       | The checkout session ID. |

### Response

**[T.nilable(Models::Operations::CheckoutsGetResponse)](../../models/operations/checkoutsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## client_get

Get a checkout session by client secret.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="checkouts:client_get" method="get" path="/v1/checkouts/client/{client_secret}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.checkouts.client_get(client_secret: '<value>')

unless res.checkout_public.nil?
  # handle response
end

```

### Parameters

| Parameter                           | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `client_secret`                     | *::String*                          | :heavy_check_mark:                  | The checkout session client secret. |

### Response

**[T.nilable(Models::Operations::CheckoutsClientGetResponse)](../../models/operations/checkoutsclientgetresponse.md)**

### Errors

| Error Type                           | Status Code                          | Content Type                         |
| ------------------------------------ | ------------------------------------ | ------------------------------------ |
| Models::Errors::ResourceNotFound     | 404                                  | application/json                     |
| Models::Errors::ExpiredCheckoutError | 410                                  | application/json                     |
| Models::Errors::HTTPValidationError  | 422                                  | application/json                     |
| Errors::APIError                     | 4XX, 5XX                             | \*/\*                                |