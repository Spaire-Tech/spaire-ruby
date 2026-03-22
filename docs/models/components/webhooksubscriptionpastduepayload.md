# WebhookSubscriptionPastDuePayload

Sent when a subscription payment fails and the subscription enters `past_due` status.

This is a recoverable state - the customer can update their payment method to restore the subscription.
Benefits may be revoked depending on the organization's grace period settings.

If payment retries are exhausted, a `subscription.revoked` event will be sent.

**Discord & Slack support:** Full


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | subscription.past_due                                                   |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::Subscription](../../models/shared/subscription.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |