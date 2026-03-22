# CustomerPortalMember

A member of the customer's team as seen in the customer portal.


## Fields

| Field                                                                | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `created_at`                                                         | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Creation timestamp of the object.                                    |
| `modified_at`                                                        | [Date](https://ruby-doc.org/stdlib-2.6.1/libdoc/date/rdoc/Date.html) | :heavy_check_mark:                                                   | Last modification timestamp of the object.                           |
| `id`                                                                 | *::String*                                                           | :heavy_check_mark:                                                   | The ID of the object.                                                |
| `email`                                                              | *::String*                                                           | :heavy_check_mark:                                                   | The email address of the member.                                     |
| `name`                                                               | *T.nilable(::String)*                                                | :heavy_check_mark:                                                   | The name of the member.                                              |
| `role`                                                               | [Models::Components::MemberRole](../../models/shared/memberrole.md)  | :heavy_check_mark:                                                   | N/A                                                                  |