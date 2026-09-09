# BenefitCourseAccessProperties

Properties for a benefit of type `course_access`.

The benefit is internal plumbing — it's created automatically when a
course is published, and its grant handler enrolls the buying
customer in the course. The only configuration is which course it
points at.


## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `course_id`        | *::String*         | :heavy_check_mark: | N/A                |