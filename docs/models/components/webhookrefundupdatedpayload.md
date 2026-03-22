# WebhookRefundUpdatedPayload

Sent when a refund is updated.

**Discord & Slack support:** Full


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  | refund.updated                                                       |
| `timestamp`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [Models::Components::Refund](../../models/shared/refund.md)          | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |