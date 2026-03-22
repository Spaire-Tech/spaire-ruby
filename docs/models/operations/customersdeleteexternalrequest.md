# CustomersDeleteExternalRequest


## Fields

| Field                                                                     | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `external_id`                                                             | *::String*                                                                | :heavy_check_mark:                                                        | The customer external ID.                                                 |
| `anonymize`                                                               | *T.nilable(T::Boolean)*                                                   | :heavy_minus_sign:                                                        | If true, also anonymize the customer's personal data for GDPR compliance. |