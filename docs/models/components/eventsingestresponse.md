# EventsIngestResponse


## Fields

| Field                               | Type                                | Required                            | Description                         |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | ----------------------------------- |
| `inserted`                          | *::Integer*                         | :heavy_check_mark:                  | Number of events inserted.          |
| `duplicates`                        | *T.nilable(::Integer)*              | :heavy_minus_sign:                  | Number of duplicate events skipped. |