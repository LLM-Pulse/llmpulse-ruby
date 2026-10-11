# LLMPulse::CreateTeamInvitationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email** | **String** |  |  |
| **project_ids** | **Array&lt;Integer&gt;** | Projects the member can access. Send this or all_projects true. | [optional] |
| **all_projects** | **Boolean** | Access to every project, including future ones | [optional] |
| **permission_role** | **String** | Default full_access. Owner and co-owners only. | [optional] |
| **account_role_id** | **Integer** | One of the account&#39;s roles, with permission_role account_role | [optional] |
| **permissions** | **Hash&lt;String, Array&lt;String&gt;&gt;** | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\&quot;overview\&quot;: [\&quot;read\&quot;], \&quot;prompts\&quot;: [\&quot;read\&quot;, \&quot;create\&quot;]} | [optional] |
| **account_admin** | **Boolean** | Make the member a co-owner. Account owner only. | [optional] |
| **billing_access** | **Boolean** | Access to Billing and Plans. Account owner only. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateTeamInvitationRequest.new(
  email: null,
  project_ids: null,
  all_projects: null,
  permission_role: null,
  account_role_id: null,
  permissions: null,
  account_admin: null,
  billing_access: null
)
```

