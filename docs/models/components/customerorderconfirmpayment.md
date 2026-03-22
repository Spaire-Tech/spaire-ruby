# CustomerOrderConfirmPayment

Schema to confirm a retry payment using either a saved payment method or a new confirmation token.


## Fields

| Field                                                                                      | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `confirmation_token_id`                                                                    | *T.nilable(::String)*                                                                      | :heavy_minus_sign:                                                                         | ID of the Stripe confirmation token for new payment methods.                               |
| `payment_method_id`                                                                        | *T.nilable(::String)*                                                                      | :heavy_minus_sign:                                                                         | ID of an existing saved payment method.                                                    |
| `payment_processor`                                                                        | [T.nilable(Models::Components::PaymentProcessor)](../../models/shared/paymentprocessor.md) | :heavy_minus_sign:                                                                         | N/A                                                                                        |