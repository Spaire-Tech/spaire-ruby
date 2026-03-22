# WebhookProductCreatedPayload

Sent when a new product is created.

**Discord & Slack support:** Basic


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  | product.created                                                      |
| `timestamp`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [Models::Components::Product](../../models/shared/product.md)        | :heavy_check_mark:                                                   | A product.                                                           |                                                                      |