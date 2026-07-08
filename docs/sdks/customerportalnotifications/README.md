# CustomerPortalNotifications

## Overview

### Available Operations

* [list_notifications](#list_notifications) - List Customer Notifications
* [unread_count](#unread_count) - Unread Notification Count
* [mark_read](#mark_read) - Mark Notification Read
* [mark_all_read](#mark_all_read) - Mark All Notifications Read
* [get_preferences](#get_preferences) - Get Notification Preferences
* [update_preferences](#update_preferences) - Update Notification Preferences

## list_notifications

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:list_notifications" method="get" path="/v1/customer-portal/notifications/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_notifications.list_notifications(security: Models::Operations::CustomerPortalNotificationsListNotificationsSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.response_customer_portal_notifications_list_notifications.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                   | Type                                                                                                                                                        | Required                                                                                                                                                    | Description                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                                  | [Models::Operations::CustomerPortalNotificationsListNotificationsSecurity](../../models/operations/customerportalnotificationslistnotificationssecurity.md) | :heavy_check_mark:                                                                                                                                          | The security requirements to use for the request.                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsListNotificationsResponse)](../../models/operations/customerportalnotificationslistnotificationsresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## unread_count

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:unread_count" method="get" path="/v1/customer-portal/notifications/unread-count" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_notifications.unread_count(security: Models::Operations::CustomerPortalNotificationsUnreadCountSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.unread_count_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                       | Type                                                                                                                                            | Required                                                                                                                                        | Description                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                      | [Models::Operations::CustomerPortalNotificationsUnreadCountSecurity](../../models/operations/customerportalnotificationsunreadcountsecurity.md) | :heavy_check_mark:                                                                                                                              | The security requirements to use for the request.                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsUnreadCountResponse)](../../models/operations/customerportalnotificationsunreadcountresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## mark_read

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:mark_read" method="post" path="/v1/customer-portal/notifications/{notification_id}/read" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_notifications.mark_read(security: Models::Operations::CustomerPortalNotificationsMarkReadSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
), notification_id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                 | Type                                                                                                                                      | Required                                                                                                                                  | Description                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                | [Models::Operations::CustomerPortalNotificationsMarkReadSecurity](../../models/operations/customerportalnotificationsmarkreadsecurity.md) | :heavy_check_mark:                                                                                                                        | The security requirements to use for the request.                                                                                         |
| `notification_id`                                                                                                                         | *::String*                                                                                                                                | :heavy_check_mark:                                                                                                                        | N/A                                                                                                                                       |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsMarkReadResponse)](../../models/operations/customerportalnotificationsmarkreadresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## mark_all_read

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:mark_all_read" method="post" path="/v1/customer-portal/notifications/read-all" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_notifications.mark_all_read(security: Models::Operations::CustomerPortalNotificationsMarkAllReadSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                       | Type                                                                                                                                            | Required                                                                                                                                        | Description                                                                                                                                     |
| ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                      | [Models::Operations::CustomerPortalNotificationsMarkAllReadSecurity](../../models/operations/customerportalnotificationsmarkallreadsecurity.md) | :heavy_check_mark:                                                                                                                              | The security requirements to use for the request.                                                                                               |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsMarkAllReadResponse)](../../models/operations/customerportalnotificationsmarkallreadresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## get_preferences

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:get_preferences" method="get" path="/v1/customer-portal/notifications/preferences" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.customer_portal_notifications.get_preferences(security: Models::Operations::CustomerPortalNotificationsGetPreferencesSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_notification_preferences_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                             | Type                                                                                                                                                  | Required                                                                                                                                              | Description                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                                                            | [Models::Operations::CustomerPortalNotificationsGetPreferencesSecurity](../../models/operations/customerportalnotificationsgetpreferencessecurity.md) | :heavy_check_mark:                                                                                                                                    | The security requirements to use for the request.                                                                                                     |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsGetPreferencesResponse)](../../models/operations/customerportalnotificationsgetpreferencesresponse.md)**

### Errors

| Error Type       | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| Errors::APIError | 4XX, 5XX         | \*/\*            |

## update_preferences

**Scopes**: `customer_portal:read` `customer_portal:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="customer_portal_notifications:update_preferences" method="patch" path="/v1/customer-portal/notifications/preferences" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Components::CustomerNotificationPreferencesUpdate.new
res = s.customer_portal_notifications.update_preferences(request: req, security: Models::Operations::CustomerPortalNotificationsUpdatePreferencesSecurity.new(
  customer_session: '<YOUR_BEARER_TOKEN_HERE>'
))

unless res.customer_notification_preferences_read.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                                                                                   | Type                                                                                                                                                        | Required                                                                                                                                                    | Description                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `request`                                                                                                                                                   | [Models::Components::CustomerNotificationPreferencesUpdate](../../models/shared/customernotificationpreferencesupdate.md)                                   | :heavy_check_mark:                                                                                                                                          | The request object to use for the request.                                                                                                                  |
| `security`                                                                                                                                                  | [Models::Operations::CustomerPortalNotificationsUpdatePreferencesSecurity](../../models/operations/customerportalnotificationsupdatepreferencessecurity.md) | :heavy_check_mark:                                                                                                                                          | The security requirements to use for the request.                                                                                                           |

### Response

**[T.nilable(Models::Operations::CustomerPortalNotificationsUpdatePreferencesResponse)](../../models/operations/customerportalnotificationsupdatepreferencesresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |