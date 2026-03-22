# WebhookCustomerStateChangedPayload

Sent when a customer state has changed.

It's triggered when:

* Customer is created, updated or deleted.
* A subscription is created or updated.
* A benefit is granted or revoked.

**Discord & Slack support:** Basic


## Fields

| Field                                                                                                          | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    | Example                                                                                                        |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `type`                                                                                                         | *::String*                                                                                                     | :heavy_check_mark:                                                                                             | N/A                                                                                                            | customer.state_changed                                                                                         |
| `timestamp`                                                                                                    | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html)                                           | :heavy_check_mark:                                                                                             | N/A                                                                                                            |                                                                                                                |
| `data`                                                                                                         | [Models::Components::CustomerState](../../models/shared/customerstate.md)                                      | :heavy_check_mark:                                                                                             | A customer along with additional state information:<br/><br/>* Active subscriptions<br/>* Granted benefits<br/>* Active meters |                                                                                                                |