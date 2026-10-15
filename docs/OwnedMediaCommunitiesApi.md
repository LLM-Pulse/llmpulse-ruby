# LLMPulse::OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_owned_media_profiles**](OwnedMediaCommunitiesApi.md#get_owned_media_profiles) | **GET** /projects/{id}/owned_media | Get a project&#39;s owned-media profiles |
| [**get_owned_media_summary**](OwnedMediaCommunitiesApi.md#get_owned_media_summary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary |
| [**list_owned_media**](OwnedMediaCommunitiesApi.md#list_owned_media) | **GET** /dimensions/owned_media | List owned-media citations |
| [**list_owned_media_citing_prompts**](OwnedMediaCommunitiesApi.md#list_owned_media_citing_prompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item |
| [**list_reddit_citations**](OwnedMediaCommunitiesApi.md#list_reddit_citations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**update_owned_media_profiles**](OwnedMediaCommunitiesApi.md#update_owned_media_profiles) | **PATCH** /projects/{id}/owned_media | Update a project&#39;s owned-media profiles |


## get_owned_media_profiles

> <OwnedMediaProfilesResponse> get_owned_media_profiles(id)

Get a project's owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings > Owned Media shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
id = 56 # Integer | Project ID

begin
  # Get a project's owned-media profiles
  result = api_instance.get_owned_media_profiles(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->get_owned_media_profiles: #{e}"
end
```

#### Using the get_owned_media_profiles_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnedMediaProfilesResponse>, Integer, Hash)> get_owned_media_profiles_with_http_info(id)

```ruby
begin
  # Get a project's owned-media profiles
  data, status_code, headers = api_instance.get_owned_media_profiles_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnedMediaProfilesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->get_owned_media_profiles_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Project ID |  |

### Return type

[**OwnedMediaProfilesResponse**](OwnedMediaProfilesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_owned_media_summary

> <OwnedMediaSummaryResponse> get_owned_media_summary(project_id, provider, opts)

Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives the platform citations (total), yours (your profiles and their content), your_profile and your_content apart, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes the difference (percent for counts, percentage points for share_pct, null when there is nothing to compare). weekly is the citations per week, yours against everyone else. by_model and by_country split every citation of the platform; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider=mobile_apps adds stores, the per-store totals, and has no content type or age; provider=overview returns platforms, one rollup per platform the caller can read, and no breakdowns. A team member also needs the YouTube Intelligence permission for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
project_id = 56 # Integer | Project ID
provider = 'youtube' # String | The platform to summarize, or overview for every platform at once
opts = {
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00') # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
}

begin
  # Get an owned-media summary
  result = api_instance.get_owned_media_summary(project_id, provider, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->get_owned_media_summary: #{e}"
end
```

#### Using the get_owned_media_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnedMediaSummaryResponse>, Integer, Hash)> get_owned_media_summary_with_http_info(project_id, provider, opts)

```ruby
begin
  # Get an owned-media summary
  data, status_code, headers = api_instance.get_owned_media_summary_with_http_info(project_id, provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnedMediaSummaryResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->get_owned_media_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **provider** | **String** | The platform to summarize, or overview for every platform at once |  |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

### Return type

[**OwnedMediaSummaryResponse**](OwnedMediaSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_owned_media

> <OwnedMediaListResponse> list_owned_media(project_id, provider, opts)

List owned-media citations

Which owned-media content AI answers cite, by platform. `provider` is required. Each row carries a `yours` flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. view=own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
project_id = 56 # Integer | Project ID
provider = 'youtube' # String | The platform to report on
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  view: 'videos', # String | Row shape; the allowed set depends on provider
  store: 'google_play', # String | provider=mobile_apps only
  owned: true, # Boolean | Return only rows belonging to the account's own connected profile
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List owned-media citations
  result = api_instance.list_owned_media(project_id, provider, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_owned_media: #{e}"
end
```

#### Using the list_owned_media_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnedMediaListResponse>, Integer, Hash)> list_owned_media_with_http_info(project_id, provider, opts)

```ruby
begin
  # List owned-media citations
  data, status_code, headers = api_instance.list_owned_media_with_http_info(project_id, provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnedMediaListResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_owned_media_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **provider** | **String** | The platform to report on |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **view** | **String** | Row shape; the allowed set depends on provider | [optional] |
| **store** | **String** | provider&#x3D;mobile_apps only | [optional][default to &#39;google_play&#39;] |
| **owned** | **Boolean** | Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**OwnedMediaListResponse**](OwnedMediaListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_owned_media_citing_prompts

> <OwnedMediaCitingPromptsResponse> list_owned_media_citing_prompts(project_id, provider, opts)

List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
project_id = 56 # Integer | Project ID
provider = 'youtube' # String | The platform the item belongs to
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  url: 'url_example', # String | A post or video URL, or a profile or channel URL. Exclusive with profile
  profile: 'profile_example', # String | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List the answers citing an owned-media item
  result = api_instance.list_owned_media_citing_prompts(project_id, provider, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_owned_media_citing_prompts: #{e}"
end
```

#### Using the list_owned_media_citing_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnedMediaCitingPromptsResponse>, Integer, Hash)> list_owned_media_citing_prompts_with_http_info(project_id, provider, opts)

```ruby
begin
  # List the answers citing an owned-media item
  data, status_code, headers = api_instance.list_owned_media_citing_prompts_with_http_info(project_id, provider, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnedMediaCitingPromptsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_owned_media_citing_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **provider** | **String** | The platform the item belongs to |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **url** | **String** | A post or video URL, or a profile or channel URL. Exclusive with profile | [optional] |
| **profile** | **String** | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url | [optional] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**OwnedMediaCitingPromptsResponse**](OwnedMediaCitingPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_reddit_citations

> list_reddit_citations(project_id, opts)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view=subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view=authors returns one row per author; view=threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  view: 'subreddits', # String | 
  subreddit: 'subreddit_example', # String | Filter to one subreddit (name without the r/ prefix)
  author: 'author_example', # String | Filter to one Reddit author
  status: 'open', # String | view=threads only
  owned: true, # Boolean | Return only subreddits/authors the account has claimed as its own
  brand: 'brand_example', # String | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer.
  order: 'citations', # String | Sort field; the allowed set depends on view
  direction: 'asc', # String | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List cited Reddit content
  api_instance.list_reddit_citations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_reddit_citations: #{e}"
end
```

#### Using the list_reddit_citations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_reddit_citations_with_http_info(project_id, opts)

```ruby
begin
  # List cited Reddit content
  data, status_code, headers = api_instance.list_reddit_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->list_reddit_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **view** | **String** |  | [optional][default to &#39;subreddits&#39;] |
| **subreddit** | **String** | Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **String** | Filter to one Reddit author | [optional] |
| **status** | **String** | view&#x3D;threads only | [optional] |
| **owned** | **Boolean** | Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **String** | Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional] |
| **order** | **String** | Sort field; the allowed set depends on view | [optional] |
| **direction** | **String** |  | [optional][default to &#39;desc&#39;] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_owned_media_profiles

> <OwnedMediaProfilesUpdateResponse> update_owned_media_profiles(id, update_owned_media_profiles_request)

Update a project's owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings > Owned Media. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, YouTube Intelligence create to change the YouTube channel, and Projects update to change the extra profile or Reddit lists. Requires the Growth plan or above and a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::OwnedMediaCommunitiesApi.new
id = 56 # Integer | Project ID
update_owned_media_profiles_request = LLMPulse::UpdateOwnedMediaProfilesRequest.new # UpdateOwnedMediaProfilesRequest | 

begin
  # Update a project's owned-media profiles
  result = api_instance.update_owned_media_profiles(id, update_owned_media_profiles_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->update_owned_media_profiles: #{e}"
end
```

#### Using the update_owned_media_profiles_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnedMediaProfilesUpdateResponse>, Integer, Hash)> update_owned_media_profiles_with_http_info(id, update_owned_media_profiles_request)

```ruby
begin
  # Update a project's owned-media profiles
  data, status_code, headers = api_instance.update_owned_media_profiles_with_http_info(id, update_owned_media_profiles_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnedMediaProfilesUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling OwnedMediaCommunitiesApi->update_owned_media_profiles_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Project ID |  |
| **update_owned_media_profiles_request** | [**UpdateOwnedMediaProfilesRequest**](UpdateOwnedMediaProfilesRequest.md) |  |  |

### Return type

[**OwnedMediaProfilesUpdateResponse**](OwnedMediaProfilesUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

