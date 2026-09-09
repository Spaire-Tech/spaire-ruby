# Community

## Overview

### Available Operations

* [get_event_public](#get_event_public) - Get Community Event (Public Share)
* [download_event_ics](#download_event_ics) - Download Event Calendar File (.ics)

## get_event_public

Get Community Event (Public Share)

### Example Usage

<!-- UsageSnippet language="ruby" operationID="community:get_event_public" method="get" path="/v1/community/public/events/{event_id}" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.community.get_event_public(event_id: '<value>')

unless res.community_event_public.nil?
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `event_id`         | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CommunityGetEventPublicResponse)](../../models/operations/communitygeteventpublicresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |

## download_event_ics

Serves the same calendar file the RSVP confirmation email
attaches. Public so the public event page can deep-link "Add to
Calendar" without an auth round-trip — the ICS only contains data
already exposed by GET /events/{event_id}.

### Example Usage

<!-- UsageSnippet language="ruby" operationID="community:download_event_ics" method="get" path="/v1/community/public/events/{event_id}/ics" -->
```ruby
require 'spaire'

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new
res = s.community.download_event_ics(event_id: '<value>')

if res.status_code == 200
  # handle response
end

```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `event_id`         | *::String*         | :heavy_check_mark: | N/A                |

### Response

**[T.nilable(Models::Operations::CommunityDownloadEventIcsResponse)](../../models/operations/communitydownloadeventicsresponse.md)**

### Errors

| Error Type                          | Status Code                         | Content Type                        |
| ----------------------------------- | ----------------------------------- | ----------------------------------- |
| Models::Errors::HTTPValidationError | 422                                 | application/json                    |
| Errors::APIError                    | 4XX, 5XX                            | \*/\*                               |