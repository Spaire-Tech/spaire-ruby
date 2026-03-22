# CustomerOrderPaymentStatus

Payment status for an order.


## Fields

| Field                            | Type                             | Required                         | Description                      |
| -------------------------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| `status`                         | *::String*                       | :heavy_check_mark:               | Current payment status.          |
| `error`                          | *T.nilable(::String)*            | :heavy_minus_sign:               | Error message if payment failed. |