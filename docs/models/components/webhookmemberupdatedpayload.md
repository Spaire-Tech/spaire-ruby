# WebhookMemberUpdatedPayload

Sent when a member is updated.

This event is triggered when member details are updated,
such as their name or role within the customer.

**Discord & Slack support:** Basic


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `type`                                                               | *::String*                                                           | :heavy_check_mark:                                                   | N/A                                                                  | member.updated                                                       |
| `timestamp`                                                          | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | N/A                                                                  |                                                                      |
| `data`                                                               | [Models::Components::Member](../../models/shared/member.md)          | :heavy_check_mark:                                                   | A member of a customer.                                              |                                                                      |