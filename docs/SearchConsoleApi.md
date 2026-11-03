# LLMPulse::SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_search_console_ai_visibility_gaps**](SearchConsoleApi.md#get_search_console_ai_visibility_gaps) | **GET** /search_console/ai_visibility_gaps | Search Console queries vs AI tracking (Growth+) |
| [**get_search_console_brand_split**](SearchConsoleApi.md#get_search_console_brand_split) | **GET** /search_console/brand_split | Search Console branded vs non-branded split (Growth+) |
| [**get_search_console_cannibalization**](SearchConsoleApi.md#get_search_console_cannibalization) | **GET** /search_console/cannibalization | Search Console keyword cannibalization (Growth+) |
| [**get_search_console_decay**](SearchConsoleApi.md#get_search_console_decay) | **GET** /search_console/decay | Search Console content decay (Growth+) |
| [**get_search_console_opportunities**](SearchConsoleApi.md#get_search_console_opportunities) | **GET** /search_console/opportunities | Search Console ranking opportunities (Growth+) |
| [**get_search_console_pages**](SearchConsoleApi.md#get_search_console_pages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**get_search_console_queries**](SearchConsoleApi.md#get_search_console_queries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**get_search_console_rows**](SearchConsoleApi.md#get_search_console_rows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+) |
| [**get_search_console_summary**](SearchConsoleApi.md#get_search_console_summary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**get_search_console_timeseries**](SearchConsoleApi.md#get_search_console_timeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |
| [**list_search_console_properties**](SearchConsoleApi.md#list_search_console_properties) | **GET** /search_console/properties | List Search Console properties (Growth+) |


## get_search_console_ai_visibility_gaps

> <SearchConsoleAiVisibilityGapsResponse> get_search_console_ai_visibility_gaps(project_id, opts)

Search Console queries vs AI tracking (Growth+)

The property's queries with at least min_impressions impressions, most impressions first, each matched against the project's prompts. The match is exact and deliberately conservative: a query matches a prompt with the same text once both are lowercased, accents and similar letters folded the way AI answers are matched for brand mentions, spacing squeezed and leading or trailing punctuation dropped (best crm for agencies matches Best CRM for agencies?, but not What is the best CRM for agencies). When two prompts share a text (other countries or languages), the oldest is the match. A matched query carries its prompt_id, responses (the prompt's AI answers in the same window, over the account's enabled models) and brand_visibility, the percent of those answers that mention the brand (null before any answer), as /metrics/prompt_summary computes it. unmatched_only=true lists only the queries no prompt matches: search demand the AI tracking does not cover yet, the strongest candidates to add as prompts. Rows with a prompt and a low brand_visibility are queries people search for where AI answers rarely mention the brand; how low is low is the caller's choice. matched_count counts the qualifying queries a prompt matches. A team member also needs read access to the Overview, which holds prompt-level Brand Visibility, or gets ERR_INSUFFICIENT_PERMISSION. Reads Google's top 25,000 queries per property (truncated: true when reached) and excludes anonymized queries. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  property: 'all', # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  min_impressions: 56, # Integer | Smallest impressions a query needs.
  unmatched_only: true, # Boolean | List only the queries no prompt of the project matches (true or false).
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto' # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
}

begin
  # Search Console queries vs AI tracking (Growth+)
  result = api_instance.get_search_console_ai_visibility_gaps(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_ai_visibility_gaps: #{e}"
end
```

#### Using the get_search_console_ai_visibility_gaps_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleAiVisibilityGapsResponse>, Integer, Hash)> get_search_console_ai_visibility_gaps_with_http_info(project_id, opts)

```ruby
begin
  # Search Console queries vs AI tracking (Growth+)
  data, status_code, headers = api_instance.get_search_console_ai_visibility_gaps_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleAiVisibilityGapsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_ai_visibility_gaps_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **min_impressions** | **Integer** | Smallest impressions a query needs. | [optional][default to 100] |
| **unmatched_only** | **Boolean** | List only the queries no prompt of the project matches (true or false). | [optional][default to false] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |

### Return type

[**SearchConsoleAiVisibilityGapsResponse**](SearchConsoleAiVisibilityGapsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_brand_split

> <SearchConsoleBrandSplitResponse> get_search_console_brand_split(project_id, opts)

Search Console branded vs non-branded split (Growth+)

Splits the property's impressions and clicks into branded queries, which contain one of the project's brand terms as a whole word, case-insensitively (brand_terms: its brand name, matching names, app names and domain, each also matched with its accents folded and with either apostrophe, so Nestlé also matches nestle and L’Oréal matches l'oreal), and non-branded ones, next to the unfiltered totals. Google applies the split itself as a regular-expression query filter, so it covers every query Google counts, not only the 25,000 rows one read lists. Use it to see how much search traffic comes from people who already know the brand and how much from discovery searches, and how each side evolves across date ranges. Google leaves anonymized queries out of any query filter, so unclassified holds the impressions and clicks neither side counts. Returns ERR_INVALID_PARAM when the brand terms are too long for one Google filter (4,096 characters, Google's documented limit), and ERR_SEARCH_CONSOLE_UPSTREAM (503) if Google refuses the filter built from them; our team is alerted in that case. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  property: 'all', # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto' # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
}

begin
  # Search Console branded vs non-branded split (Growth+)
  result = api_instance.get_search_console_brand_split(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_brand_split: #{e}"
end
```

#### Using the get_search_console_brand_split_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleBrandSplitResponse>, Integer, Hash)> get_search_console_brand_split_with_http_info(project_id, opts)

```ruby
begin
  # Search Console branded vs non-branded split (Growth+)
  data, status_code, headers = api_instance.get_search_console_brand_split_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleBrandSplitResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_brand_split_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |

### Return type

[**SearchConsoleBrandSplitResponse**](SearchConsoleBrandSplitResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_cannibalization

> <SearchConsoleCannibalizationResponse> get_search_console_cannibalization(project_id, opts)

Search Console keyword cannibalization (Growth+)

Queries with at least min_impressions impressions for which two or more pages each take at least min_share (default 0.1) of the query's impressions, most impressions first, each with its competing pages (share, impressions, clicks, ctr, position). Use it to find the keywords several of the site's pages fight over, and decide which pages to merge, redirect or differentiate. Google counts page-by-query impressions per page, so a query's impressions here can exceed its property-wide figure. Reads Google's top 25,000 page-query rows per property (truncated: true when reached). With output=flat or csv, each competing page is its own row, with its URL in page_url. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  property: 'all', # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  min_impressions: 56, # Integer | Smallest impressions a query needs.
  min_share: 8.14, # Float | Smallest fraction (0.01 to 0.5) of the query's impressions a page needs to count as competing.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto' # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
}

begin
  # Search Console keyword cannibalization (Growth+)
  result = api_instance.get_search_console_cannibalization(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_cannibalization: #{e}"
end
```

#### Using the get_search_console_cannibalization_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleCannibalizationResponse>, Integer, Hash)> get_search_console_cannibalization_with_http_info(project_id, opts)

```ruby
begin
  # Search Console keyword cannibalization (Growth+)
  data, status_code, headers = api_instance.get_search_console_cannibalization_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleCannibalizationResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_cannibalization_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **min_impressions** | **Integer** | Smallest impressions a query needs. | [optional][default to 100] |
| **min_share** | **Float** | Smallest fraction (0.01 to 0.5) of the query&#39;s impressions a page needs to count as competing. | [optional][default to 0.1] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |

### Return type

[**SearchConsoleCannibalizationResponse**](SearchConsoleCannibalizationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_decay

> <SearchConsoleDecayResponse> get_search_console_decay(project_id, opts)

Search Console content decay (Growth+)

Pages (or queries, with dimension=query) that had at least min_clicks clicks in the window just before the requested one (previous_from to previous_to, the same length) and lost clicks since, biggest loss first, with clicks, impressions and average position in both windows. Use it to find the pages losing traffic and to tell lost rankings (a worse position) from lost demand (fewer impressions at a stable position). The requested window ends at compared_through, the last day Google has published when that is before to, so days Google has not filled in yet never read as a loss. Both windows must fit in Google's 487-day retention, or the request returns ERR_INVALID_PARAM. Reads Google's top 25,000 rows per window and property (truncated: true when reached); when the requested window reaches that cap, a page or query missing from it is left out rather than read as a loss. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  property: 'all', # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  dimension: 'page', # String | Compare pages or queries.
  min_clicks: 56, # Integer | Smallest clicks in the previous window.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto' # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
}

begin
  # Search Console content decay (Growth+)
  result = api_instance.get_search_console_decay(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_decay: #{e}"
end
```

#### Using the get_search_console_decay_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleDecayResponse>, Integer, Hash)> get_search_console_decay_with_http_info(project_id, opts)

```ruby
begin
  # Search Console content decay (Growth+)
  data, status_code, headers = api_instance.get_search_console_decay_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleDecayResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_decay_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **dimension** | **String** | Compare pages or queries. | [optional][default to &#39;page&#39;] |
| **min_clicks** | **Integer** | Smallest clicks in the previous window. | [optional][default to 10] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |

### Return type

[**SearchConsoleDecayResponse**](SearchConsoleDecayResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_opportunities

> <SearchConsoleOpportunitiesResponse> get_search_console_opportunities(project_id, opts)

Search Console ranking opportunities (Growth+)

Queries whose average position is between min_position and max_position (default 4 to 20) with at least min_impressions impressions, ranked by potential_clicks: the clicks a move into the top 3 would add at top_ctr, the CTR the property's own queries averaging position 3 or better get in the same window. Use it to find the queries where a small ranking gain would add the most traffic. No outside CTR curve is used: with no top-3 query in the window, top_ctr and potential_clicks are null. Reads Google's top 25,000 queries per property (truncated: true when reached) and excludes anonymized queries. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  property: 'all', # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  min_impressions: 56, # Integer | Smallest impressions a query needs.
  min_position: 8.14, # Float | Best average position to include.
  max_position: 8.14, # Float | Worst average position to include; at least min_position.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto' # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
}

begin
  # Search Console ranking opportunities (Growth+)
  result = api_instance.get_search_console_opportunities(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_opportunities: #{e}"
end
```

#### Using the get_search_console_opportunities_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleOpportunitiesResponse>, Integer, Hash)> get_search_console_opportunities_with_http_info(project_id, opts)

```ruby
begin
  # Search Console ranking opportunities (Growth+)
  data, status_code, headers = api_instance.get_search_console_opportunities_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleOpportunitiesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_opportunities_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **min_impressions** | **Integer** | Smallest impressions a query needs. | [optional][default to 100] |
| **min_position** | **Float** | Best average position to include. | [optional][default to 4] |
| **max_position** | **Float** | Worst average position to include; at least min_position. | [optional][default to 20] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |

### Return type

[**SearchConsoleOpportunitiesResponse**](SearchConsoleOpportunitiesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_pages

> <SearchConsoleListResponse> get_search_console_pages(project_id, opts)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  sort: 'impressions', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  start_row: 56, # Integer | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto', # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
  property: 'all' # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
}

begin
  # Top Search Console pages (Growth+)
  result = api_instance.get_search_console_pages(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_pages: #{e}"
end
```

#### Using the get_search_console_pages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleListResponse>, Integer, Hash)> get_search_console_pages_with_http_info(project_id, opts)

```ruby
begin
  # Top Search Console pages (Growth+)
  data, status_code, headers = api_instance.get_search_console_pages_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleListResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_pages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **String** |  | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **start_row** | **Integer** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional][default to 0] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_queries

> <SearchConsoleListResponse> get_search_console_queries(project_id, opts)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  sort: 'impressions', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  start_row: 56, # Integer | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto', # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
  property: 'all' # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
}

begin
  # Top Search Console queries (Growth+)
  result = api_instance.get_search_console_queries(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_queries: #{e}"
end
```

#### Using the get_search_console_queries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleListResponse>, Integer, Hash)> get_search_console_queries_with_http_info(project_id, opts)

```ruby
begin
  # Top Search Console queries (Growth+)
  data, status_code, headers = api_instance.get_search_console_queries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleListResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_queries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **String** |  | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **start_row** | **Integer** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional][default to 0] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_rows

> <SearchConsoleRowsResponse> get_search_console_rows(project_id, dimensions, opts)

Search Console rows by several dimensions (Growth+)

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance, property) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
dimensions = 'page,query' # String | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance, property. Each becomes a field of every row; country and device values are lowercase. property is the Search Console property the row comes from (see the property parameter).
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  sort: 'impressions', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  start_row: 56, # Integer | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto', # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
  property: 'all' # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
}

begin
  # Search Console rows by several dimensions (Growth+)
  result = api_instance.get_search_console_rows(project_id, dimensions, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_rows: #{e}"
end
```

#### Using the get_search_console_rows_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleRowsResponse>, Integer, Hash)> get_search_console_rows_with_http_info(project_id, dimensions, opts)

```ruby
begin
  # Search Console rows by several dimensions (Growth+)
  data, status_code, headers = api_instance.get_search_console_rows_with_http_info(project_id, dimensions, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleRowsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_rows_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **dimensions** | **String** | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance, property. Each becomes a field of every row; country and device values are lowercase. property is the Search Console property the row comes from (see the property parameter). |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **sort** | **String** |  | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **start_row** | **Integer** | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [optional][default to 0] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |

### Return type

[**SearchConsoleRowsResponse**](SearchConsoleRowsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_summary

> <SearchConsoleSummaryResponse> get_search_console_summary(project_id, opts)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension=country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit, or dimension=property for one row per property read (with a property list or property=all). With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google's 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  dimension: 'country', # String | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. property gives one row per property read (see the property parameter).
  limit: 56, # Integer | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto', # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
  property: 'all' # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
}

begin
  # Search Console summary (Growth+)
  result = api_instance.get_search_console_summary(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_summary: #{e}"
end
```

#### Using the get_search_console_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleSummaryResponse>, Integer, Hash)> get_search_console_summary_with_http_info(project_id, opts)

```ruby
begin
  # Search Console summary (Growth+)
  data, status_code, headers = api_instance.get_search_console_summary_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleSummaryResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **dimension** | **String** | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. property gives one row per property read (see the property parameter). | [optional] |
| **limit** | **Integer** | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |

### Return type

[**SearchConsoleSummaryResponse**](SearchConsoleSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_timeseries

> <SearchConsoleTimeseriesResponse> get_search_console_timeseries(project_id, opts)

Search Console time series (Growth+)

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences > Project Settings > Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to). At most 487, Google's retention.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Defaults to 30 days ago.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches.
  granularity: 'day', # String | 
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  search_type: 'web', # String | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them.
  filters: '[{"dimension":"page","operator":"contains","expression":"/blog/"}]', # String | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted.
  data_state: 'final', # String | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change.
  aggregation_type: 'auto', # String | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter.
  property: 'all' # String | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would.
}

begin
  # Search Console time series (Growth+)
  result = api_instance.get_search_console_timeseries(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_timeseries: #{e}"
end
```

#### Using the get_search_console_timeseries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsoleTimeseriesResponse>, Integer, Hash)> get_search_console_timeseries_with_http_info(project_id, opts)

```ruby
begin
  # Search Console time series (Growth+)
  data, status_code, headers = api_instance.get_search_console_timeseries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsoleTimeseriesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_timeseries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to). At most 487, Google&#39;s retention. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [optional] |
| **granularity** | **String** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **search_type** | **String** | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [optional][default to &#39;web&#39;] |
| **filters** | **String** | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [optional] |
| **data_state** | **String** | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [optional][default to &#39;final&#39;] |
| **aggregation_type** | **String** | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [optional][default to &#39;auto&#39;] |
| **property** | **String** | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [optional] |

### Return type

[**SearchConsoleTimeseriesResponse**](SearchConsoleTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_search_console_properties

> <SearchConsolePropertiesResponse> list_search_console_properties(project_id, opts)

List Search Console properties (Growth+)

The Google Search Console properties connected to the project, up to max_properties, from one or more Google accounts, primary first. Each id is a value the property parameter of the other /search_console endpoints accepts: omit it for the primary property, pass one id, or a comma-separated list or all to combine several. type is domain (sc-domain:example.com, which counts every subdomain and protocol) or url_prefix. status reconnect_required means Google refused the stored access; reconnect the property in Preferences > Project Settings > Data Connections. An empty data list means the project has no Search Console connection. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List Search Console properties (Growth+)
  result = api_instance.list_search_console_properties(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->list_search_console_properties: #{e}"
end
```

#### Using the list_search_console_properties_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SearchConsolePropertiesResponse>, Integer, Hash)> list_search_console_properties_with_http_info(project_id, opts)

```ruby
begin
  # List Search Console properties (Growth+)
  data, status_code, headers = api_instance.list_search_console_properties_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SearchConsolePropertiesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->list_search_console_properties_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**SearchConsolePropertiesResponse**](SearchConsolePropertiesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

