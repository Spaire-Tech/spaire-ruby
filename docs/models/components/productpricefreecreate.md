# ProductPriceFreeCreate

Schema to create a free price.


## Fields

| Field                                                                                                  | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `amount_type`                                                                                          | *::String*                                                                                             | :heavy_check_mark:                                                                                     | N/A                                                                                                    |
| `price_currency`                                                                                       | [T.nilable(Models::Components::PresentmentCurrency)](../../models/shared/presentmentcurrency.md)       | :heavy_minus_sign:                                                                                     | N/A                                                                                                    |
| `tax_behavior`                                                                                         | [T.nilable(Models::Components::TaxBehaviorOption)](../../models/shared/taxbehavioroption.md)           | :heavy_minus_sign:                                                                                     | The tax behavior of the price. If not set, it will default to the organization's default tax behavior. |