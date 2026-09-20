# LLMPulse::ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_project**](ProjectsApi.md#create_project) | **POST** /projects | Create a project (fast mode) |
| [**create_project_draft**](ProjectsApi.md#create_project_draft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalize_project_draft**](ProjectsApi.md#finalize_project_draft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**get_project_details**](ProjectsApi.md#get_project_details) | **GET** /dimensions/projects/{id} | Project details |
| [**get_project_draft**](ProjectsApi.md#get_project_draft) | **GET** /project_drafts/{id} | Read a project draft |
| [**list_locales**](ProjectsApi.md#list_locales) | **GET** /dimensions/locales | List locales with data |
| [**list_models**](ProjectsApi.md#list_models) | **GET** /dimensions/models | List models with data |
| [**list_projects**](ProjectsApi.md#list_projects) | **GET** /dimensions/projects | List projects |
| [**update_project**](ProjectsApi.md#update_project) | **PATCH** /projects/{id} | Update a project profile (Brand Book) |
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


## get_project_details

> <ProjectDetails> get_project_details(id)

Project details

Detailed info for one project: matching_names, industry, business model, primary products, target audience, brand voice, locale, app store IDs, stats (incl. prompts_by_brand_kind counts) and data_coverage (models, countries and languages with data).

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
id = 56 # Integer | 

begin
  # Project details
  result = api_instance.get_project_details(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->get_project_details: #{e}"
end
```

#### Using the get_project_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectDetails>, Integer, Hash)> get_project_details_with_http_info(id)

```ruby
begin
  # Project details
  data, status_code, headers = api_instance.get_project_details_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectDetails>
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->get_project_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |

### Return type

[**ProjectDetails**](ProjectDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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


## list_locales

> list_locales(project_id)

List locales with data

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
project_id = 56 # Integer | Project ID

begin
  # List locales with data
  api_instance.list_locales(project_id)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_locales: #{e}"
end
```

#### Using the list_locales_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_locales_with_http_info(project_id)

```ruby
begin
  # List locales with data
  data, status_code, headers = api_instance.list_locales_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_locales_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_models

> list_models(project_id)

List models with data

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
project_id = 56 # Integer | Project ID

begin
  # List models with data
  api_instance.list_models(project_id)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_models: #{e}"
end
```

#### Using the list_models_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_models_with_http_info(project_id)

```ruby
begin
  # List models with data
  data, status_code, headers = api_instance.list_models_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_models_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_projects

> <ListProjects200Response> list_projects(opts)

List projects

All projects accessible with your API key.

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
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List projects
  result = api_instance.list_projects(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_projects: #{e}"
end
```

#### Using the list_projects_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListProjects200Response>, Integer, Hash)> list_projects_with_http_info(opts)

```ruby
begin
  # List projects
  data, status_code, headers = api_instance.list_projects_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListProjects200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->list_projects_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_project

> update_project(id, update_project_request)

Update a project profile (Brand Book)

Updates the project profile, the same fields as Project Settings: brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names. Send only the fields to change; unknown fields are rejected. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background (rematching=true); further edits are rejected while that runs. Requires a `read_write` scope API key.

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
id = 56 # Integer | 
update_project_request = LLMPulse::UpdateProjectRequest.new # UpdateProjectRequest | 

begin
  # Update a project profile (Brand Book)
  api_instance.update_project(id, update_project_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->update_project: #{e}"
end
```

#### Using the update_project_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_project_with_http_info(id, update_project_request)

```ruby
begin
  # Update a project profile (Brand Book)
  data, status_code, headers = api_instance.update_project_with_http_info(id, update_project_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ProjectsApi->update_project_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **update_project_request** | [**UpdateProjectRequest**](UpdateProjectRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
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

