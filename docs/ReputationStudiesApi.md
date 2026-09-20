# LLMPulse::ReputationStudiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_reputation_report**](ReputationStudiesApi.md#get_reputation_report) | **GET** /reputation/reports/{id} | Get reputation report scores |
| [**get_study**](ReputationStudiesApi.md#get_study) | **GET** /studies/{id} | Get a custom AI study |
| [**get_study_report**](ReputationStudiesApi.md#get_study_report) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores |
| [**list_reputation_reports**](ReputationStudiesApi.md#list_reputation_reports) | **GET** /reputation/reports | List reputation reports |
| [**list_studies**](ReputationStudiesApi.md#list_studies) | **GET** /studies | List custom AI studies |


## get_reputation_report

> get_reputation_report(id, project_id, opts)

Get reputation report scores

One reputation report's scores as flat rows: one row per analyst model, brand, dimension and attribute, with its 0-100 score and the reasoning the model gave. Scores come from several analyst models independently, so compare models rather than averaging them blindly.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReputationStudiesApi.new
id = 'id_example' # String | The report id from GET /reputation/reports
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Restrict to one analyst model
  brand: 'brand_example', # String | Restrict to one brand name, or a comma-separated list
  dimension: 'dimension_example', # String | Restrict to one reputation dimension key
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Get reputation report scores
  api_instance.get_reputation_report(id, project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_reputation_report: #{e}"
end
```

#### Using the get_reputation_report_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_reputation_report_with_http_info(id, project_id, opts)

```ruby
begin
  # Get reputation report scores
  data, status_code, headers = api_instance.get_reputation_report_with_http_info(id, project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_reputation_report_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The report id from GET /reputation/reports |  |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Restrict to one analyst model | [optional] |
| **brand** | **String** | Restrict to one brand name, or a comma-separated list | [optional] |
| **dimension** | **String** | Restrict to one reputation dimension key | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_study

> get_study(id)

Get a custom AI study

One study with its brief, the subjects it compares, the dimensions it scores them on, and its report history. Use the ids in `reports` with GET /studies/{id}/reports/{report_id}.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReputationStudiesApi.new
id = 56 # Integer | 

begin
  # Get a custom AI study
  api_instance.get_study(id)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_study: #{e}"
end
```

#### Using the get_study_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_study_with_http_info(id)

```ruby
begin
  # Get a custom AI study
  data, status_code, headers = api_instance.get_study_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_study_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_study_report

> get_study_report(id, report_id, opts)

Get custom study report scores

One custom-study report's scores as flat rows: one row per analyst model, subject, dimension and attribute, with its 0-100 score and the reasoning the model gave.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReputationStudiesApi.new
id = 56 # Integer | 
report_id = 'report_id_example' # String | The report id from GET /studies/{id}
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Restrict to one analyst model
  subject: 'subject_example', # String | Restrict to one subject name, or a comma-separated list
  dimension: 'dimension_example', # String | Restrict to one dimension key
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Get custom study report scores
  api_instance.get_study_report(id, report_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_study_report: #{e}"
end
```

#### Using the get_study_report_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_study_report_with_http_info(id, report_id, opts)

```ruby
begin
  # Get custom study report scores
  data, status_code, headers = api_instance.get_study_report_with_http_info(id, report_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->get_study_report_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **report_id** | **String** | The report id from GET /studies/{id} |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Restrict to one analyst model | [optional] |
| **subject** | **String** | Restrict to one subject name, or a comma-separated list | [optional] |
| **dimension** | **String** | Restrict to one dimension key | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_reputation_reports

> list_reputation_reports(project_id, opts)

List reputation reports

The monthly multi-model analyst reports scoring the tracked brand and its competitors, newest first. Pending and failed reports are included on purpose: whether this month ran at all is often the question. Each row carries the report id, its status, and which analyst models produced data. Requires reputation monitoring to be enabled on the account.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReputationStudiesApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List reputation reports
  api_instance.list_reputation_reports(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->list_reputation_reports: #{e}"
end
```

#### Using the list_reputation_reports_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_reputation_reports_with_http_info(project_id, opts)

```ruby
begin
  # List reputation reports
  data, status_code, headers = api_instance.list_reputation_reports_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->list_reputation_reports_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_studies

> list_studies(opts)

List custom AI studies

The custom AI studies defined on the account: analyst reports over any set of subjects (brands, sectors, topics) and any set of dimensions. Studies belong to the ACCOUNT, not to a project, so project_id is an optional filter here and account-level studies are returned whichever project you filter by. A team member whose project access is restricted sees only the studies of the projects they can reach. Requires reputation monitoring to be enabled on the account.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReputationStudiesApi.new
opts = {
  project_id: 56, # Integer | Restrict to studies attached to this project (plus account-level ones)
  status: 'active', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List custom AI studies
  api_instance.list_studies(opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->list_studies: #{e}"
end
```

#### Using the list_studies_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_studies_with_http_info(opts)

```ruby
begin
  # List custom AI studies
  data, status_code, headers = api_instance.list_studies_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ReputationStudiesApi->list_studies_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Restrict to studies attached to this project (plus account-level ones) | [optional] |
| **status** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

