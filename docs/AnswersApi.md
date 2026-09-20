# LLMPulse::AnswersApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_answer**](AnswersApi.md#get_answer) | **GET** /answers/{id} | Get one AI response |
| [**list_answers**](AnswersApi.md#list_answers) | **GET** /answers | List AI responses |


## get_answer

> <AnswerDetails> get_answer(project_id, id, opts)

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass `include_source_page_details=true` to nest page-cache metadata under each source.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnswersApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 
opts = {
  include_source_page_details: true # Boolean | 
}

begin
  # Get one AI response
  result = api_instance.get_answer(project_id, id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling AnswersApi->get_answer: #{e}"
end
```

#### Using the get_answer_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AnswerDetails>, Integer, Hash)> get_answer_with_http_info(project_id, id, opts)

```ruby
begin
  # Get one AI response
  data, status_code, headers = api_instance.get_answer_with_http_info(project_id, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AnswerDetails>
rescue LLMPulse::ApiError => e
  puts "Error when calling AnswersApi->get_answer_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** |  |  |
| **include_source_page_details** | **Boolean** |  | [optional][default to false] |

### Return type

[**AnswerDetails**](AnswerDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_answers

> list_answers(project_id, opts)

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass `query` for case-insensitive full-text search inside response texts: `total` becomes the exact count of matching responses and each item returns `snippet` + `match_count` instead of `response`/`response_truncated`.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnswersApi.new
project_id = 56 # Integer | Project ID
opts = {
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  citation_filter: 'cites_you', # String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  query: 'query_example', # String | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode.
  no_result: true # Boolean | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false = only real answers, true = only sentinels, omit = both. Every item carries its own no_result flag.
}

begin
  # List AI responses
  api_instance.list_answers(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling AnswersApi->list_answers: #{e}"
end
```

#### Using the list_answers_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_answers_with_http_info(project_id, opts)

```ruby
begin
  # List AI responses
  data, status_code, headers = api_instance.list_answers_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AnswersApi->list_answers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **mention_filter** | **String** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **String** | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **query** | **String** | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [optional] |
| **no_result** | **Boolean** | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false &#x3D; only real answers, true &#x3D; only sentinels, omit &#x3D; both. Every item carries its own no_result flag. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

