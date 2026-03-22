# CustomerOrderUpdate

Schema to update an order.


## Fields

| Field                                                                                                      | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `billing_name`                                                                                             | *T.nilable(::String)*                                                                                      | :heavy_minus_sign:                                                                                         | The name of the customer that should appear on the invoice.                                                |
| `billing_address`                                                                                          | [T.nilable(Models::Components::AddressInput)](../../models/shared/addressinput.md)                         | :heavy_minus_sign:                                                                                         | The address of the customer that should appear on the invoice. Country and state fields cannot be updated. |