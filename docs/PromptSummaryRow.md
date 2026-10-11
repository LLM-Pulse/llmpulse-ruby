# LLMPulse::PromptSummaryRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **model** | **String** | Only present when breakdown&#x3D;model | [optional] |
| **responses** | **Integer** |  | [optional] |
| **mentions** | **Integer** |  | [optional] |
| **citations** | **Integer** |  | [optional] |
| **visibility** | **Float** |  | [optional] |
| **mention_rate** | **Float** |  | [optional] |
| **citation_rate** | **Float** |  | [optional] |
| **avg_mention_position** | **Float** |  | [optional] |
| **avg_position** | **Float** |  | [optional] |
| **app_url** | **String** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | [optional] |
| **country_code** | **String** | Country of the prompt, as in /dimensions/prompts | [optional] |
| **language_code** | **String** | Language of the prompt, as in /dimensions/prompts | [optional] |
| **prompt_type** | **String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | [optional] |
| **brand_kind** | **String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | [optional] |
| **tags** | [**Array&lt;TagRef&gt;**](TagRef.md) | Every tag the prompt belongs to | [optional] |
| **sentiment_responses** | **Integer** | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) | [optional] |
| **sentiment_very_positive** | **Float** | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 | [optional] |
| **sentiment_positive** | **Float** | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 | [optional] |
| **sentiment_neutral** | **Float** | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 | [optional] |
| **sentiment_negative** | **Float** | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 | [optional] |
| **sentiment_very_negative** | **Float** | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 | [optional] |
| **net_sentiment** | **Float** | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptSummaryRow.new(
  prompt_id: null,
  prompt_text: null,
  model: null,
  responses: null,
  mentions: null,
  citations: null,
  visibility: null,
  mention_rate: null,
  citation_rate: null,
  avg_mention_position: null,
  avg_position: null,
  app_url: null,
  country_code: null,
  language_code: null,
  prompt_type: null,
  brand_kind: null,
  tags: null,
  sentiment_responses: null,
  sentiment_very_positive: null,
  sentiment_positive: null,
  sentiment_neutral: null,
  sentiment_negative: null,
  sentiment_very_negative: null,
  net_sentiment: null
)
```

