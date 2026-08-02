# LLMPulse::MetricsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_agent_traffic**](MetricsApi.md#get_agent_traffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta) |
| [**get_ai_traffic**](MetricsApi.md#get_ai_traffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+) |
| [**get_prompt_summary**](MetricsApi.md#get_prompt_summary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**get_share_of_voice**](MetricsApi.md#get_share_of_voice) | **GET** /metrics/sov | Share of Voice |
| [**get_summary**](MetricsApi.md#get_summary) | **GET** /metrics/summary | Aggregated metrics summary |
| [**get_timeseries**](MetricsApi.md#get_timeseries) | **GET** /metrics/timeseries | Time-series metrics |
| [**get_top_sources**](MetricsApi.md#get_top_sources) | **GET** /metrics/top_sources | Top cited sources |


## get_agent_traffic

> <AgentTrafficResponse> get_agent_traffic(project_id, opts)

AI bot crawler traffic (Scale+, Beta)

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

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  bot: 'bot_example', # String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
  company: 'company_example', # String | Filter by company (e.g. openai, anthropic, google)
  group_by: 'bot', # String | 
  granularity: 'day' # String | 
}

begin
  # AI bot crawler traffic (Scale+, Beta)
  result = api_instance.get_agent_traffic(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_agent_traffic: #{e}"
end
```

#### Using the get_agent_traffic_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentTrafficResponse>, Integer, Hash)> get_agent_traffic_with_http_info(project_id, opts)

```ruby
begin
  # AI bot crawler traffic (Scale+, Beta)
  data, status_code, headers = api_instance.get_agent_traffic_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentTrafficResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_agent_traffic_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
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

AI referral traffic (Scale+)

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

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  source: 'source_example', # String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
  granularity: 'day' # String | 
}

begin
  # AI referral traffic (Scale+)
  api_instance.get_ai_traffic(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_ai_traffic: #{e}"
end
```

#### Using the get_ai_traffic_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_ai_traffic_with_http_info(project_id, opts)

```ruby
begin
  # AI referral traffic (Scale+)
  data, status_code, headers = api_instance.get_ai_traffic_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_ai_traffic_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **source** | **String** | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| **granularity** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_prompt_summary

> <PromptSummaryResponse> get_prompt_summary(project_id, opts)

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass `breakdown=model` to split each prompt by model.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  breakdown: 'model', # String | Add per-(prompt, model) rows to the output
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  sort: 'responses', # String | 
  sort_dir: 'asc', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Per-prompt metrics summary
  result = api_instance.get_prompt_summary(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_prompt_summary: #{e}"
end
```

#### Using the get_prompt_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptSummaryResponse>, Integer, Hash)> get_prompt_summary_with_http_info(project_id, opts)

```ruby
begin
  # Per-prompt metrics summary
  data, status_code, headers = api_instance.get_prompt_summary_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptSummaryResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_prompt_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **breakdown** | **String** | Add per-(prompt, model) rows to the output | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **sort** | **String** |  | [optional][default to &#39;responses&#39;] |
| **sort_dir** | **String** |  | [optional][default to &#39;desc&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**PromptSummaryResponse**](PromptSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_share_of_voice

> <SovResponse> get_share_of_voice(project_id, opts)

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  granularity: 'day', # String | 
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  view: 'over_time' # String | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others.
}

begin
  # Share of Voice
  result = api_instance.get_share_of_voice(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_share_of_voice: #{e}"
end
```

#### Using the get_share_of_voice_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SovResponse>, Integer, Hash)> get_share_of_voice_with_http_info(project_id, opts)

```ruby
begin
  # Share of Voice
  data, status_code, headers = api_instance.get_share_of_voice_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SovResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_share_of_voice_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **view** | **String** | Which Share of Voice projection to flatten. Only valid together with &#39;output&#39;. &#39;over_time&#39; (default) is one row per date and actor, &#39;current&#39; the ranked snapshot, &#39;breakdown&#39; the Top 4 plus Others. | [optional][default to &#39;over_time&#39;] |

### Return type

[**SovResponse**](SovResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_summary

> <SummaryResponse> get_summary(project_id, opts)

Aggregated metrics summary

Same as /metrics/timeseries but adds a `summary` block with total/min/max/last per metric per actor, plus a `position_distribution` block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. `total` is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an `aggregation` field (`sum` or `average`).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  metrics: 'metrics_example', # String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
  granularity: 'day', # String | 
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Aggregated metrics summary
  result = api_instance.get_summary(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_summary: #{e}"
end
```

#### Using the get_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SummaryResponse>, Integer, Hash)> get_summary_with_http_info(project_id, opts)

```ruby
begin
  # Aggregated metrics summary
  data, status_code, headers = api_instance.get_summary_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SummaryResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **metrics** | **String** | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String** |  | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**SummaryResponse**](SummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_timeseries

> <TimeseriesResponse> get_timeseries(project_id, opts)

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  metrics: 'metrics_example', # String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
  granularity: 'day', # String | 
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  include_project: true, # Boolean | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Time-series metrics
  result = api_instance.get_timeseries(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_timeseries: #{e}"
end
```

#### Using the get_timeseries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TimeseriesResponse>, Integer, Hash)> get_timeseries_with_http_info(project_id, opts)

```ruby
begin
  # Time-series metrics
  data, status_code, headers = api_instance.get_timeseries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TimeseriesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_timeseries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **metrics** | **String** | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String** |  | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **include_project** | **Boolean** |  | [optional][default to true] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**TimeseriesResponse**](TimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_top_sources

> <TopSourcesResponse> get_top_sources(project_id, opts)

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MetricsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  sort: 'total_responses', # String | 
  query: 'query_example', # String | Filter domains by case-insensitive partial match
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Top cited sources
  result = api_instance.get_top_sources(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_top_sources: #{e}"
end
```

#### Using the get_top_sources_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TopSourcesResponse>, Integer, Hash)> get_top_sources_with_http_info(project_id, opts)

```ruby
begin
  # Top cited sources
  data, status_code, headers = api_instance.get_top_sources_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TopSourcesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MetricsApi->get_top_sources_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **sort** | **String** |  | [optional][default to &#39;total_responses&#39;] |
| **query** | **String** | Filter domains by case-insensitive partial match | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**TopSourcesResponse**](TopSourcesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

