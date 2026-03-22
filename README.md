# spaire

Developer-friendly & type-safe Ruby SDK specifically catered to leverage *spaire* API.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=spaire&utm_campaign=ruby)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<br /><br />
> [!IMPORTANT]
> This SDK is not yet ready for production use. To complete setup please follow the steps outlined in your [workspace](https://app.speakeasy.com/org/spaire/spaire-workspace). Delete this section before > publishing to a package manager.

<!-- Start Summary [summary] -->
## Summary

Spaire API: Spaire HTTP and Webhooks API

Read the docs at https://docs.spairehq.com/api-reference
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [spaire](#spaire)
  * [SDK Installation](#sdk-installation)
  * [SDK Example Usage](#sdk-example-usage)
  * [Authentication](#authentication)
  * [Available Resources and Operations](#available-resources-and-operations)
  * [Error Handling](#error-handling)
  * [Server Selection](#server-selection)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start SDK Installation [installation] -->
## SDK Installation

The SDK can be installed using [RubyGems](https://rubygems.org/):

```bash
gem install spaire
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name           | Type | Scheme      |
| -------------- | ---- | ----------- |
| `access_token` | http | HTTP Bearer |

To authenticate with the API the `access_token` parameter must be set when initializing the SDK client instance. For example:
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

### Per-Operation Security Schemes

Some operations in this SDK require the security scheme to be specified at the request level. For example:
```ruby
require "spaire"

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new

req = Models::Operations::CustomerPortalBenefitGrantsListRequest.new
res = s.customer_portal.benefit_grants.list(
  request: req,
  security: Models::Operations::CustomerPortalBenefitGrantsListSecurity.new
)

unless res.list_resource_customer_benefit_grant.nil?
  # handle response
end

```
<!-- End Authentication [security] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

<details open>
<summary>Available methods</summary>

### [BenefitGrants](docs/sdks/benefitgrants/README.md)

* [list](docs/sdks/benefitgrants/README.md#list) - List Benefit Grants

### [Benefits](docs/sdks/benefits/README.md)

* [list](docs/sdks/benefits/README.md#list) - List Benefits
* [create](docs/sdks/benefits/README.md#create) - Create Benefit
* [get](docs/sdks/benefits/README.md#get) - Get Benefit
* [delete](docs/sdks/benefits/README.md#delete) - Delete Benefit
* [update](docs/sdks/benefits/README.md#update) - Update Benefit
* [grants](docs/sdks/benefits/README.md#grants) - List Benefit Grants

### [CheckoutLinks](docs/sdks/checkoutlinks/README.md)

* [list](docs/sdks/checkoutlinks/README.md#list) - List Checkout Links
* [create](docs/sdks/checkoutlinks/README.md#create) - Create Checkout Link
* [get](docs/sdks/checkoutlinks/README.md#get) - Get Checkout Link
* [delete](docs/sdks/checkoutlinks/README.md#delete) - Delete Checkout Link
* [update](docs/sdks/checkoutlinks/README.md#update) - Update Checkout Link

### [Checkouts](docs/sdks/checkouts/README.md)

* [list](docs/sdks/checkouts/README.md#list) - List Checkout Sessions
* [create](docs/sdks/checkouts/README.md#create) - Create Checkout Session
* [get](docs/sdks/checkouts/README.md#get) - Get Checkout Session
* [client_get](docs/sdks/checkouts/README.md#client_get) - Get Checkout Session from Client

### [ClientInvoices](docs/sdks/clientinvoices/README.md)

* [list_client_invoices](docs/sdks/clientinvoices/README.md#list_client_invoices) - List Client Invoices
* [create_client_invoice](docs/sdks/clientinvoices/README.md#create_client_invoice) - Create Client Invoice
* [get_client_invoice](docs/sdks/clientinvoices/README.md#get_client_invoice) - Get Client Invoice
* [download_client_invoice_pdf](docs/sdks/clientinvoices/README.md#download_client_invoice_pdf) - Download Client Invoice PDF
* [finalize_client_invoice](docs/sdks/clientinvoices/README.md#finalize_client_invoice) - Finalize Client Invoice
* [send_client_invoice](docs/sdks/clientinvoices/README.md#send_client_invoice) - Send Client Invoice
* [mark_client_invoice_paid](docs/sdks/clientinvoices/README.md#mark_client_invoice_paid) - Mark Client Invoice as Paid
* [void_client_invoice](docs/sdks/clientinvoices/README.md#void_client_invoice) - Void Client Invoice

### [CustomFields](docs/sdks/customfields/README.md)

* [list](docs/sdks/customfields/README.md#list) - List Custom Fields
* [create](docs/sdks/customfields/README.md#create) - Create Custom Field
* [get](docs/sdks/customfields/README.md#get) - Get Custom Field
* [delete](docs/sdks/customfields/README.md#delete) - Delete Custom Field
* [update](docs/sdks/customfields/README.md#update) - Update Custom Field

### [CustomerMeters](docs/sdks/customermeters/README.md)

* [list](docs/sdks/customermeters/README.md#list) - List Customer Meters
* [get](docs/sdks/customermeters/README.md#get) - Get Customer Meter

### [CustomerPortal.BenefitGrants](docs/sdks/spairebenefitgrants/README.md)

* [list](docs/sdks/spairebenefitgrants/README.md#list) - List Benefit Grants
* [get](docs/sdks/spairebenefitgrants/README.md#get) - Get Benefit Grant
* [update](docs/sdks/spairebenefitgrants/README.md#update) - Update Benefit Grant

### [CustomerPortal.CustomerMeters](docs/sdks/spairecustomermeters/README.md)

* [list](docs/sdks/spairecustomermeters/README.md#list) - List Meters
* [get](docs/sdks/spairecustomermeters/README.md#get) - Get Customer Meter

### [CustomerPortal.CustomerSession](docs/sdks/customersession/README.md)

* [introspect](docs/sdks/customersession/README.md#introspect) - Introspect Customer Session
* [get_authenticated_user](docs/sdks/customersession/README.md#get_authenticated_user) - Get Authenticated Portal User

### [CustomerPortal.Customers](docs/sdks/spairecustomers/README.md)

* [get](docs/sdks/spairecustomers/README.md#get) - Get Customer
* [update](docs/sdks/spairecustomers/README.md#update) - Update Customer
* [list_payment_methods](docs/sdks/spairecustomers/README.md#list_payment_methods) - List Customer Payment Methods
* [add_payment_method](docs/sdks/spairecustomers/README.md#add_payment_method) - Add Customer Payment Method
* [confirm_payment_method](docs/sdks/spairecustomers/README.md#confirm_payment_method) - Confirm Customer Payment Method
* [delete_payment_method](docs/sdks/spairecustomers/README.md#delete_payment_method) - Delete Customer Payment Method

### [CustomerPortal.Downloadables](docs/sdks/downloadables/README.md)

* [list](docs/sdks/downloadables/README.md#list) - List Downloadables

### [CustomerPortal.LicenseKeys](docs/sdks/spairelicensekeys/README.md)

* [list](docs/sdks/spairelicensekeys/README.md#list) - List License Keys
* [get](docs/sdks/spairelicensekeys/README.md#get) - Get License Key
* [validate](docs/sdks/spairelicensekeys/README.md#validate) - Validate License Key
* [activate](docs/sdks/spairelicensekeys/README.md#activate) - Activate License Key
* [deactivate](docs/sdks/spairelicensekeys/README.md#deactivate) - Deactivate License Key

### [CustomerPortal.Members](docs/sdks/spairemembers/README.md)

* [list_members](docs/sdks/spairemembers/README.md#list_members) - List Members
* [add_member](docs/sdks/spairemembers/README.md#add_member) - Add Member
* [remove_member](docs/sdks/spairemembers/README.md#remove_member) - Remove Member
* [update_member](docs/sdks/spairemembers/README.md#update_member) - Update Member

### [CustomerPortal.Orders](docs/sdks/spaireorders/README.md)

* [list](docs/sdks/spaireorders/README.md#list) - List Orders
* [get](docs/sdks/spaireorders/README.md#get) - Get Order
* [update](docs/sdks/spaireorders/README.md#update) - Update Order
* [invoice](docs/sdks/spaireorders/README.md#invoice) - Get Order Invoice
* [get_payment_status](docs/sdks/spaireorders/README.md#get_payment_status) - Get Order Payment Status
* [confirm_retry_payment](docs/sdks/spaireorders/README.md#confirm_retry_payment) - Confirm Retry Payment

### [CustomerPortal.Organizations](docs/sdks/spaireorganizations/README.md)

* [get](docs/sdks/spaireorganizations/README.md#get) - Get Organization

### [CustomerPortal.Seats](docs/sdks/seats/README.md)

* [list_seats](docs/sdks/seats/README.md#list_seats) - List Seats
* [assign_seat](docs/sdks/seats/README.md#assign_seat) - Assign Seat
* [revoke_seat](docs/sdks/seats/README.md#revoke_seat) - Revoke Seat
* [resend_invitation](docs/sdks/seats/README.md#resend_invitation) - Resend Invitation
* [list_claimed_subscriptions](docs/sdks/seats/README.md#list_claimed_subscriptions) - List Claimed Subscriptions

### [CustomerPortal.Subscriptions](docs/sdks/spairesubscriptions/README.md)

* [list](docs/sdks/spairesubscriptions/README.md#list) - List Subscriptions
* [get](docs/sdks/spairesubscriptions/README.md#get) - Get Subscription
* [cancel](docs/sdks/spairesubscriptions/README.md#cancel) - Cancel Subscription
* [update](docs/sdks/spairesubscriptions/README.md#update) - Update Subscription

### [CustomerPortal.Wallets](docs/sdks/wallets/README.md)

* [list](docs/sdks/wallets/README.md#list) - List Wallets
* [get](docs/sdks/wallets/README.md#get) - Get Wallet

### [CustomerSeats](docs/sdks/customerseats/README.md)

* [list_seats](docs/sdks/customerseats/README.md#list_seats) - List Seats
* [assign_seat](docs/sdks/customerseats/README.md#assign_seat) - Assign Seat
* [revoke_seat](docs/sdks/customerseats/README.md#revoke_seat) - Revoke Seat
* [resend_invitation](docs/sdks/customerseats/README.md#resend_invitation) - Resend Invitation
* [get_claim_info](docs/sdks/customerseats/README.md#get_claim_info) - Get Claim Info
* [claim_seat](docs/sdks/customerseats/README.md#claim_seat) - Claim Seat

### [CustomerSessions](docs/sdks/customersessions/README.md)

* [create](docs/sdks/customersessions/README.md#create) - Create Customer Session

### [Customers](docs/sdks/customers/README.md)

* [list](docs/sdks/customers/README.md#list) - List Customers
* [create](docs/sdks/customers/README.md#create) - Create Customer
* [export](docs/sdks/customers/README.md#export) - Export Customers
* [get](docs/sdks/customers/README.md#get) - Get Customer
* [delete](docs/sdks/customers/README.md#delete) - Delete Customer
* [update](docs/sdks/customers/README.md#update) - Update Customer
* [get_external](docs/sdks/customers/README.md#get_external) - Get Customer by External ID
* [delete_external](docs/sdks/customers/README.md#delete_external) - Delete Customer by External ID
* [update_external](docs/sdks/customers/README.md#update_external) - Update Customer by External ID
* [get_state](docs/sdks/customers/README.md#get_state) - Get Customer State
* [get_state_external](docs/sdks/customers/README.md#get_state_external) - Get Customer State by External ID

### [Discounts](docs/sdks/discounts/README.md)

* [list](docs/sdks/discounts/README.md#list) - List Discounts
* [create](docs/sdks/discounts/README.md#create) - Create Discount
* [get](docs/sdks/discounts/README.md#get) - Get Discount
* [delete](docs/sdks/discounts/README.md#delete) - Delete Discount
* [update](docs/sdks/discounts/README.md#update) - Update Discount

### [Disputes](docs/sdks/disputes/README.md)

* [list](docs/sdks/disputes/README.md#list) - List Disputes
* [get](docs/sdks/disputes/README.md#get) - Get Dispute

### [EventTypes](docs/sdks/eventtypes/README.md)

* [list](docs/sdks/eventtypes/README.md#list) - List Event Types
* [update](docs/sdks/eventtypes/README.md#update) - Update Event Type

### [Events](docs/sdks/events/README.md)

* [list](docs/sdks/events/README.md#list) - List Events
* [list_names](docs/sdks/events/README.md#list_names) - List Event Names
* [get](docs/sdks/events/README.md#get) - Get Event
* [ingest](docs/sdks/events/README.md#ingest) - Ingest Events

### [Files](docs/sdks/files/README.md)

* [list](docs/sdks/files/README.md#list) - List Files
* [create](docs/sdks/files/README.md#create) - Create File
* [uploaded](docs/sdks/files/README.md#uploaded) - Complete File Upload
* [delete](docs/sdks/files/README.md#delete) - Delete File
* [update](docs/sdks/files/README.md#update) - Update File

### [LicenseKeys](docs/sdks/licensekeys/README.md)

* [list](docs/sdks/licensekeys/README.md#list) - List License Keys
* [get](docs/sdks/licensekeys/README.md#get) - Get License Key
* [update](docs/sdks/licensekeys/README.md#update) - Update License Key
* [get_activation](docs/sdks/licensekeys/README.md#get_activation) - Get Activation
* [validate](docs/sdks/licensekeys/README.md#validate) - Validate License Key
* [activate](docs/sdks/licensekeys/README.md#activate) - Activate License Key
* [deactivate](docs/sdks/licensekeys/README.md#deactivate) - Deactivate License Key

### [MemberSessions](docs/sdks/membersessions/README.md)

* [create](docs/sdks/membersessions/README.md#create) - Create Member Session

### [Members](docs/sdks/members/README.md)

* [list_members](docs/sdks/members/README.md#list_members) - List Members
* [create_member](docs/sdks/members/README.md#create_member) - Create Member
* [get_member](docs/sdks/members/README.md#get_member) - Get Member
* [delete_member](docs/sdks/members/README.md#delete_member) - Delete Member
* [update_member](docs/sdks/members/README.md#update_member) - Update Member

### [Meters](docs/sdks/meters/README.md)

* [list](docs/sdks/meters/README.md#list) - List Meters
* [create](docs/sdks/meters/README.md#create) - Create Meter
* [get](docs/sdks/meters/README.md#get) - Get Meter
* [update](docs/sdks/meters/README.md#update) - Update Meter
* [quantities](docs/sdks/meters/README.md#quantities) - Get Meter Quantities

### [Metrics](docs/sdks/metrics/README.md)

* [get](docs/sdks/metrics/README.md#get) - Get Metrics
* [limits](docs/sdks/metrics/README.md#limits) - Get Metrics Limits

### [Oauth2](docs/sdks/oauth2/README.md)

* [authorize](docs/sdks/oauth2/README.md#authorize) - Authorize
* [token](docs/sdks/oauth2/README.md#token) - Request Token
* [revoke](docs/sdks/oauth2/README.md#revoke) - Revoke Token
* [introspect](docs/sdks/oauth2/README.md#introspect) - Introspect Token
* [userinfo](docs/sdks/oauth2/README.md#userinfo) - Get User Info

#### [Oauth2.Clients](docs/sdks/clients/README.md)

* [create](docs/sdks/clients/README.md#create) - Create Client
* [get](docs/sdks/clients/README.md#get) - Get Client
* [update](docs/sdks/clients/README.md#update) - Update Client
* [delete](docs/sdks/clients/README.md#delete) - Delete Client

### [Orders](docs/sdks/orders/README.md)

* [list](docs/sdks/orders/README.md#list) - List Orders
* [export](docs/sdks/orders/README.md#export) - Export Subscriptions
* [get](docs/sdks/orders/README.md#get) - Get Order
* [update](docs/sdks/orders/README.md#update) - Update Order
* [invoice](docs/sdks/orders/README.md#invoice) - Get Order Invoice

### [OrganizationAccessTokens](docs/sdks/organizationaccesstokens/README.md)

* [list](docs/sdks/organizationaccesstokens/README.md#list) - List
* [create](docs/sdks/organizationaccesstokens/README.md#create) - Create
* [delete](docs/sdks/organizationaccesstokens/README.md#delete) - Delete
* [update](docs/sdks/organizationaccesstokens/README.md#update) - Update

### [Organizations](docs/sdks/organizations/README.md)

* [list](docs/sdks/organizations/README.md#list) - List Organizations
* [create](docs/sdks/organizations/README.md#create) - Create Organization
* [get](docs/sdks/organizations/README.md#get) - Get Organization
* [update](docs/sdks/organizations/README.md#update) - Update Organization

### [Payments](docs/sdks/payments/README.md)

* [list](docs/sdks/payments/README.md#list) - List Payments
* [get](docs/sdks/payments/README.md#get) - Get Payment

### [Products](docs/sdks/products/README.md)

* [list](docs/sdks/products/README.md#list) - List Products
* [create](docs/sdks/products/README.md#create) - Create Product
* [get](docs/sdks/products/README.md#get) - Get Product
* [update](docs/sdks/products/README.md#update) - Update Product
* [update_benefits](docs/sdks/products/README.md#update_benefits) - Update Product Benefits

### [Refunds](docs/sdks/refunds/README.md)

* [list](docs/sdks/refunds/README.md#list) - List Refunds
* [create](docs/sdks/refunds/README.md#create) - Create Refund

### [Subscriptions](docs/sdks/subscriptions/README.md)

* [list](docs/sdks/subscriptions/README.md#list) - List Subscriptions
* [create](docs/sdks/subscriptions/README.md#create) - Create Subscription
* [export](docs/sdks/subscriptions/README.md#export) - Export Subscriptions
* [get](docs/sdks/subscriptions/README.md#get) - Get Subscription
* [revoke](docs/sdks/subscriptions/README.md#revoke) - Revoke Subscription
* [update](docs/sdks/subscriptions/README.md#update) - Update Subscription

### [Webhooks](docs/sdks/webhooks/README.md)

* [list_webhook_endpoints](docs/sdks/webhooks/README.md#list_webhook_endpoints) - List Webhook Endpoints
* [create_webhook_endpoint](docs/sdks/webhooks/README.md#create_webhook_endpoint) - Create Webhook Endpoint
* [get_webhook_endpoint](docs/sdks/webhooks/README.md#get_webhook_endpoint) - Get Webhook Endpoint
* [delete_webhook_endpoint](docs/sdks/webhooks/README.md#delete_webhook_endpoint) - Delete Webhook Endpoint
* [update_webhook_endpoint](docs/sdks/webhooks/README.md#update_webhook_endpoint) - Update Webhook Endpoint
* [reset_webhook_endpoint_secret](docs/sdks/webhooks/README.md#reset_webhook_endpoint_secret) - Reset Webhook Endpoint Secret
* [list_webhook_deliveries](docs/sdks/webhooks/README.md#list_webhook_deliveries) - List Webhook Deliveries
* [redeliver_webhook_event](docs/sdks/webhooks/README.md#redeliver_webhook_event) - Redeliver Webhook Event

</details>
<!-- End Available Resources and Operations [operations] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations. All operations return a response object or raise an error.

By default an API error will raise a `Errors::APIError`, which has the following properties:

| Property       | Type                                    | Description           |
|----------------|-----------------------------------------|-----------------------|
| `message`     | *string*                                 | The error message     |
| `status_code`  | *int*                                   | The HTTP status code  |
| `raw_response` | *Faraday::Response*                     | The raw HTTP response |
| `body`        | *string*                                 | The response content  |

When custom error responses are specified for an operation, the SDK may also throw their associated exception. You can refer to respective *Errors* tables in SDK docs for more details on possible exception types for each operation. For example, the `list` method throws the following exceptions:

| Error Type                          | Status Code | Content Type     |
| ----------------------------------- | ----------- | ---------------- |
| Models::Errors::HTTPValidationError | 422         | application/json |
| Errors::APIError                    | 4XX, 5XX    | \*/\*            |

### Example

```ruby
require "spaire"

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  access_token: "<YOUR_BEARER_TOKEN_HERE>"
)

begin
  res = s.organizations.list(page: 1, limit: 10)

  unless res.list_resource_organization.nil?
    # handle response
  end

rescue Models::Errors::HTTPValidationError => e
  # handle e.container data
  raise e
rescue Errors::APIError => e
  # handle default exception
  raise e
end

```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Name

You can override the default server globally by passing a server name to the `server (Symbol)` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the names associated with the available servers:

| Name         | Server                     | Description            |
| ------------ | -------------------------- | ---------------------- |
| `production` | `https://api.spairehq.com` | Production environment |

#### Example

```ruby
require "spaire"

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  server: "production",
  access_token: "<YOUR_BEARER_TOKEN_HERE>"
)
res = s.organizations.list(page: 1, limit: 10)

unless res.list_resource_organization.nil?
  # handle response
end

```

### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `server_url (String)` optional parameter when initializing the SDK client instance. For example:
```ruby
require "spaire"

Models = ::OpenApiSDK::Models
s = ::OpenApiSDK::Spaire.new(
  server_url: "https://api.spairehq.com",
  access_token: "<YOUR_BEARER_TOKEN_HERE>"
)
res = s.organizations.list(page: 1, limit: 10)

unless res.list_resource_organization.nil?
  # handle response
end

```
<!-- End Server Selection [server] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### SDK Created by [Speakeasy](https://www.speakeasy.com/?utm_source=spaire&utm_campaign=ruby)
