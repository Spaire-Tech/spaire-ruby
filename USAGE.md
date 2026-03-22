<!-- Start SDK Example Usage [usage] -->
```ruby
require "spaire"

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: "<YOUR_BEARER_TOKEN_HERE>"
)
res = s.organizations.list(page: 1, limit: 10)

unless res.list_resource_organization.nil?
  # handle response
end

```
<!-- End SDK Example Usage [usage] -->