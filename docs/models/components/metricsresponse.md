# MetricsResponse

Metrics response schema.


## Fields

| Field                                                                             | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `periods`                                                                         | T::Array<[Models::Components::MetricPeriod](../../models/shared/metricperiod.md)> | :heavy_check_mark:                                                                | List of data for each timestamp.                                                  |
| `totals`                                                                          | [Models::Components::MetricsTotals](../../models/shared/metricstotals.md)         | :heavy_check_mark:                                                                | N/A                                                                               |
| `metrics`                                                                         | [Models::Components::Metrics](../../models/shared/metrics.md)                     | :heavy_check_mark:                                                                | N/A                                                                               |