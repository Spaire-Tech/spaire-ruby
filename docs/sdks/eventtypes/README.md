# EventTypes

## Overview

### Available Operations

* [list](#list) - List Event Types
* [update](#update) - Update Event Type

## list

List event types with aggregated statistics.

**Scopes**: `events:read` `events:write`

### Example Usage

<!-- UsageSnippet language="ruby" operationID="event-types:list" method="get" path="/v1/event-types/" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)

req = Models::Operations::EventTypesListRequest.new(
  organization_id: '1dbfc517-0bbf-4301-9ba8-555ca42b9737'
)
res = s.event_types.list(request: req)

unless res.list_resource_event_type_with_stats.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                                     | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `request`                                                                                     | [Models::Operations::EventTypesListRequest](../../models/operations/eventtypeslistrequest.md) | :heavy_check_mark:                                                                            | The request object to use for the request.                                                    |

### Response

**[T.nilable(Models::Operations::EventTypesListResponse)](../../models/operations/eventtypeslistresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## update

Update an event type's label.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="event-types:update" method="patch" path="/v1/event-types/{id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: '<YOUR_BEARER_TOKEN_HERE>'
)
res = s.event_types.update(id: '<value>', body: Models::Components::EventTypeUpdate.new(
  label: '<value>'
))

unless res.event_type.nil?
  # handle response
end

```

### Parameters

| Parameter                                                                     | Type                                                                          | Required                                                                      | Description                                                                   |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| `id`                                                                          | *::String*                                                                    | :heavy_check_mark:                                                            | The event type ID.                                                            |
| `body`                                                                        | [Models::Components::EventTypeUpdate](../../models/shared/eventtypeupdate.md) | :heavy_check_mark:                                                            | N/A                                                                           |

### Response

**[T.nilable(Models::Operations::EventTypesUpdateResponse)](../../models/operations/eventtypesupdateresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |