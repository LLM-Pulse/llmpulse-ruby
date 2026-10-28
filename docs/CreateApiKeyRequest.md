# LLMPulse::CreateApiKeyRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | A label to recognize the key, for example the customer it is for |  |
| **scope** | **String** | read (default) only reads data; read_write can also create, change and delete within the key&#39;s projects | [optional][default to &#39;read&#39;] |
| **project_ids** | **Array&lt;Integer&gt;** | The projects the key is limited to, at least one |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateApiKeyRequest.new(
  name: null,
  scope: null,
  project_ids: null
)
```

