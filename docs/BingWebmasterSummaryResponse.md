# LLMPulse::BingWebmasterSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **site** | **String** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional] |
| **sync_status** | **String** | State of the daily sync: pending, syncing, completed, failed or on_hold. on_hold means Bing refused the stored API key or the site is no longer verified: the data already synced still answers but stops updating until the site is reconnected in Preferences &gt; Project Settings &gt; Connections. | [optional] |
| **last_synced_at** | **Time** | When the site last synced. Null before its first sync, or while history_current is false. | [optional] |
| **history_current** | **Boolean** | False right after the site was changed and before its first sync. Until then the response holds no data and data_through is null. | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | The last day synced for the site. Later days are missing, not zero. | [optional] |
| **totals** | [**BingWebmasterMetrics**](BingWebmasterMetrics.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::BingWebmasterSummaryResponse.new(
  project_id: null,
  site: null,
  sync_status: null,
  last_synced_at: null,
  history_current: null,
  from: null,
  to: null,
  data_through: null,
  totals: null,
  request_id: null
)
```

