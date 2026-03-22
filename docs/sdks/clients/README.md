# Oauth2.Clients

## Overview

### Available Operations

* [create](#create) - Create Client
* [get](#get) - Get Client
* [update](#update) - Update Client
* [delete](#delete) - Delete Client

## create

Create an OAuth2 client.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:clients:oauth2:create_client" method="post" path="/v1/oauth2/register" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::OAuth2ClientConfiguration.new(
  redirect_uris: [
    'https://impolite-hippodrome.com/',
    'https://acidic-tomography.net/',
  ],
  client_name: '<value>'
)
res = s.oauth2.clients.create(request: req)

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                         | Type                                                                                              | Required                                                                                          | Description                                                                                       |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `request`                                                                                         | [Models::Components::OAuth2ClientConfiguration](../../models/shared/oauth2clientconfiguration.md) | :heavy_check_mark:                                                                                | The request object to use for the request.                                                        |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2CreateClientResponse)](../../models/operations/oauth2clientsoauth2createclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get an OAuth2 client by Client ID.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:clients:oauth2:get_client" method="get" path="/v1/oauth2/register/{client_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.oauth2.clients.get(client_id: '<id>')

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `client_id`        | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2GetClientResponse)](../../models/operations/oauth2clientsoauth2getclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an OAuth2 client.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:clients:oauth2:update_client" method="put" path="/v1/oauth2/register/{client_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.oauth2.clients.update(client_id: '<id>', body: Models::Components::OAuth2ClientConfigurationUpdate.new(
  redirect_uris: [
    'https://classic-cantaloupe.org',
    'https://corrupt-status.biz/',
  ],
  client_name: '<value>',
  client_id: '<id>'
))

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                     | Type                                                                                                          | Required                                                                                                      | Description                                                                                                   |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `client_id`                                                                                                   | *::String*                                                                                                    | :heavy_check_mark:                                                                                            | N/A                                                                                                           |
| `body`                                                                                                        | [Models::Components::OAuth2ClientConfigurationUpdate](../../models/shared/oauth2clientconfigurationupdate.md) | :heavy_check_mark:                                                                                            | N/A                                                                                                           |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2UpdateClientResponse)](../../models/operations/oauth2clientsoauth2updateclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete an OAuth2 client.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="oauth2:clients:oauth2:delete_client" method="delete" path="/v1/oauth2/register/{client_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.oauth2.clients.delete(client_id: '<id>')

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `client_id`        | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::Oauth2ClientsOauth2DeleteClientResponse)](../../models/operations/oauth2clientsoauth2deleteclientresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |