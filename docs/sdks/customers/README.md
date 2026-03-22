# Customers

## Overview

### Available Operations

* [list](#list) - List Customers
* [create](#create) - Create Customer
* [export](#export) - Export Customers
* [get](#get) - Get Customer
* [delete](#delete) - Delete Customer
* [update](#update) - Update Customer
* [get_external](#get_external) - Get Customer by External ID
* [delete_external](#delete_external) - Delete Customer by External ID
* [update_external](#update_external) - Update Customer by External ID
* [get_state](#get_state) - Get Customer State
* [get_state_external](#get_state_external) - Get Customer State by External ID

## list

List customers.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:list" method="get" path="/v1/customers/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::CustomersListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.customers.list(request: req)

unless res.list_resource_customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                   | Type                                                                                        | Required                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `request`                                                                                   | [Models::Operations::CustomersListRequest](../../models/operations/customerslistrequest.md) | :heavy_check_mark:                                                                          | The request object to use for the request.                                                  |

### Response

**[T.nilable(Models::Operations::CustomersListResponse)](../../models/operations/customerslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## create

Create a customer.

**Scopes**: `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:create" method="post" path="/v1/customers/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::CustomerCreate.new(
  external_id: 'usr_1337',
  email: 'customer@example.com',
  name: 'John Doe',
  billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  ),
  tax_id: [
    '911144442',
    'us_ein',
  ],
  type: Models::Components::CustomerType::INDIVIDUAL,
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737',
  owner: Models::Components::OwnerCreate.new(
    email: 'member@example.com',
    name: 'Jane Doe',
    external_id: 'usr_1337'
  )
)
res = s.customers.create(request: req)

unless res.customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `request`                                                                   | [Models::Components::CustomerCreate](../../models/shared/customercreate.md) | :heavy_check_mark:                                                          | The request object to use for the request.                                  |

### Response

**[T.nilable(Models::Operations::CustomersCreateResponse)](../../models/operations/customerscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## export

Export customers as a CSV file.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:export" method="get" path="/v1/customers/export" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.export(organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737')

unless res.any.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                            | Type                                                                                                                 | Required                                                                                                             | Description                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `organization_id`                                                                                                    | [T.nilable(T.any(::String, T::Array[::String]))](../../models/operations/customersexportqueryparamorganizationid.md) | :heavy_minus_sign:                                                                                                   | Filter by organization ID.                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomersExportResponse)](../../models/operations/customersexportresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a customer by ID.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:get" method="get" path="/v1/customers/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.get(id: '<value>')

unless res.customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The customer ID.   |

### Response

**[T.nilable(Models::Operations::CustomersGetResponse)](../../models/operations/customersgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete

Delete a customer.

This action cannot be undone and will immediately:
- Cancel any active subscriptions for the customer
- Revoke all their benefits
- Clear any `external_id`

Use it only in the context of deleting a user within your
own service. Otherwise, use more granular API endpoints to cancel
a specific subscription or revoke certain benefits.

Note: The customers information will nonetheless be retained for historic
orders and subscriptions.

Set `anonymize=true` to also anonymize PII for GDPR compliance.

**Scopes**: `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:delete" method="delete" path="/v1/customers/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.delete(id: '<value>', anonymize: false)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                                                                              | Type                                                                                                                                                                                                                                                   | Required                                                                                                                                                                                                                                               | Description                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id`                                                                                                                                                                                                                                                   | *::String*                                                                                                                                                                                                                                             | :heavy_check_mark:                                                                                                                                                                                                                                     | The customer ID.                                                                                                                                                                                                                                       |
| `anonymize`                                                                                                                                                                                                                                            | *T.nilable(T::Boolean)*                                                                                                                                                                                                                                | :heavy_minus_sign:                                                                                                                                                                                                                                     | If true, also anonymize the customer's personal data for GDPR compliance. This replaces email with a hashed version, hashes name and billing name (name preserved for businesses with tax_id), clears billing address, and removes OAuth account data. |

### Response

**[T.nilable(Models::Operations::CustomersDeleteResponse)](../../models/operations/customersdeleteresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update a customer.

**Scopes**: `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:update" method="patch" path="/v1/customers/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.update(id: '<value>', body: Models::Components::CustomerUpdate.new(
  email: 'customer@example.com',
  name: 'John Doe',
  billing_address: Models::Components::AddressInput.new(
    country: Models::Components::CountryAlpha2Input::US
  ),
  tax_id: [
    '911144442',
    'us_ein',
  ],
  external_id: 'usr_1337',
  type: Models::Components::CustomerType::INDIVIDUAL
))

unless res.customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `id`                                                                        | *::String*                                                                  | :heavy_check_mark:                                                          | The customer ID.                                                            |
| `body`                                                                      | [Models::Components::CustomerUpdate](../../models/shared/customerupdate.md) | :heavy_check_mark:                                                          | N/A                                                                         |

### Response

**[T.nilable(Models::Operations::CustomersUpdateResponse)](../../models/operations/customersupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_external

Get a customer by external ID.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:get_external" method="get" path="/v1/customers/external/{external_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.get_external(external_id: '<id>')

unless res.customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter                 | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `external_id`             | *::String*                | :heavy_check_mark:        | The customer external ID. |

### Response

**[T.nilable(Models::Operations::CustomersGetExternalResponse)](../../models/operations/customersgetexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## delete_external

Delete a customer by external ID.

Immediately cancels any active subscriptions and revokes any active benefits.

Set `anonymize=true` to also anonymize PII for GDPR compliance.

**Scopes**: `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:delete_external" method="delete" path="/v1/customers/external/{external_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.delete_external(external_id: '<id>', anonymize: false)

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `external_id`                                                             | *::String*                                                                | :heavy_check_mark:                                                        | The customer external ID.                                                 |
| `anonymize`                                                               | *T.nilable(T::Boolean)*                                                   | :heavy_minus_sign:                                                        | If true, also anonymize the customer's personal data for GDPR compliance. |

### Response

**[T.nilable(Models::Operations::CustomersDeleteExternalResponse)](../../models/operations/customersdeleteexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update_external

Update a customer by external ID.

**Scopes**: `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:update_external" method="patch" path="/v1/customers/external/{external_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.update_external(external_id: '<id>', body: Models::Components::CustomerUpdateExternalID.new(
  email: 'customer@example.com',
  name: 'John Doe',
  billing_address: nil,
  tax_id: [
    '911144442',
    'us_ein',
  ]
))

unless res.customer_with_members.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                       | Type                                                                                            | Required                                                                                        | Description                                                                                     |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `external_id`                                                                                   | *::String*                                                                                      | :heavy_check_mark:                                                                              | The customer external ID.                                                                       |
| `body`                                                                                          | [Models::Components::CustomerUpdateExternalID](../../models/shared/customerupdateexternalid.md) | :heavy_check_mark:                                                                              | N/A                                                                                             |

### Response

**[T.nilable(Models::Operations::CustomersUpdateExternalResponse)](../../models/operations/customersupdateexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_state

Get a customer state by ID.

The customer state includes information about
the customer's active subscriptions and benefits.

It's the ideal endpoint to use when you need to get a full overview
of a customer's status.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:get_state" method="get" path="/v1/customers/{id}/state" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.get_state(id: '<value>')

unless res.customer_state.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *::String*         | :heavy_check_mark: | The customer ID.   |

### Response

**[T.nilable(Models::Operations::CustomersGetStateResponse)](../../models/operations/customersgetstateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_state_external

Get a customer state by external ID.

The customer state includes information about
the customer's active subscriptions and benefits.

It's the ideal endpoint to use when you need to get a full overview
of a customer's status.

**Scopes**: `customers:read` `customers:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customers:get_state_external" method="get" path="/v1/customers/external/{external_id}/state" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customers.get_state_external(external_id: '<id>')

unless res.customer_state.nil?
  # handle response
end

```

### Parameters

| Parameter                 | Type                      | Required                  | Description               |
| ------------------------- | ------------------------- | ------------------------- | ------------------------- |
| `external_id`             | *::String*                | :heavy_check_mark:        | The customer external ID. |

### Response

**[T.nilable(Models::Operations::CustomersGetStateExternalResponse)](../../models/operations/customersgetstateexternalresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |