# LLMPulse::TeamApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_team_invitation**](TeamApi.md#create_team_invitation) | **POST** /team_invitations | Invite a team member |
| [**list_team_invitations**](TeamApi.md#list_team_invitations) | **GET** /team_invitations | List pending team invitations |
| [**list_team_members**](TeamApi.md#list_team_members) | **GET** /team_members | List team members |
| [**remove_team_member**](TeamApi.md#remove_team_member) | **DELETE** /team_members/{id} | Remove a team member |
| [**revoke_team_invitation**](TeamApi.md#revoke_team_invitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation |


## create_team_invitation

> <CreateTeamInvitation201Response> create_team_invitation(create_team_invitation_request)

Invite a team member

Invites someone to the account team with the same rules as the Team Members settings page, and sends them the invitation email (email_sent is false when the email provider refused it; the invitation still exists, so revoke it and invite again once the address is fixed). Send project_ids, or all_projects: true for every project (for a team member inviting, every project they can access). The account owner and co-owners choose the access with permission_role: full_access (default), view_only, custom (with permissions, feature key to verbs) or account_role (with account_role_id). A team member with permission to invite cannot choose access: leave those fields out and the invitation copies their own permissions. Only the account owner can set account_admin (co-owner) or billing_access. An address already registered on the platform, or with an invitation pending, is refused with ERR_INVALID_PARAM (revoke the pending one first). An account that cannot add more team members, or that reached its daily limit of invitations sent through the API and MCP (revoked ones count), answers ERR_LIMIT_REACHED; the message says which. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TeamApi.new
create_team_invitation_request = LLMPulse::CreateTeamInvitationRequest.new({email: 'email_example'}) # CreateTeamInvitationRequest | 

begin
  # Invite a team member
  result = api_instance.create_team_invitation(create_team_invitation_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->create_team_invitation: #{e}"
end
```

#### Using the create_team_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateTeamInvitation201Response>, Integer, Hash)> create_team_invitation_with_http_info(create_team_invitation_request)

```ruby
begin
  # Invite a team member
  data, status_code, headers = api_instance.create_team_invitation_with_http_info(create_team_invitation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateTeamInvitation201Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->create_team_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_team_invitation_request** | [**CreateTeamInvitationRequest**](CreateTeamInvitationRequest.md) |  |  |

### Return type

[**CreateTeamInvitation201Response**](CreateTeamInvitation201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_team_invitations

> <ListTeamInvitations200Response> list_team_invitations(opts)

List pending team invitations

Lists invitations that have not been accepted yet: the address, the access and projects the person will get, when the invitation was sent and when its link expires. An accepted invitation keeps its id and moves to GET /team_members. Same access rules as GET /team_members.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TeamApi.new
opts = {
  page: 56, # Integer | 
  per_page: 56 # Integer | Default 20, max 100
}

begin
  # List pending team invitations
  result = api_instance.list_team_invitations(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->list_team_invitations: #{e}"
end
```

#### Using the list_team_invitations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListTeamInvitations200Response>, Integer, Hash)> list_team_invitations_with_http_info(opts)

```ruby
begin
  # List pending team invitations
  data, status_code, headers = api_instance.list_team_invitations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListTeamInvitations200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->list_team_invitations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** | Default 20, max 100 | [optional] |

### Return type

[**ListTeamInvitations200Response**](ListTeamInvitations200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_team_members

> <ListTeamMembers200Response> list_team_members(opts)

List team members

Lists the account owner first, then every team member who joined, with their access level (permission_role, account role and the resulting permissions), co-owner and billing flags, project access, status (active or blocked) and last sign-in. Pending invitations are listed by GET /team_invitations; GET /account limits.team_members.used counts both. Available to the account owner, co-owners and team members with the Team Members permission. A key limited to some projects answers ERR_KEY_PROJECT_SCOPED: the team belongs to the whole account.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TeamApi.new
opts = {
  page: 56, # Integer | 
  per_page: 56 # Integer | Default 20, max 100
}

begin
  # List team members
  result = api_instance.list_team_members(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->list_team_members: #{e}"
end
```

#### Using the list_team_members_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListTeamMembers200Response>, Integer, Hash)> list_team_members_with_http_info(opts)

```ruby
begin
  # List team members
  data, status_code, headers = api_instance.list_team_members_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListTeamMembers200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->list_team_members_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** | Default 20, max 100 | [optional] |

### Return type

[**ListTeamMembers200Response**](ListTeamMembers200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_team_member

> <RemoveTeamMember200Response> remove_team_member(id)

Remove a team member

Removes a member from the team, as the settings page does: their sessions and API keys stop working at once and their user account is deleted in the background shortly after. Account owner or co-owner only; a co-owner cannot remove the owner, another co-owner or themselves. The owner cannot be removed. Pending invitations are revoked with DELETE /team_invitations/{id}; an id that is not a member of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TeamApi.new
id = 56 # Integer | The member id from GET /team_members

begin
  # Remove a team member
  result = api_instance.remove_team_member(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->remove_team_member: #{e}"
end
```

#### Using the remove_team_member_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveTeamMember200Response>, Integer, Hash)> remove_team_member_with_http_info(id)

```ruby
begin
  # Remove a team member
  data, status_code, headers = api_instance.remove_team_member_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveTeamMember200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->remove_team_member_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The member id from GET /team_members |  |

### Return type

[**RemoveTeamMember200Response**](RemoveTeamMember200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## revoke_team_invitation

> <RevokeTeamInvitation200Response> revoke_team_invitation(id)

Revoke a pending team invitation

Revokes a pending invitation: its link stops working immediately. Account owner or co-owner only, and a co-owner cannot revoke an invitation that makes someone a co-owner. Members who already joined are removed with DELETE /team_members/{id}; an id that is not a pending invitation of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TeamApi.new
id = 56 # Integer | The invitation id from GET /team_invitations

begin
  # Revoke a pending team invitation
  result = api_instance.revoke_team_invitation(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->revoke_team_invitation: #{e}"
end
```

#### Using the revoke_team_invitation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RevokeTeamInvitation200Response>, Integer, Hash)> revoke_team_invitation_with_http_info(id)

```ruby
begin
  # Revoke a pending team invitation
  data, status_code, headers = api_instance.revoke_team_invitation_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RevokeTeamInvitation200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling TeamApi->revoke_team_invitation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The invitation id from GET /team_invitations |  |

### Return type

[**RevokeTeamInvitation200Response**](RevokeTeamInvitation200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

