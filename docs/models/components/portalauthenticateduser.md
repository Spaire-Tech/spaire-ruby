# PortalAuthenticatedUser

Information about the authenticated portal user.


## Fields

| Field                                                               | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `type`                                                              | *::String*                                                          | :heavy_check_mark:                                                  | Type of authenticated user: 'customer' or 'member'                  |
| `name`                                                              | *T.nilable(::String)*                                               | :heavy_check_mark:                                                  | User's name, if available.                                          |
| `email`                                                             | *::String*                                                          | :heavy_check_mark:                                                  | User's email address.                                               |
| `customer_id`                                                       | *::String*                                                          | :heavy_check_mark:                                                  | Associated customer ID.                                             |
| `member_id`                                                         | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Member ID. Only set for members.                                    |
| `role`                                                              | *T.nilable(::String)*                                               | :heavy_minus_sign:                                                  | Member role (owner, billing_manager, member). Only set for members. |