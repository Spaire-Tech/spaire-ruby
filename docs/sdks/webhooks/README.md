# Webhooks

## Overview

### Available Operations

* [list_webhook_endpoints](#list_webhook_endpoints) - List Webhook Endpoints
* [create_webhook_endpoint](#create_webhook_endpoint) - Create Webhook Endpoint
* [get_webhook_endpoint](#get_webhook_endpoint) - Get Webhook Endpoint
* [delete_webhook_endpoint](#delete_webhook_endpoint) - Delete Webhook Endpoint
* [update_webhook_endpoint](#update_webhook_endpoint) - Update Webhook Endpoint
* [reset_webhook_endpoint_secret](#reset_webhook_endpoint_secret) - Reset Webhook Endpoint Secret
* [list_webhook_deliveries](#list_webhook_deliveries) - List Webhook Deliveries
* [redeliver_webhook_event](#redeliver_webhook_event) - Redeliver Webhook Event

## list_webhook_endpoints

List webhook endpoints.

**Scopes**: `webhooks:read` `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:list_webhook_endpoints" method="get" path="/v1/webhooks/endpoints" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.list_webhook_endpoints(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737', page: 1, limit: 10)

unless res.list_resource_webhook_endpoint.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                             | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                     | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/queryparamorganizationid.md) | :heavy_minus_sign:                                                                                    | Filter by organization ID.                                                                            |
| `page`                                                                                                | *T.nilable(::Integer)*                                                                                | :heavy_minus_sign:                                                                                    | Page number, defaults to 1.                                                                           |
| `limit`                                                                                               | *T.nilable(::Integer)*                                                                                | :heavy_minus_sign:                                                                                    | Size of a page, defaults to 10. Maximum is 100.                                                       |

### Response

**[T.nilable(Models::Operations::WebhooksListWebhookEndpointsResponse)](../../models/operations/webhookslistwebhookendpointsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create_webhook_endpoint

Create a webhook endpoint.

**Scopes**: `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:create_webhook_endpoint" method="post" path="/v1/webhooks/endpoints" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::WebhookEndpointCreate.new(
  url: 'https://webhook.site/cb791d80-f26e-4f8c-be88-6e56054192b0',
  format: Models::Components::WebhookFormat::SLACK,
  events: [
    Models::Components::WebhookEventType::SUBSCRIPTION_ACTIVE,
  ],
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.webhooks.create_webhook_endpoint(request: req)

unless res.webhook_endpoint.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `request`                                                                                 | [Models::Components::WebhookEndpointCreate](../../models/shared/webhookendpointcreate.md) | :heavy_check_mark:                                                                        | The request object to use for the request.                                                |

### Response

**[T.nilable(Models::Operations::WebhooksCreateWebhookEndpointResponse)](../../models/operations/webhookscreatewebhookendpointresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_webhook_endpoint

Get a webhook endpoint by ID.

**Scopes**: `webhooks:read` `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:get_webhook_endpoint" method="get" path="/v1/webhooks/endpoints/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.get_webhook_endpoint(id: '<value>')

unless res.webhook_endpoint.nil?
  # handle response
end

```

### Parameters

| Parameter                | Type                     | Required                 | Description              |
| ------------------------ | ------------------------ | ------------------------ | ------------------------ |
| `id`                     | *::String*               | :heavy_check_mark:       | The webhook endpoint ID. |

### Response

**[T.nilable(Models::Operations::WebhooksGetWebhookEndpointResponse)](../../models/operations/webhooksgetwebhookendpointresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_webhook_endpoint

Delete a webhook endpoint.

**Scopes**: `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:delete_webhook_endpoint" method="delete" path="/v1/webhooks/endpoints/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.delete_webhook_endpoint(id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                | Type                     | Required                 | Description              |
| ------------------------ | ------------------------ | ------------------------ | ------------------------ |
| `id`                     | *::String*               | :heavy_check_mark:       | The webhook endpoint ID. |

### Response

**[T.nilable(Models::Operations::WebhooksDeleteWebhookEndpointResponse)](../../models/operations/webhooksdeletewebhookendpointresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_webhook_endpoint

Update a webhook endpoint.

**Scopes**: `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:update_webhook_endpoint" method="patch" path="/v1/webhooks/endpoints/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.update_webhook_endpoint(id: '<value>', body: Models::Components::WebhookEndpointUpdate.new(
  url: 'https://webhook.site/cb791d80-f26e-4f8c-be88-6e56054192b0'
))

unless res.webhook_endpoint.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                 | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `id`                                                                                      | *::String*                                                                                | :heavy_check_mark:                                                                        | The webhook endpoint ID.                                                                  |
| `body`                                                                                    | [Models::Components::WebhookEndpointUpdate](../../models/shared/webhookendpointupdate.md) | :heavy_check_mark:                                                                        | N/A                                                                                       |

### Response

**[T.nilable(Models::Operations::WebhooksUpdateWebhookEndpointResponse)](../../models/operations/webhooksupdatewebhookendpointresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## reset_webhook_endpoint_secret

Regenerate a webhook endpoint secret.

**Scopes**: `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:reset_webhook_endpoint_secret" method="patch" path="/v1/webhooks/endpoints/{id}/secret" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.reset_webhook_endpoint_secret(id: '<value>')

unless res.webhook_endpoint.nil?
  # handle response
end

```

### Parameters

| Parameter                | Type                     | Required                 | Description              |
| ------------------------ | ------------------------ | ------------------------ | ------------------------ |
| `id`                     | *::String*               | :heavy_check_mark:       | The webhook endpoint ID. |

### Response

**[T.nilable(Models::Operations::WebhooksResetWebhookEndpointSecretResponse)](../../models/operations/webhooksresetwebhookendpointsecretresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_webhook_deliveries

List webhook deliveries.

Deliveries are all the attempts to deliver a webhook event to an endpoint.

**Scopes**: `webhooks:read` `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:list_webhook_deliveries" method="get" path="/v1/webhooks/deliveries" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::WebhooksListWebhookDeliveriesRequest.new
res = s.webhooks.list_webhook_deliveries(request: req)

unless res.list_resource_webhook_delivery.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                   | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                   | [Models::Operations::WebhooksListWebhookDeliveriesRequest](../../models/operations/webhookslistwebhookdeliveriesrequest.md) | :heavy_check_mark:                                                                                                          | The request object to use for the request.                                                                                  |

### Response

**[T.nilable(Models::Operations::WebhooksListWebhookDeliveriesResponse)](../../models/operations/webhookslistwebhookdeliveriesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## redeliver_webhook_event

Schedule the re-delivery of a webhook event.

**Scopes**: `webhooks:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="webhooks:redeliver_webhook_event" method="post" path="/v1/webhooks/events/{id}/redeliver" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.webhooks.redeliver_webhook_event(id: '<value>')

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter             | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `id`                  | *::String*            | :heavy_check_mark:    | The webhook event ID. |

### Response

**[T.nilable(Models::Operations::WebhooksRedeliverWebhookEventResponse)](../../models/operations/webhooksredeliverwebhookeventresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |