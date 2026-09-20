# LLMPulse::AccountApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_account**](AccountApi.md#get_account) | **GET** /account | Account plan, quota usage and rate limits |


## get_account

> <GetAccount200Response> get_account

Account plan, quota usage and rate limits

Returns the account plan, tracking cadence, subscription window, how much of each quota is used (prompts, projects, competitors per project, monthly GEO Writer tasks, team members) and the published API rate limits. Limits resolve through the account owner, so a team member sees the capacity that applies to them. An unlimited quota returns limit and remaining as null with unlimited set to true, since Infinity is not representable in JSON. The subscription block is only present for callers who can access Billing and Plans in the app (the account owner, or a team member with billing access); everyone else gets the same response without that key. requests_per_minute is the ceiling of the key used for the call, not a fixed number.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AccountApi.new

begin
  # Account plan, quota usage and rate limits
  result = api_instance.get_account
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling AccountApi->get_account: #{e}"
end
```

#### Using the get_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAccount200Response>, Integer, Hash)> get_account_with_http_info

```ruby
begin
  # Account plan, quota usage and rate limits
  data, status_code, headers = api_instance.get_account_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAccount200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling AccountApi->get_account_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetAccount200Response**](GetAccount200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

