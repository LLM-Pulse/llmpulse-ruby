# LLMPulse::TeamMember

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **email** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **role** | **String** | The account owner is listed first; everyone else who joined is a member. |  |
| **status** | **String** | A blocked member cannot sign in or use the API until unblocked in the app. |  |
| **permission_role** | **String** | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. |  |
| **account_role** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
| **permissions** | **Hash&lt;String, Array&lt;String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
| **account_admin** | **Boolean** | A co-owner, who can manage the team. |  |
| **billing_access** | **Boolean** | Can open Billing and Plans (always true for the owner). |  |
| **all_projects** | **Boolean** | Has access to every project of the account, including future ones. |  |
| **project_ids** | **Array&lt;Integer&gt;** | The projects a member is limited to; empty when all_projects is true. |  |
| **last_sign_in_at** | **Time** |  | [optional] |
| **joined_at** | **Time** | When the member accepted the invitation; null for the owner and for members added without one. | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TeamMember.new(
  id: null,
  email: null,
  name: null,
  role: null,
  status: null,
  permission_role: null,
  account_role: null,
  permissions: null,
  account_admin: null,
  billing_access: null,
  all_projects: null,
  project_ids: null,
  last_sign_in_at: null,
  joined_at: null,
  created_at: null
)
```

