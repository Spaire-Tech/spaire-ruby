# Permission

The permission level to grant. Read more about roles and their permissions on [GitHub documentation](https://docs.github.com/en/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/repository-roles-for-an-organization#permissions-for-each-role).

## Example Usage

```ruby
require "spaire"

value = Permission::PULL

# Open enum: use .deserialize() to create instances from custom string values
custom = Permission.deserialize("custom_value")
```


## Values

| Name       | Value      |
| ---------- | ---------- |
| `PULL`     | pull       |
| `TRIAGE`   | triage     |
| `PUSH`     | push       |
| `MAINTAIN` | maintain   |
| `ADMIN`    | admin      |