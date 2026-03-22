# WebhookCustomerSeatRevokedPayload

Sent when a customer seat is revoked.

This event is triggered when access to a seat is revoked, either manually by the organization or automatically when a subscription is canceled.


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | customer_seat.revoked                                                   |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::CustomerSeat](../../models/shared/customerseat.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |