# CustomerPortal.Wallets

## Overview

### Available Operations

* [list](#list) - List Wallets
* [get](#get) - Get Wallet

## list

List wallets of the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:wallets:list" method="get" path="/v1/customer-portal/wallets/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.wallets.list(security: Models::Operations::CustomerPortalWalletsListSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), page: 1, limit: 10)

unless res.list_resource_customer_wallet.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                              | [Models::Operations::CustomerPortalWalletsListSecurity](../../models/operations/customerportalwalletslistsecurity.md)                                                   | :heavy_check_mark:                                                                                                                                                      | The security requirements to use for the request.                                                                                                                       |
| `page`                                                                                                                                                                  | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Page number, defaults to 1.                                                                                                                                             |
| `limit`                                                                                                                                                                 | *T.nilable(::Integer)*                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Size of a page, defaults to 10. Maximum is 100.                                                                                                                         |
| `sorting`                                                                                                                                                               | T::Array<[Models::Components::CustomerWalletSortProperty](../../models/shared/customerwalletsortproperty.md)>                                                           | :heavy_minus_sign:                                                                                                                                                      | Sorting criterion. Several criteria can be used simultaneously and will be applied in order. Add a minus sign `-` before the criteria name to sort by descending order. |

### Response

**[T.nilable(Models::Operations::CustomerPortalWalletsListResponse)](../../models/operations/customerportalwalletslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get

Get a wallet by ID for the authenticated customer.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:wallets:get" method="get" path="/v1/customer-portal/wallets/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.wallets.get(security: Models::Operations::CustomerPortalWalletsGetSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), id: '<value>')

unless res.customer_wallet.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                           | Type                                                                                                                | Required                                                                                                            | Description                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                          | [Models::Operations::CustomerPortalWalletsGetSecurity](../../models/operations/customerportalwalletsgetsecurity.md) | :heavy_check_mark:                                                                                                  | The security requirements to use for the request.                                                                   |
| `id`                                                                                                                | *::String*                                                                                                          | :heavy_check_mark:                                                                                                  | The wallet ID.                                                                                                      |

### Response

**[T.nilable(Models::Operations::CustomerPortalWalletsGetResponse)](../../models/operations/customerportalwalletsgetresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::ResourceNotFound    | 404                                 | application/json                    |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |