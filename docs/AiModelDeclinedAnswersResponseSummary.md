# LLMPulse::AiModelDeclinedAnswersResponseSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **answers** | **Integer** | Finished runs of the model, declined ones included | [optional] |
| **declined** | **Integer** | Answers the model declined | [optional] |
| **decline_rate** | **Float** |  | [optional] |
| **safety_filter** | **Integer** | Answers declined by the model&#39;s own safety filters | [optional] |
| **safety_filter_rate** | **Float** |  | [optional] |
| **topic_refusal** | **Integer** | Answers that declined the topic itself, such as tobacco, gambling or alcohol | [optional] |
| **topic_refusal_rate** | **Float** |  | [optional] |
| **last_declined_at** | **Time** | When the latest declined answer of the window was created; null when none was declined | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelDeclinedAnswersResponseSummary.new(
  answers: null,
  declined: null,
  decline_rate: null,
  safety_filter: null,
  safety_filter_rate: null,
  topic_refusal: null,
  topic_refusal_rate: null,
  last_declined_at: null
)
```

