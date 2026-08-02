# LLMPulse::Project

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **name** | **String** | Internal project label (sidebar, settings, admin) | [optional] |
| **brand_name** | **String** | LLM-facing brand label (used in prompts and customer-facing charts). Defaults to &#x60;name&#x60; when not set. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::Project.new(
  id: null,
  name: null,
  brand_name: null
)
```

