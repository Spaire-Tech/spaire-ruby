# Subscriptions

## Overview

### Available Operations

* [list](#list) - List Subscriptions
* [create](#create) - Create Subscription
* [export](#export) - Export Subscriptions
* [get](#get) - Get Subscription
* [revoke](#revoke) - Revoke Subscription
* [update](#update) - Update Subscription

## list

List subscriptions.

**Scopes**: `subscriptions:read` `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:list" method="get" path="/v1/subscriptions/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::SubscriptionsListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.subscriptions.list(request: req)

unless res.list_resource_subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                           | Type                                                                                                | Required                                                                                            | Description                                                                                         |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| `request`                                                                                           | [Models::Operations::SubscriptionsListRequest](../../models/operations/subscriptionslistrequest.md) | :heavy_check_mark:                                                                                  | The request object to use for the request.                                                          |

### Response

**[T.nilable(Models::Operations::SubscriptionsListResponse)](../../models/operations/subscriptionslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a subscription programmatically.

This endpoint only allows to create subscription on free products.
For paid products, use the checkout flow.

No initial order will be created and no confirmation email will be sent.

**Scopes**: `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:create" method="post" path="/v1/subscriptions/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::SubscriptionCreateCustomer.new(
  product_id: 'd8dd2de1-21b7-4a41-8bc3-ce909c0cfe23',
  customer_id: '992fae2a-2a17-4b7a-8d9e-e287cf90131b'
)
res = s.subscriptions.create(request: req)

unless res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                         | Type                                                                                                                                                                              | Required                                                                                                                                                                          | Description                                                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                         | [T.any(Models::Components::SubscriptionCreateCustomer, Models::Components::SubscriptionCreateExternalCustomer)](../../models/operations/subscriptionscreatesubscriptioncreate.md) | :heavy_check_mark:                                                                                                                                                                | The request object to use for the request.                                                                                                                                        |

### Response

**[T.nilable(Models::Operations::SubscriptionsCreateResponse)](../../models/operations/subscriptionscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## export

Export subscriptions as a CSV file.

**Scopes**: `subscriptions:read` `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:export" method="get" path="/v1/subscriptions/export" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.subscriptions.export(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737')

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `organization_id`                                                                           | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/organizationid.md) | :heavy_minus_sign:                                                                          | Filter by organization ID.                                                                  |

### Response

**[T.nilable(Models::Operations::SubscriptionsExportResponse)](../../models/operations/subscriptionsexportresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a subscription by ID.

**Scopes**: `subscriptions:read` `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:get" method="get" path="/v1/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.subscriptions.get(id: '<value>')

unless res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The subscription ID. |

### Response

**[T.nilable(Models::Operations::SubscriptionsGetResponse)](../../models/operations/subscriptionsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## revoke

Revoke a subscription, i.e cancel immediately.

**Scopes**: `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:revoke" method="delete" path="/v1/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.subscriptions.revoke(id: '<value>')

unless res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter            | Type                 | Required             | Description          |
| -------------------- | -------------------- | -------------------- | -------------------- |
| `id`                 | *::String*           | :heavy_check_mark:   | The subscription ID. |

### Response

**[T.nilable(Models::Operations::SubscriptionsRevokeResponse)](../../models/operations/subscriptionsrevokeresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::SubscriptionLocked          | 409                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |

## update

Update a subscription.

**Scopes**: `subscriptions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="subscriptions:update" method="patch" path="/v1/subscriptions/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.subscriptions.update(id: '<value>', body: Models::Components::SubscriptionUpdateTrial.new(
  trial_end: DateTime.iso8601('2024-12-03T14:44:14.136Z')
))

unless res.subscription.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                                                                                                                                                        | Type                                                                                                                                                                                                                                                                                                                                                                             | Required                                                                                                                                                                                                                                                                                                                                                                         | Description                                                                                                                                                                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `id`                                                                                                                                                                                                                                                                                                                                                                             | *::String*                                                                                                                                                                                                                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                               | The subscription ID.                                                                                                                                                                                                                                                                                                                                                             |
| `body`                                                                                                                                                                                                                                                                                                                                                                           | [T.any(Models::Components::SubscriptionUpdateProduct, Models::Components::SubscriptionUpdateDiscount, Models::Components::SubscriptionUpdateTrial, Models::Components::SubscriptionUpdateSeats, Models::Components::SubscriptionUpdateBillingPeriod, Models::Components::SubscriptionCancel, Models::Components::SubscriptionRevoke)](../../models/shared/subscriptionupdate.md) | :heavy_check_mark:                                                                                                                                                                                                                                                                                                                                                               | N/A                                                                                                                                                                                                                                                                                                                                                                              |

### Response

**[T.nilable(Models::Operations::SubscriptionsUpdateResponse)](../../models/operations/subscriptionsupdateresponse.md)**

### Errors

| Error Type                                  | Status Code                                 | Content Type                                |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Models::Errors::AlreadyCanceledSubscription | 403                                         | application/json                            |
| Models::Errors::ResourceNotFound            | 404                                         | application/json                            |
| Models::Errors::SubscriptionLocked          | 409                                         | application/json                            |
| Models::Errors::HTTPValidationError         | 422                                         | application/json                            |
| Errors::APIError                            | 4XX, 5XX                                    | \*/\*                                       |