# LLMPulse::ShoppingAdsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**list_ads**](ShoppingAdsApi.md#list_ads) | **GET** /dimensions/ads | List AI ad placements |
| [**list_shopping**](ShoppingAdsApi.md#list_shopping) | **GET** /dimensions/shopping | List shopping results |


## list_ads

> list_ads(project_id, opts)

List AI ad placements

Paid placements returned inside AI answers. view=advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view=ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ShoppingAdsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  view: 'advertisers', # String | Row shape: one per advertising domain, or one per placement
  owned: true, # Boolean | Return only placements identified as the tracked brand's own (view=ads)
  order: 'ads', # String | Sort field; the allowed set depends on view
  direction: 'asc', # String | Sort direction for view=advertisers. Defaults to desc, except avg_position and domain which default to asc.
  query: 'query_example', # String | Case-insensitive substring filter on the ad title, domain or snippet
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List AI ad placements
  api_instance.list_ads(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ShoppingAdsApi->list_ads: #{e}"
end
```

#### Using the list_ads_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_ads_with_http_info(project_id, opts)

```ruby
begin
  # List AI ad placements
  data, status_code, headers = api_instance.list_ads_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ShoppingAdsApi->list_ads_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **view** | **String** | Row shape: one per advertising domain, or one per placement | [optional][default to &#39;advertisers&#39;] |
| **owned** | **Boolean** | Return only placements identified as the tracked brand&#39;s own (view&#x3D;ads) | [optional] |
| **order** | **String** | Sort field; the allowed set depends on view | [optional] |
| **direction** | **String** | Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [optional] |
| **query** | **String** | Case-insensitive substring filter on the ad title, domain or snippet | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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


## list_shopping

> list_shopping(project_id, opts)

List shopping results

Product cards returned inside AI answers. view=products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view=merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ShoppingAdsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  view: 'products', # String | Row shape: one per distinct product, or one per merchant
  owned: true, # Boolean | Return only products identified as the tracked brand's own. On view=merchants this narrows to the merchants selling those products; the totals block stays account-wide.
  order: 'appearances', # String | Sort field; the allowed set depends on view
  direction: 'asc', # String | 
  query: 'query_example', # String | Case-insensitive substring filter on the product title
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List shopping results
  api_instance.list_shopping(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling ShoppingAdsApi->list_shopping: #{e}"
end
```

#### Using the list_shopping_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_shopping_with_http_info(project_id, opts)

```ruby
begin
  # List shopping results
  data, status_code, headers = api_instance.list_shopping_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling ShoppingAdsApi->list_shopping_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **view** | **String** | Row shape: one per distinct product, or one per merchant | [optional][default to &#39;products&#39;] |
| **owned** | **Boolean** | Return only products identified as the tracked brand&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [optional] |
| **order** | **String** | Sort field; the allowed set depends on view | [optional] |
| **direction** | **String** |  | [optional][default to &#39;desc&#39;] |
| **query** | **String** | Case-insensitive substring filter on the product title | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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

