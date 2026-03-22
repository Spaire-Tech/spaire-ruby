# CustomerOrderPaymentConfirmation

Response after confirming a retry payment.


## Fields

| Field                                          | Type                                           | Required                                       | Description                                    |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `status`                                       | *::String*                                     | :heavy_check_mark:                             | Payment status after confirmation.             |
| `client_secret`                                | *T.nilable(::String)*                          | :heavy_minus_sign:                             | Client secret for handling additional actions. |
| `error`                                        | *T.nilable(::String)*                          | :heavy_minus_sign:                             | Error message if confirmation failed.          |