# CustomerPortal.Subscriptions

## Overview

### Available Operations

* [list](#list) - List Subscriptions
* [get](#get) - Get Subscription
* [cancel](#cancel) - Cancel Subscription
* [update](#update) - Update Subscription

## list

List subscriptions of the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:subscriptions:list" method="get" path="/v1/customer-portal/subscriptions/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Operations::CustomerPortalSubscriptionsListRequest.new
res = s.customer_portal.subscriptions.list(request: req, security: Models::Operations::CustomerPortalSubscriptionsListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.list_resource_customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                         | Type                                                                                                                              | Required                                                                                                                          | Description                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                         | [Models::Operations::CustomerPortalSubscriptionsListRequest](../../models/operations/customerportalsubscriptionslistrequest.md)   | :heavy_check_mark:                                                                                                                | The request object to use for the request.                                                                                        |
| `security`                                                                                                                        | [Models::Operations::CustomerPortalSubscriptionsListSecurity](../../models/operations/customerportalsubscriptionslistsecurity.md) | :heavy_check_mark:                                                                                                                | The security requirements to use for the request.                                                                                 |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsListResponse)](../../models/operations/customerportalsubscriptionslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a subscription for the authenticated customer.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:subscriptions:get" method="get" path="/v1/customer-portal/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.subscriptions.get(security: Models::Operations::CustomerPortalSubscriptionsGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                       | Type                                                                                                                            | Required                                                                                                                        | Description                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                      | [Models::Operations::CustomerPortalSubscriptionsGetSecurity](../../models/operations/customerportalsubscriptionsgetsecurity.md) | :heavy_check_mark:                                                                                                              | The security requirements to use for the request.                                                                               |
| `id`                                                                                                                            | *::String*                                                                                                                      | :heavy_check_mark:                                                                                                              | The subscription ID.                                                                                                            |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsGetResponse)](../../models/operations/customerportalsubscriptionsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## cancel

Cancel a subscription of the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:subscriptions:cancel" method="delete" path="/v1/customer-portal/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.subscriptions.cancel(security: Models::Operations::CustomerPortalSubscriptionsCancelSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                             | Type                                                                                                                                  | Required                                                                                                                              | Description                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                            | [Models::Operations::CustomerPortalSubscriptionsCancelSecurity](../../models/operations/customerportalsubscriptionscancelsecurity.md) | :heavy_check_mark:                                                                                                                    | The security requirements to use for the request.                                                                                     |
| `id`                                                                                                                                  | *::String*                                                                                                                            | :heavy_check_mark:                                                                                                                    | The subscription ID.                                                                                                                  |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsCancelResponse)](../../models/operations/customerportalsubscriptionscancelresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |

## update

Update a subscription of the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:subscriptions:update" method="patch" path="/v1/customer-portal/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.subscriptions.update(security: Models::Operations::CustomerPortalSubscriptionsUpdateSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>', body: Models::Components::CustomerSubscriptionCancel.new)

unless res.customer_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                              | Type                                                                                                                                                                                                                   | Required                                                                                                                                                                                                               | Description                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                                                                             | [Models::Operations::CustomerPortalSubscriptionsUpdateSecurity](../../models/operations/customerportalsubscriptionsupdatesecurity.md)                                                                                  | :heavy_check_mark:                                                                                                                                                                                                     | The security requirements to use for the request.                                                                                                                                                                      |
| `id`                                                                                                                                                                                                                   | *::String*                                                                                                                                                                                                             | :heavy_check_mark:                                                                                                                                                                                                     | The subscription ID.                                                                                                                                                                                                   |
| `body`                                                                                                                                                                                                                 | [T.any(Models::Components::CustomerSubscriptionUpdateProduct, Models::Components::CustomerSubscriptionUpdateSeats, Models::Components::CustomerSubscriptionCancel)](../../models/shared/customersubscriptionupdate.md) | :heavy_check_mark:                                                                                                                                                                                                     | N/A                                                                                                                                                                                                                    |

### Response

**[T.nilable(Models::Operations::CustomerPortalSubscriptionsUpdateResponse)](../../models/operations/customerportalsubscriptionsupdateresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |