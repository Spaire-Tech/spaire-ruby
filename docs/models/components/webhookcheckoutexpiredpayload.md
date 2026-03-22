# WebhookCheckoutExpiredPayload

Sent when a checkout expires.

This event fires when a checkout reaches its expiration time without being completed.
Developers can use this to send reminder emails or track checkout abandonment.

**Discord & Slack support:** Basic


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  | checkout.expired                                                     |
| `timestamp`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [Models::Components::Checkout](../../models/shared/checkout.md)      | :heavy_check_mark:                                                   | Checkout session data retrieved using an access token.               |                                                                      |