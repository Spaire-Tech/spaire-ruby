# CustomerWallet

A wallet represents your balance with an organization.

You can top-up your wallet and use the balance to pay for usage.


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          | Example                                                              |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the object.                                                |                                                                      |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |                                                                      |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |                                                                      |
| `customer_id`                                                        | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the customer that owns the wallet.                         | 992fae2a-2a17-4b7a-8d9e-e287cf90131b                                 |
| `balance`                                                            | *::Integer*                                                          | :heavy_check_mark:                                                   | The current balance of the wallet, in cents.                         | 5000                                                                 |
| `currency`                                                           | *::String*                                                           | :heavy_check_mark:                                                   | The currency of the wallet.                                          | usd                                                                  |