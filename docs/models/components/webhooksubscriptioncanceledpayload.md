# WebhookSubscriptionCanceledPayload

Sent when a subscription is canceled.
Customers might still have access until the end of the current period.

**Discord & Slack support:** Full


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | subscription.canceled                                                   |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |