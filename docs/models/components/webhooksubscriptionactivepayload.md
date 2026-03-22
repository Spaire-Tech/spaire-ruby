# WebhookSubscriptionActivePayload

Sent when a subscription becomes active,
whether because it's a new paid subscription or because payment was recovered.

**Discord & Slack support:** Full


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | subscription.active                                                     |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |