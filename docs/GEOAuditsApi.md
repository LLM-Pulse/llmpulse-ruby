# LLMPulse::GEOAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**compare_geo_audit_runs**](GEOAuditsApi.md#compare_geo_audit_runs) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**create_geo_audits**](GEOAuditsApi.md#create_geo_audits) | **POST** /geo_audits | Create GEO audits |
| [**delete_geo_audit**](GEOAuditsApi.md#delete_geo_audit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**get_geo_audit**](GEOAuditsApi.md#get_geo_audit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**get_geo_audit_run**](GEOAuditsApi.md#get_geo_audit_run) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**list_geo_alerts**](GEOAuditsApi.md#list_geo_alerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**list_geo_audit_findings**](GEOAuditsApi.md#list_geo_audit_findings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**list_geo_audit_issues**](GEOAuditsApi.md#list_geo_audit_issues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**list_geo_audit_runs**](GEOAuditsApi.md#list_geo_audit_runs) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**list_geo_audits**](GEOAuditsApi.md#list_geo_audits) | **GET** /geo_audits | List GEO audits |
| [**run_geo_audit**](GEOAuditsApi.md#run_geo_audit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**update_geo_audit**](GEOAuditsApi.md#update_geo_audit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**update_geo_audit_issue**](GEOAuditsApi.md#update_geo_audit_issue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |


## compare_geo_audit_runs

> <GeoAuditComparison> compare_geo_audit_runs(project_id, id, opts)

Compare two GEO audit runs

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
id = 'id_example' # String | Audit id
opts = {
  from_run: 56, # Integer | Run number to compare from (default the run before to_run)
  to_run: 56 # Integer | Run number to compare to (default the latest completed run)
}

begin
  # Compare two GEO audit runs
  result = api_instance.compare_geo_audit_runs(project_id, id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->compare_geo_audit_runs: #{e}"
end
```

#### Using the compare_geo_audit_runs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditComparison>, Integer, Hash)> compare_geo_audit_runs_with_http_info(project_id, id, opts)

```ruby
begin
  # Compare two GEO audit runs
  data, status_code, headers = api_instance.compare_geo_audit_runs_with_http_info(project_id, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditComparison>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->compare_geo_audit_runs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** | Audit id |  |
| **from_run** | **Integer** | Run number to compare from (default the run before to_run) | [optional] |
| **to_run** | **Integer** | Run number to compare to (default the latest completed run) | [optional] |

### Return type

[**GeoAuditComparison**](GeoAuditComparison.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_geo_audits

> <GeoAuditCreateResponse> create_geo_audits(geo_audit_create_request)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
geo_audit_create_request = LLMPulse::GeoAuditCreateRequest.new({project_id: 37, target: 'target_example', audit_types: ['agent_readiness']}) # GeoAuditCreateRequest | 

begin
  # Create GEO audits
  result = api_instance.create_geo_audits(geo_audit_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->create_geo_audits: #{e}"
end
```

#### Using the create_geo_audits_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditCreateResponse>, Integer, Hash)> create_geo_audits_with_http_info(geo_audit_create_request)

```ruby
begin
  # Create GEO audits
  data, status_code, headers = api_instance.create_geo_audits_with_http_info(geo_audit_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditCreateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->create_geo_audits_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **geo_audit_create_request** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md) |  |  |

### Return type

[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_geo_audit

> <GeoAuditArchived> delete_geo_audit(project_id, id)

Delete (archive) a GEO audit

Archives the audit. Requires a `read_write` scope API key and, for team members, delete permission on GEO Optimization.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
id = 'id_example' # String | Audit id

begin
  # Delete (archive) a GEO audit
  result = api_instance.delete_geo_audit(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->delete_geo_audit: #{e}"
end
```

#### Using the delete_geo_audit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditArchived>, Integer, Hash)> delete_geo_audit_with_http_info(project_id, id)

```ruby
begin
  # Delete (archive) a GEO audit
  data, status_code, headers = api_instance.delete_geo_audit_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditArchived>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->delete_geo_audit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** | Audit id |  |

### Return type

[**GeoAuditArchived**](GeoAuditArchived.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_geo_audit

> <GeoAuditResponse> get_geo_audit(project_id, id)

Get a GEO audit

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
id = 'id_example' # String | Audit id

begin
  # Get a GEO audit
  result = api_instance.get_geo_audit(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->get_geo_audit: #{e}"
end
```

#### Using the get_geo_audit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditResponse>, Integer, Hash)> get_geo_audit_with_http_info(project_id, id)

```ruby
begin
  # Get a GEO audit
  data, status_code, headers = api_instance.get_geo_audit_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->get_geo_audit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** | Audit id |  |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_geo_audit_run

> <GeoAuditRunDetail> get_geo_audit_run(project_id, geo_audit_id, sequence)

Get a GEO audit run

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
geo_audit_id = 'geo_audit_id_example' # String | Audit id
sequence = 56 # Integer | Run number within the audit

begin
  # Get a GEO audit run
  result = api_instance.get_geo_audit_run(project_id, geo_audit_id, sequence)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->get_geo_audit_run: #{e}"
end
```

#### Using the get_geo_audit_run_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditRunDetail>, Integer, Hash)> get_geo_audit_run_with_http_info(project_id, geo_audit_id, sequence)

```ruby
begin
  # Get a GEO audit run
  data, status_code, headers = api_instance.get_geo_audit_run_with_http_info(project_id, geo_audit_id, sequence)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditRunDetail>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->get_geo_audit_run_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **geo_audit_id** | **String** | Audit id |  |
| **sequence** | **Integer** | Run number within the audit |  |

### Return type

[**GeoAuditRunDetail**](GeoAuditRunDetail.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_geo_alerts

> <GeoAlertList> list_geo_alerts(project_id, opts)

List GEO audit alerts

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
opts = {
  audit_id: 'audit_id_example', # String | Only alerts of this audit
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List GEO audit alerts
  result = api_instance.list_geo_alerts(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_alerts: #{e}"
end
```

#### Using the list_geo_alerts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAlertList>, Integer, Hash)> list_geo_alerts_with_http_info(project_id, opts)

```ruby
begin
  # List GEO audit alerts
  data, status_code, headers = api_instance.list_geo_alerts_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAlertList>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_alerts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **audit_id** | **String** | Only alerts of this audit | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

[**GeoAlertList**](GeoAlertList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_geo_audit_findings

> <GeoAuditFindingList> list_geo_audit_findings(project_id, geo_audit_id, sequence, opts)

List the findings of a GEO audit run

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
geo_audit_id = 'geo_audit_id_example' # String | Audit id
sequence = 56 # Integer | Run number within the audit
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List the findings of a GEO audit run
  result = api_instance.list_geo_audit_findings(project_id, geo_audit_id, sequence, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_findings: #{e}"
end
```

#### Using the list_geo_audit_findings_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditFindingList>, Integer, Hash)> list_geo_audit_findings_with_http_info(project_id, geo_audit_id, sequence, opts)

```ruby
begin
  # List the findings of a GEO audit run
  data, status_code, headers = api_instance.list_geo_audit_findings_with_http_info(project_id, geo_audit_id, sequence, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditFindingList>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_findings_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **geo_audit_id** | **String** | Audit id |  |
| **sequence** | **Integer** | Run number within the audit |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**GeoAuditFindingList**](GeoAuditFindingList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_geo_audit_issues

> <GeoAuditIssueList> list_geo_audit_issues(project_id, geo_audit_id, opts)

List the issues of a GEO audit

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
geo_audit_id = 'geo_audit_id_example' # String | Audit id
opts = {
  state: 'open', # String | open means open and not accepted; default all
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List the issues of a GEO audit
  result = api_instance.list_geo_audit_issues(project_id, geo_audit_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_issues: #{e}"
end
```

#### Using the list_geo_audit_issues_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditIssueList>, Integer, Hash)> list_geo_audit_issues_with_http_info(project_id, geo_audit_id, opts)

```ruby
begin
  # List the issues of a GEO audit
  data, status_code, headers = api_instance.list_geo_audit_issues_with_http_info(project_id, geo_audit_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditIssueList>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_issues_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **geo_audit_id** | **String** | Audit id |  |
| **state** | **String** | open means open and not accepted; default all | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

[**GeoAuditIssueList**](GeoAuditIssueList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_geo_audit_runs

> <GeoAuditRunList> list_geo_audit_runs(project_id, geo_audit_id, opts)

List the runs of a GEO audit

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
geo_audit_id = 'geo_audit_id_example' # String | Audit id
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List the runs of a GEO audit
  result = api_instance.list_geo_audit_runs(project_id, geo_audit_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_runs: #{e}"
end
```

#### Using the list_geo_audit_runs_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditRunList>, Integer, Hash)> list_geo_audit_runs_with_http_info(project_id, geo_audit_id, opts)

```ruby
begin
  # List the runs of a GEO audit
  data, status_code, headers = api_instance.list_geo_audit_runs_with_http_info(project_id, geo_audit_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditRunList>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audit_runs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **geo_audit_id** | **String** | Audit id |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**GeoAuditRunList**](GeoAuditRunList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_geo_audits

> <GeoAuditList> list_geo_audits(project_id, opts)

List GEO audits

Lists the project's audits, most recently updated first. Archived audits are left out unless status=archived.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
opts = {
  audit_type: 'agent_readiness', # String | 
  status: 'active', # String | 
  cadence: 'once', # String | 
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List GEO audits
  result = api_instance.list_geo_audits(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audits: #{e}"
end
```

#### Using the list_geo_audits_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditList>, Integer, Hash)> list_geo_audits_with_http_info(project_id, opts)

```ruby
begin
  # List GEO audits
  data, status_code, headers = api_instance.list_geo_audits_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditList>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->list_geo_audits_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **audit_type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **cadence** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

[**GeoAuditList**](GeoAuditList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## run_geo_audit

> <GeoAuditRunResponse> run_geo_audit(project_id, geo_audit_id)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
project_id = 56 # Integer | Project ID
geo_audit_id = 'geo_audit_id_example' # String | Audit id

begin
  # Run a GEO audit now
  result = api_instance.run_geo_audit(project_id, geo_audit_id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->run_geo_audit: #{e}"
end
```

#### Using the run_geo_audit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditRunResponse>, Integer, Hash)> run_geo_audit_with_http_info(project_id, geo_audit_id)

```ruby
begin
  # Run a GEO audit now
  data, status_code, headers = api_instance.run_geo_audit_with_http_info(project_id, geo_audit_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditRunResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->run_geo_audit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **geo_audit_id** | **String** | Audit id |  |

### Return type

[**GeoAuditRunResponse**](GeoAuditRunResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_geo_audit

> <GeoAuditResponse> update_geo_audit(id, geo_audit_update_request)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
id = 'id_example' # String | Audit id
geo_audit_update_request = LLMPulse::GeoAuditUpdateRequest.new # GeoAuditUpdateRequest | 

begin
  # Update a GEO audit
  result = api_instance.update_geo_audit(id, geo_audit_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->update_geo_audit: #{e}"
end
```

#### Using the update_geo_audit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditResponse>, Integer, Hash)> update_geo_audit_with_http_info(id, geo_audit_update_request)

```ruby
begin
  # Update a GEO audit
  data, status_code, headers = api_instance.update_geo_audit_with_http_info(id, geo_audit_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->update_geo_audit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Audit id |  |
| **geo_audit_update_request** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md) |  |  |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_geo_audit_issue

> <GeoAuditIssueResponse> update_geo_audit_issue(geo_audit_id, id, geo_audit_issue_update_request)

Accept or reopen a GEO audit issue

Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOAuditsApi.new
geo_audit_id = 'geo_audit_id_example' # String | Audit id
id = 56 # Integer | Issue id
geo_audit_issue_update_request = LLMPulse::GeoAuditIssueUpdateRequest.new({accepted: false}) # GeoAuditIssueUpdateRequest | 

begin
  # Accept or reopen a GEO audit issue
  result = api_instance.update_geo_audit_issue(geo_audit_id, id, geo_audit_issue_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->update_geo_audit_issue: #{e}"
end
```

#### Using the update_geo_audit_issue_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GeoAuditIssueResponse>, Integer, Hash)> update_geo_audit_issue_with_http_info(geo_audit_id, id, geo_audit_issue_update_request)

```ruby
begin
  # Accept or reopen a GEO audit issue
  data, status_code, headers = api_instance.update_geo_audit_issue_with_http_info(geo_audit_id, id, geo_audit_issue_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GeoAuditIssueResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOAuditsApi->update_geo_audit_issue_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **geo_audit_id** | **String** | Audit id |  |
| **id** | **Integer** | Issue id |  |
| **geo_audit_issue_update_request** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md) |  |  |

### Return type

[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

