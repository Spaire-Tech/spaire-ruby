# CustomerPortal.Seats

## Overview

### Available Operations

* [list_seats](#list_seats) - List Seats
* [assign_seat](#assign_seat) - Assign Seat
* [revoke_seat](#revoke_seat) - Revoke Seat
* [resend_invitation](#resend_invitation) - Resend Invitation
* [list_claimed_subscriptions](#list_claimed_subscriptions) - List Claimed Subscriptions

## list_seats

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:seats:list_seats" method="get" path="/v1/customer-portal/seats" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.seats.list_seats(security: Models::Operations::CustomerPortalSeatsListSeatsSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.seats_list.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                   | Type                                                                                                                        | Required                                                                                                                    | Description                                                                                                                 |
| --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                  | [Models::Operations::CustomerPortalSeatsListSeatsSecurity](../../models/operations/customerportalseatslistseatssecurity.md) | :heavy_check_mark:                                                                                                          | The security requirements to use for the request.                                                                           |
| `subscription_id`                                                                                                           | *T.nilable(::String)*                                                                                                       | :heavy_minus_sign:                                                                                                          | Subscription ID                                                                                                             |
| `order_id`                                                                                                                  | *T.nilable(::String)*                                                                                                       | :heavy_minus_sign:                                                                                                          | Order ID                                                                                                                    |

### Response

**[T.nilable(Models::Operations::CustomerPortalSeatsListSeatsResponse)](../../models/operations/customerportalseatslistseatsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## assign_seat

Assign Seat

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:seats:assign_seat" method="post" path="/v1/customer-portal/seats" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::SeatAssign.new
res = s.customer_portal.seats.assign_seat(request: req, security: Models::Operations::CustomerPortalSeatsAssignSeatSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                     | [Models::Components::SeatAssign](../../models/shared/seatassign.md)                                                           | :heavy_check_mark:                                                                                                            | The request object to use for the request.                                                                                    |
| `security`                                                                                                                    | [Models::Operations::CustomerPortalSeatsAssignSeatSecurity](../../models/operations/customerportalseatsassignseatsecurity.md) | :heavy_check_mark:                                                                                                            | The security requirements to use for the request.                                                                             |

### Response

**[T.nilable(Models::Operations::CustomerPortalSeatsAssignSeatResponse)](../../models/operations/customerportalseatsassignseatresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## revoke_seat

Revoke Seat

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:seats:revoke_seat" method="delete" path="/v1/customer-portal/seats/{seat_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.seats.revoke_seat(security: Models::Operations::CustomerPortalSeatsRevokeSeatSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), seat_id: '<value>')

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                     | Type                                                                                                                          | Required                                                                                                                      | Description                                                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                    | [Models::Operations::CustomerPortalSeatsRevokeSeatSecurity](../../models/operations/customerportalseatsrevokeseatsecurity.md) | :heavy_check_mark:                                                                                                            | The security requirements to use for the request.                                                                             |
| `seat_id`                                                                                                                     | *::String*                                                                                                                    | :heavy_check_mark:                                                                                                            | N/A                                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalSeatsRevokeSeatResponse)](../../models/operations/customerportalseatsrevokeseatresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## resend_invitation

Resend Invitation

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:seats:resend_invitation" method="post" path="/v1/customer-portal/seats/{seat_id}/resend" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.seats.resend_invitation(security: Models::Operations::CustomerPortalSeatsResendInvitationSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), seat_id: '<value>')

unless res.customer_seat.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                 | Type                                                                                                                                      | Required                                                                                                                                  | Description                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                | [Models::Operations::CustomerPortalSeatsResendInvitationSecurity](../../models/operations/customerportalseatsresendinvitationsecurity.md) | :heavy_check_mark:                                                                                                                        | The security requirements to use for the request.                                                                                         |
| `seat_id`                                                                                                                                 | *::String*                                                                                                                                | :heavy_check_mark:                                                                                                                        | N/A                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalSeatsResendInvitationResponse)](../../models/operations/customerportalseatsresendinvitationresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## list_claimed_subscriptions

List all subscriptions where the authenticated customer has claimed a seat.

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal:seats:list_claimed_subscriptions" method="get" path="/v1/customer-portal/seats/subscriptions" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal.seats.list_claimed_subscriptions(security: Models::Operations::CustomerPortalSeatsListClaimedSubscriptionsSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.response_customer_portal_seats_list_claimed_subscriptions.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                 | Type                                                                                                                                                      | Required                                                                                                                                                  | Description                                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                | [Models::Operations::CustomerPortalSeatsListClaimedSubscriptionsSecurity](../../models/operations/customerportalseatslistclaimedsubscriptionssecurity.md) | :heavy_check_mark:                                                                                                                                        | The security requirements to use for the request.                                                                                                         |

### Response

**[T.nilable(Models::Operations::CustomerPortalSeatsListClaimedSubscriptionsResponse)](../../models/operations/customerportalseatslistclaimedsubscriptionsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |