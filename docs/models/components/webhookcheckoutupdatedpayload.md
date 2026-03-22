# WebhookCheckoutUpdatedPayload

Sent when a checkout is updated.

**Discord & Slack support:** Basic


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  | checkout.updated                                                     |
| `timestamp`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [Models::Components::Checkout](../../models/shared/checkout.md)      | :heavy_check_mark:                                                   | Checkout session data retrieved using an access token.               |                                                                      |