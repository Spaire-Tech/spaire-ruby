# MemberUpdate

Schema for updating a member.


## Fields

| Field                                                                          | Type                                                                           | Required                                                                       | Description                                                                    | Example                                                                        |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `name`                                                                         | *T.nilable(::String)*                                                          | :heavy_minus_sign:                                                             | N/A                                                                            | Jane Doe                                                                       |
| `role`                                                                         | [T.nilable(Models::Components::MemberRole)](../../models/shared/memberrole.md) | :heavy_minus_sign:                                                             | The role of the member within the customer.                                    |                                                                                |