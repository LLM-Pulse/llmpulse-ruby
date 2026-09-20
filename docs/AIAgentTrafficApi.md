# LLMPulse::AIAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_agent_traffic**](AIAgentTrafficApi.md#get_agent_traffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**get_ai_traffic**](AIAgentTrafficApi.md#get_ai_traffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**list_agent_bots**](AIAgentTrafficApi.md#list_agent_bots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |


## get_agent_traffic

> <AgentTrafficResponse> get_agent_traffic(project_id, opts)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project's origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AIAgentTrafficApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  bot: 'bot_example', # String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
  company: 'company_example', # String | Filter by company (e.g. openai, anthropic, google)
  group_by: 'bot', # String | 
  granularity: 'day' # String | 
}

begin
  # AI bot crawler traffic (Scale plan or above, Beta)
  result = api_instance.get_agent_traffic(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->get_agent_traffic: #{e}"
end
```

#### Using the get_agent_traffic_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentTrafficResponse>, Integer, Hash)> get_agent_traffic_with_http_info(project_id, opts)

```ruby
begin
  # AI bot crawler traffic (Scale plan or above, Beta)
  data, status_code, headers = api_instance.get_agent_traffic_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentTrafficResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->get_agent_traffic_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **bot** | **String** | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional] |
| **company** | **String** | Filter by company (e.g. openai, anthropic, google) | [optional] |
| **group_by** | **String** |  | [optional][default to &#39;bot&#39;] |
| **granularity** | **String** |  | [optional] |

### Return type

[**AgentTrafficResponse**](AgentTrafficResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_ai_traffic

> get_ai_traffic(project_id, opts)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AIAgentTrafficApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  source: 'source_example', # String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
  granularity: 'day' # String | 
}

begin
  # AI referral traffic (Scale plan or above)
  api_instance.get_ai_traffic(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->get_ai_traffic: #{e}"
end
```

#### Using the get_ai_traffic_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_ai_traffic_with_http_info(project_id, opts)

```ruby
begin
  # AI referral traffic (Scale plan or above)
  data, status_code, headers = api_instance.get_ai_traffic_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->get_ai_traffic_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source** | **String** | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| **granularity** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_agent_bots

> <AgentBotsResponse> list_agent_bots(project_id, opts)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AIAgentTrafficApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # AI bot catalog (Scale plan or above)
  result = api_instance.list_agent_bots(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->list_agent_bots: #{e}"
end
```

#### Using the list_agent_bots_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentBotsResponse>, Integer, Hash)> list_agent_bots_with_http_info(project_id, opts)

```ruby
begin
  # AI bot catalog (Scale plan or above)
  data, status_code, headers = api_instance.list_agent_bots_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentBotsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling AIAgentTrafficApi->list_agent_bots_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**AgentBotsResponse**](AgentBotsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

