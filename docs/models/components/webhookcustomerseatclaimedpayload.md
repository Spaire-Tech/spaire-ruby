# WebhookCustomerSeatClaimedPayload

Sent when a customer seat is claimed.

This event is triggered when a customer accepts the seat invitation and claims their access.


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             | Example                                                                 |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `type`                                                                  | *::String*                                                              | :heavy_check_mark:                                                      | N/A                                                                     | customer_seat.claimed                                                   |
| `timestamp`                                                             | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)    | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |
| `data`                                                                  | [Models::Components::CustomerSeat](../../models/shared/customerseat.md) | :heavy_check_mark:                                                      | N/A                                                                     |                                                                         |