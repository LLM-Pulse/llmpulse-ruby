# LLMPulse::BingWebmasterListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **site** | **String** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional] |
| **sync_status** | **String** | State of the daily sync: pending, syncing, completed, failed or on_hold (the data already synced still answers, but stops updating until the site is reconnected) | [optional] |
| **last_synced_at** | **Time** | When the site last synced. Null before its first sync, or while history_current is false. | [optional] |
| **history_current** | **Boolean** | False right after the site was changed and before its first sync. Until then data is empty and data_through is null. | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | The last week_ending synced for the site (the Friday that closes a Bing week) | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Distinct pages or queries found in the weeks of the window | [optional] |
| **sort** | **String** |  | [optional] |
| **weeks_covered** | **Integer** | Weeks with data whose week_ending falls in the window | [optional] |
| **data** | [**Array&lt;BingWebmasterListResponseDataInner&gt;**](BingWebmasterListResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::BingWebmasterListResponse.new(
  project_id: null,
  site: null,
  sync_status: null,
  last_synced_at: null,
  history_current: null,
  from: null,
  to: null,
  data_through: null,
  page: null,
  per_page: null,
  total: null,
  sort: null,
  weeks_covered: null,
  data: null,
  request_id: null
)
```

