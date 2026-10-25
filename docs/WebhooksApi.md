# LLMPulse::WebhooksApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_webhook**](WebhooksApi.md#create_webhook) | **POST** /webhooks | Create a webhook subscription |
| [**delete_webhook**](WebhooksApi.md#delete_webhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription |
| [**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /webhooks | List webhook subscriptions |
| [**sample_webhook_payloads**](WebhooksApi.md#sample_webhook_payloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads |


## create_webhook

> <CreateWebhook201Response> create_webhook(create_webhook_request)

Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (`event`, `occurred_at`, `project_id`, `subscription_id`, `data`) to the URL every time the event occurs, signed via the `X-LLMPulse-Signature` header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries receive up to 5 attempts in total, including the first, with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. While the account is below the Scale plan its subscriptions are kept but deliver nothing: no failed delivery is counted, none is disabled, and deliveries resume once the account is back on Scale or above, without resending the events from that period. Each delivery also checks that the API key that created the subscription still covers its project: an API key limited to some projects that loses the project stops the subscription for good. Idempotent for the same project + event + URL: re-posting returns the existing subscription, unless the API key or OAuth connection that created it was revoked, or that API key no longer covers the project; then it is replaced by a new subscription with a new secret. The response carries `secret` when it creates the subscription, and on a re-post only for the API key or OAuth connection that created it: any other credential gets the subscription without `secret`. Requires a `read_write` scope API key and the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::WebhooksApi.new
create_webhook_request = LLMPulse::CreateWebhookRequest.new({project_id: 37, event_type: 'mention.created', target_url: 'target_url_example'}) # CreateWebhookRequest | 

begin
  # Create a webhook subscription
  result = api_instance.create_webhook(create_webhook_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->create_webhook: #{e}"
end
```

#### Using the create_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateWebhook201Response>, Integer, Hash)> create_webhook_with_http_info(create_webhook_request)

```ruby
begin
  # Create a webhook subscription
  data, status_code, headers = api_instance.create_webhook_with_http_info(create_webhook_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateWebhook201Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->create_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_webhook_request** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  |  |

### Return type

[**CreateWebhook201Response**](CreateWebhook201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_webhook

> <DeleteWebhook200Response> delete_webhook(id)

Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a `read_write` scope API key. Works on every plan, with an API key created on Scale too, so a subscription paused below Scale can still be removed.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::WebhooksApi.new
id = 56 # Integer | 

begin
  # Delete a webhook subscription
  result = api_instance.delete_webhook(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->delete_webhook: #{e}"
end
```

#### Using the delete_webhook_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteWebhook200Response>, Integer, Hash)> delete_webhook_with_http_info(id)

```ruby
begin
  # Delete a webhook subscription
  data, status_code, headers = api_instance.delete_webhook_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteWebhook200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->delete_webhook_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |

### Return type

[**DeleteWebhook200Response**](DeleteWebhook200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_webhooks

> <ListWebhooks200Response> list_webhooks(opts)

List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. A read-only API key receives each `target_url` masked to its scheme, host and any non-default port followed by `/…`, because the full URL can let anyone post to the receiver; a `read_write` scope key receives the full URL. Works on every plan, with an API key created on Scale too. Below Scale the subscriptions are kept but deliver nothing, and they can still be listed and deleted.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::WebhooksApi.new
opts = {
  project_id: 56, # Integer | Optional project filter
  page: 56, # Integer | 
  per_page: 56 # Integer | Max 100
}

begin
  # List webhook subscriptions
  result = api_instance.list_webhooks(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks: #{e}"
end
```

#### Using the list_webhooks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListWebhooks200Response>, Integer, Hash)> list_webhooks_with_http_info(opts)

```ruby
begin
  # List webhook subscriptions
  data, status_code, headers = api_instance.list_webhooks_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListWebhooks200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->list_webhooks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Optional project filter | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** | Max 100 | [optional] |

### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## sample_webhook_payloads

> <SampleWebhookPayloads200Response> sample_webhook_payloads(event_type, project_id)

Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project's most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::WebhooksApi.new
event_type = 'mention.created' # String | 
project_id = 56 # Integer | 

begin
  # Sample event payloads
  result = api_instance.sample_webhook_payloads(event_type, project_id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->sample_webhook_payloads: #{e}"
end
```

#### Using the sample_webhook_payloads_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SampleWebhookPayloads200Response>, Integer, Hash)> sample_webhook_payloads_with_http_info(event_type, project_id)

```ruby
begin
  # Sample event payloads
  data, status_code, headers = api_instance.sample_webhook_payloads_with_http_info(event_type, project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SampleWebhookPayloads200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling WebhooksApi->sample_webhook_payloads_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **event_type** | **String** |  |  |
| **project_id** | **Integer** |  |  |

### Return type

[**SampleWebhookPayloads200Response**](SampleWebhookPayloads200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

