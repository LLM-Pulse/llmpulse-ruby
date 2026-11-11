# LLMPulse::OwnedMediaSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **connected** | **Boolean** | Whether a profile is claimed on the platform (on overview, on any platform) | [optional] |
| **kpis** | [**OwnedMediaKpis**](OwnedMediaKpis.md) |  | [optional] |
| **previous** | [**OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  | [optional] |
| **changes** | [**OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  | [optional] |
| **weekly** | [**Array&lt;OwnedMediaWeek&gt;**](OwnedMediaWeek.md) |  | [optional] |
| **by_model** | [**Array&lt;OwnedMediaModelShare&gt;**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview | [optional] |
| **by_country** | [**Array&lt;OwnedMediaCountryShare&gt;**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview | [optional] |
| **content_types** | [**Array&lt;OwnedMediaContentTypeShare&gt;**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only | [optional] |
| **age_buckets** | [**Array&lt;OwnedMediaAgeBucketShare&gt;**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out | [optional] |
| **stores** | [**Array&lt;OwnedMediaStoreTotals&gt;**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only | [optional] |
| **platforms** | [**Array&lt;OwnedMediaPlatformRollup&gt;**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read | [optional] |
| **activity** | [**Array&lt;OwnedMediaSummaryActivityPeriod&gt;**](OwnedMediaSummaryActivityPeriod.md) | All providers. One row per actual project reporting period with runs; provider&#x3D;overview has null yours and other, and provider&#x3D;reddit also returns positive, neutral and negative sentiment counts. Citation counts use the selected date window, and periods with runs but no citation have zero | [optional] |
| **subreddit_activity** | [**Array&lt;RedditSubredditActivityPeriod&gt;**](RedditSubredditActivityPeriod.md) | provider&#x3D;reddit only. One row per subreddit and actual reporting period; the top five subreddits are separate and Others has a null subreddit | [optional] |
| **positions** | [**Array&lt;RedditPositionShare&gt;**](RedditPositionShare.md) | provider&#x3D;reddit only. Position distribution over the selected date window | [optional] |
| **brand_share** | [**Array&lt;RedditBrandShare&gt;**](RedditBrandShare.md) | provider&#x3D;reddit only. Citation share among the tracked brand and competitors with cited mentions | [optional] |
| **replies** | [**TrustpilotReplies**](TrustpilotReplies.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaSummaryResponse.new(
  project_id: null,
  provider: null,
  from: null,
  to: null,
  connected: null,
  kpis: null,
  previous: null,
  changes: null,
  weekly: null,
  by_model: null,
  by_country: null,
  content_types: null,
  age_buckets: null,
  stores: null,
  platforms: null,
  activity: null,
  subreddit_activity: null,
  positions: null,
  brand_share: null,
  replies: null,
  request_id: null
)
```

