# WebhookSubscriptionCreatedPayload

Sent when a new subscription is created.

When this event occurs, the subscription `status` might not be `active` yet, as we can still have to wait for the first payment to be processed.

**Discord & Slack support:** Full


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | subscription.created                                                    |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |