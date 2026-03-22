# CustomerPortalMemberCreate

Schema for adding a new member to the customer's team.


## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `email`                                                                        | *::String*                                                                     | :heavy_check_mark:                                                             | The email address of the new member.                                           |
| `name`                                                                         | *T.nilable(::String)*                                                          | :heavy_minus_sign:                                                             | The name of the new member (optional).                                         |
| `role`                                                                         | [T.nilable(Models::Components::MemberRole)](../../models/shared/memberrole.md) | :heavy_minus_sign:                                                             | N/A                                                                            |