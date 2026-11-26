# LLMPulse::AdRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** | Advertising domain; null on a placement that names none (view&#x3D;ads) |  |
| **ads** | **Integer** | Placements of the domain (view&#x3D;advertisers) | [optional] |
| **executions** | **Integer** | Answers that carried them (view&#x3D;advertisers) | [optional] |
| **prompts** | **Integer** | Distinct prompts that triggered them (view&#x3D;advertisers) | [optional] |
| **avg_position** | **Float** | Average position, 1 is the best slot; null when no placement has one (view&#x3D;advertisers) | [optional] |
| **best_position** | **Integer** | Best position, 1 is the best slot (view&#x3D;advertisers) | [optional] |
| **id** | **Integer** | The placement (view&#x3D;ads) | [optional] |
| **model** | **String** |  | [optional] |
| **title** | **String** |  | [optional] |
| **snippet** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **position** | **Integer** | Position of the placement, 1 is the best slot (view&#x3D;ads) | [optional] |
| **is_client** | **Boolean** | Whether the placement is identified as your brand&#39;s own (view&#x3D;ads) | [optional] |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **prompt_execution_id** | **Integer** |  | [optional] |
| **executed_at** | **Time** | When the answer that carried the placement was collected (view&#x3D;ads) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AdRow.new(
  domain: null,
  ads: null,
  executions: null,
  prompts: null,
  avg_position: null,
  best_position: null,
  id: null,
  model: null,
  title: null,
  snippet: null,
  url: null,
  position: null,
  is_client: null,
  prompt_id: null,
  prompt_text: null,
  prompt_execution_id: null,
  executed_at: null
)
```

