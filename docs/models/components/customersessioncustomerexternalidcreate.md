# CustomerSessionCustomerExternalIDCreate

Schema for creating a customer session using an external customer ID.


## Fields

| Field                                                                               | Type                                                                                | Required                                                                            | Description                                                                         | Example                                                                             |
| ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| `return_url`                                                                        | *T.nilable(::String)*                                                               | :heavy_minus_sign:                                                                  | When set, a back button will be shown in the customer portal to return to this URL. | https://example.com/account                                                         |
| `external_customer_id`                                                              | *::String*                                                                          | :heavy_check_mark:                                                                  | External ID of the customer to create a session for.                                |                                                                                     |