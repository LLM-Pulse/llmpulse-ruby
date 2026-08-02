# LLMPulse::ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_project**](ProjectsApi.md#create_project) | **POST** /projects | Create a project (fast mode) |
| [**create_project_draft**](ProjectsApi.md#create_project_draft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalize_project_draft**](ProjectsApi.md#finalize_project_draft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**get_project_draft**](ProjectsApi.md#get_project_draft) | **GET** /project_drafts/{id} | Read a project draft |
| [**update_project_draft**](ProjectsApi.md#update_project_draft) | **PATCH** /project_drafts/{id} | Submit a wizard step |


## create_project

> <ProjectCreateResponse> create_project(project_create_request)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ProjectsApi.new
project_create_request = LLMPulse::ProjectCreateRequest.new({website_url: 'https://acme.com', name: 'Acme', main_country: 'US', main_language: 'en'}) # ProjectCreateRequest | 

begin
  # Create a project (fast mode)
  result = api_instance.create_project(project_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->create_project: #{e}"
end
```

#### Using the create_project_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectCreateResponse>, Integer, Hash)> create_project_with_http_info(project_create_request)

```ruby
begin
  # Create a project (fast mode)
  data, status_code, headers = api_instance.create_project_with_http_info(project_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectCreateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->create_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_create_request** | [**ProjectCreateRequest**](ProjectCreateRequest.md) |  |  |

### Return type

[**ProjectCreateResponse**](ProjectCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_project_draft

> create_project_draft(create_project_draft_request)

Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest=false to skip AI and respond instantly. Drafts expire after 24h. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ProjectsApi.new
create_project_draft_request = LLMPulse::CreateProjectDraftRequest.new({website_url: 'website_url_example', main_country: 'main_country_example', main_language: 'main_language_example'}) # CreateProjectDraftRequest | 

begin
  # Start a project draft (wizard step 1)
  api_instance.create_project_draft(create_project_draft_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->create_project_draft: #{e}"
end
```

#### Using the create_project_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_project_draft_with_http_info(create_project_draft_request)

```ruby
begin
  # Start a project draft (wizard step 1)
  data, status_code, headers = api_instance.create_project_draft_with_http_info(create_project_draft_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->create_project_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_project_draft_request** | [**CreateProjectDraftRequest**](CreateProjectDraftRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## finalize_project_draft

> finalize_project_draft(id, opts)

Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ProjectsApi.new
id = 'id_example' # String | 
opts = {
  finalize_project_draft_request: LLMPulse::FinalizeProjectDraftRequest.new # FinalizeProjectDraftRequest | 
}

begin
  # Finalize a draft into a real project
  api_instance.finalize_project_draft(id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->finalize_project_draft: #{e}"
end
```

#### Using the finalize_project_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> finalize_project_draft_with_http_info(id, opts)

```ruby
begin
  # Finalize a draft into a real project
  data, status_code, headers = api_instance.finalize_project_draft_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->finalize_project_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **finalize_project_draft_request** | [**FinalizeProjectDraftRequest**](FinalizeProjectDraftRequest.md) |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_project_draft

> get_project_draft(id, opts)

Read a project draft

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ProjectsApi.new
id = 'id_example' # String | Draft id (draft_...)
opts = {
  include_suggestions: true # Boolean | Cache-only: returns suggestions for the current step if already generated, never triggers AI
}

begin
  # Read a project draft
  api_instance.get_project_draft(id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->get_project_draft: #{e}"
end
```

#### Using the get_project_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_project_draft_with_http_info(id, opts)

```ruby
begin
  # Read a project draft
  data, status_code, headers = api_instance.get_project_draft_with_http_info(id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->get_project_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Draft id (draft_...) |  |
| **include_suggestions** | **Boolean** | Cache-only: returns suggestions for the current step if already generated, never triggers AI | [optional][default to false] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_project_draft

> update_project_draft(id, update_project_draft_request)

Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (`ERR_DRAFT_STATE` otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ProjectsApi.new
id = 'id_example' # String | 
update_project_draft_request = LLMPulse::UpdateProjectDraftRequest.new({step: 'details'}) # UpdateProjectDraftRequest | 

begin
  # Submit a wizard step
  api_instance.update_project_draft(id, update_project_draft_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->update_project_draft: #{e}"
end
```

#### Using the update_project_draft_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_project_draft_with_http_info(id, update_project_draft_request)

```ruby
begin
  # Submit a wizard step
  data, status_code, headers = api_instance.update_project_draft_with_http_info(id, update_project_draft_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->update_project_draft_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **update_project_draft_request** | [**UpdateProjectDraftRequest**](UpdateProjectDraftRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

