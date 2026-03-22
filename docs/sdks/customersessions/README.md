# CustomerSessions

## Overview

### Available Operations

* [create](#create) - Create Customer Session

## create

Create a customer session.

For organizations with `member_model_enabled`, this will automatically
create a member session for the owner member of the customer.

**Scopes**: `customer_sessions:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-sessions:create" method="post" path="/v1/customer-sessions/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::CustomerSessionCustomerExternalIDCreate.new(
  return_url: 'https://example.com/account',
  external_customer_id: '<id>'
)
res = s.customer_sessions.create(request: req)

unless res.customer_session.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                                                         | Type                                                                                                                                                                                              | Required                                                                                                                                                                                          | Description                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                                                         | [T.any(Models::Components::CustomerSessionCustomerIDCreate, Models::Components::CustomerSessionCustomerExternalIDCreate)](../../models/operations/customersessionscreatecustomersessioncreate.md) | :heavy_check_mark:                                                                                                                                                                                | The request object to use for the request.                                                                                                                                                        |

### Response

**[T.nilable(Models::Operations::CustomerSessionsCreateResponse)](../../models/operations/customersessionscreateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |