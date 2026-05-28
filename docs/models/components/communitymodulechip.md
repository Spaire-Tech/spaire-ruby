# CommunityModuleChip

Module-only chip used on activity pins where the activity is
scoped to a module (no lesson). Mirrors CommunityLessonChip's shape
so the FE can render the same pill component.


## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `module_id`           | *::String*            | :heavy_check_mark:    | N/A                   |
| `module_title`        | *T.nilable(::String)* | :heavy_minus_sign:    | N/A                   |