# LLMPulse::CreateProjectDraftRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **website_url** | **String** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
| **main_country** | **String** |  |  |
| **main_language** | **String** |  |  |
| **use_subdomain** | **Boolean** |  | [optional][default to false] |
| **suggest** | **Boolean** |  | [optional][default to true] |
| **execute_prompts_immediately** | **Boolean** |  | [optional][default to true] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateProjectDraftRequest.new(
  website_url: null,
  main_country: null,
  main_language: null,
  use_subdomain: null,
  suggest: null,
  execute_prompts_immediately: null
)
```

