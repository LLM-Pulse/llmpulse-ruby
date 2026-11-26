# LLMPulse::AnalystScoreRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **brand** | **String** | Brand name; the subject name in a custom study |  |
| **is_project** | **Boolean** | Whether it is the project&#39;s own brand; in a custom study, the focus subject |  |
| **model** | **String** |  |  |
| **report_date** | **Date** |  |  |
| **dimension** | **String** | Dimension key, as the dimension filter takes it |  |
| **dimension_name** | **String** |  |  |
| **attribute** | **String** | Attribute key within the dimension |  |
| **attribute_name** | **String** |  |  |
| **score** | **Object** | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model&#39;s output is stored without coercion |  |
| **reasoning** | **String** | Why the model gave this score; null when it gave no reasoning |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AnalystScoreRow.new(
  brand: null,
  is_project: null,
  model: null,
  report_date: null,
  dimension: null,
  dimension_name: null,
  attribute: null,
  attribute_name: null,
  score: null,
  reasoning: null
)
```

