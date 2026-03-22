# CustomerSeats

## Overview

### Available Operations

* [list_seats](#list_seats) - List Seats
* [assign_seat](#assign_seat) - Assign Seat
* [revoke_seat](#revoke_seat) - Revoke Seat
* [resend_invitation](#resend_invitation) - Resend Invitation
* [get_claim_info](#get_claim_info) - Get Claim Info
* [claim_seat](#claim_seat) - Claim Seat

## list_seats

**Scopes**: `customer_seats:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:list_seats" method="get" path="/v1/customer-seats" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_seats.list_seats

unless res.seats_list.nil?
  # handle response
end

```

### Parameters

| Parameter             | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `subscription_id`     | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |
| `order_id`            | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |

### Response

**[T.nilable(Models::Operations::CustomerSeatsListSeatsResponse)](../../models/operations/customerseatslistseatsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## assign_seat

**Scopes**: `customer_seats:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:assign_seat" method="post" path="/v1/customer-seats" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Components::SeatAssign.new
res = s.customer_seats.assign_seat(request: req)

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [Models::Components::SeatAssign](../../models/shared/seatassign.md) | :heavy_check_mark:                                                  | The request object to use for the request.                          |

### Response

**[T.nilable(Models::Operations::CustomerSeatsAssignSeatResponse)](../../models/operations/customerseatsassignseatresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## revoke_seat

**Scopes**: `customer_seats:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:revoke_seat" method="delete" path="/v1/customer-seats/{seat_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_seats.revoke_seat(seat_id: '<value>')

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `seat_id`          | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CustomerSeatsRevokeSeatResponse)](../../models/operations/customerseatsrevokeseatresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## resend_invitation

**Scopes**: `customer_seats:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:resend_invitation" method="post" path="/v1/customer-seats/{seat_id}/resend" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.customer_seats.resend_invitation(seat_id: '<value>')

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `seat_id`          | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CustomerSeatsResendInvitationResponse)](../../models/operations/customerseatsresendinvitationresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## get_claim_info

Get Claim Info

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:get_claim_info" method="get" path="/v1/customer-seats/claim/{invitation_token}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_seats.get_claim_info(invitation_token: '<value>')

unless res.seat_claim_info.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `invitation_token` | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CustomerSeatsGetClaimInfoResponse)](../../models/operations/customerseatsgetclaiminforesponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## claim_seat

Claim Seat

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer-seats:claim_seat" method="post" path="/v1/customer-seats/claim" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::SeatClaim.new(
  invitation_token: '<value>'
)
res = s.customer_seats.claim_seat(request: req)

unless res.customer_seat_claim_response.nil?
  # handle response
end

```

### Parameters

| Parameter                                                         | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `request`                                                         | [Models::Components::SeatClaim](../../models/shared/seatclaim.md) | :heavy_check_mark:                                                | The request object to use for the request.                        |

### Response

**[T.nilable(Models::Operations::CustomerSeatsClaimSeatResponse)](../../models/operations/customerseatsclaimseatresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |