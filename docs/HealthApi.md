# LLMPulse::HealthApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**ping**](HealthApi.md#ping) | **GET** /ping | Health check |


## ping

> <Ping200Response> ping(opts)

Health check

Validates the API key and optionally pings a project. Returns the authenticated user_id, project (if project_id is supplied), and a request_id.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::HealthApi.new
opts = {
  project_id: 56 # Integer | Optional project to verify access for
}

begin
  # Health check
  result = api_instance.ping(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling HealthApi->ping: #{e}"
end
```

#### Using the ping_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Ping200Response>, Integer, Hash)> ping_with_http_info(opts)

```ruby
begin
  # Health check
  data, status_code, headers = api_instance.ping_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Ping200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling HealthApi->ping_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Optional project to verify access for | [optional] |

### Return type

[**Ping200Response**](Ping200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

