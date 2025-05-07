# Analytics, Data, Stat
everything about data, 
some images related these CRM dashboards are also available on [Push](/App/Push/README.md)


# Comparision Table

Platform	|User Identification	|Events Tracking
-|-|-
Adjust|	Available: Uses device IDs and custom user IDs (e.g., email) via SDK. Focuses on attribution and campaign tracking.	|Available: Tracks events like installs, sessions, and custom in-app events for attribution. Less focused on deep behavioral analytics compared to Mixpanel.
Airship|	Available: Supports email, named user IDs, and device IDs via SDK/API. Used for messaging and audience targeting across channels.	|Available: Tracks events like opens, clicks, and custom events for messaging campaigns and analytics. Focused on engagement and push notification performance.
AppsFlyer|	Available: Uses device IDs (GAID, IDFA) and custom customer_user_id (e.g., email). Indirect email support via custom ID. Focuses on attribution.	|Available: Tracks events like installs, in-app events, and conversions tied to campaigns. Limited to attribution-related events, less granular than analytics platforms.
Facebook|	Limited: Email or user ID available via Facebook Login, but only if user grants permission and has an email linked. Phone-based accounts may lack email.	|Available: Tracks events (e.g., app installs, purchases) via Facebook SDK for advertising and analytics. Focused on ad performance and attribution.
Firebase|	Available: Uses email, anonymous IDs, and custom IDs via Firebase Authentication. Central for user management and cross-platform tracking.	|Available: Tracks events via Firebase Analytics (e.g., screen views, custom events). Integrates with BigQuery for advanced analysis. Strong for app analytics.
Mixpanel|	Available: Uses distinct_id (e.g., email, custom ID) and user properties via SDK. Ideal for behavioral analytics and cohort tracking.	|Available: Tracks detailed custom events (e.g., page views, clicks) and funnels for product analytics. Highly granular for user behavior and retention analysis.
MoEngage|	Available: Supports email, device IDs, and custom IDs as primary identifiers via SDK/API. Used for cross-channel user profiles and engagement.	|Available: Tracks user actions (e.g., clicks, purchases) and custom events for segmentation, personalization, and campaign triggers. Robust for engagement analytics.
PostHog|	Available: Supports email, UUIDs, or custom distinct_id via SDK/API. Links anonymous and identified events for cross-session/device tracking.	|Available: Tracks autocaptured (e.g., pageviews, clicks) and custom events (e.g., sign-ups, feature usage) for product analytics. Supports funnels, retention, and session replays.


## [Adjust](Adjust)
- [10.9.0 Adjust Document](https://docs.google.com/document/d/1o4W9hWqjEqSRYWCJ2yGxwleZzpXG2BA6FxYBy_IZVMg/edit#heading=h.qv5tuf5lkyjv)
- Dashboard -> https://suite.adjust.com/datascape/report
- track device based on gps_adid(android), idfa(ios) , oaid(huawei)
- event management (properties cannot be viewed on dashboard, but need to download raw data)

## [Airship](Airship)
- [Dashboard](https://go.airship.com/apps/TDTGyqSbQyq4XHajj62UrA/contact_management/channel/35145b1c-b746-444b-a8e0-026c4473f5fe)

## [Appsflyer](appsflyer)
- event management (properties cannot be viewed on dashboard, but need to download raw data)
- [Live events tracking ✅](https://support.appsflyer.com/hc/en-us/articles/207031996-Registering-test-devices#register-a-device-using-the-appsflyer-device-id-app-admin-only)

## [Firebase / GA4](Firebase)
- [Dashboard](https://console.firebase.google.com/u/1/project/savyour-test/analytics/app/ios:com.disrupt.savyour/events/)
- Live events tracking ✅

## [Facebook](Facebook)
- [Dashboard](https://www.facebook.com/events_manager2/overview)
- [Facebook Conversion Api](https://www.youtube.com/watch?v=Tqb9GcHlAfk)
> After Apple rolled out the IOS 14.5 updates with updated Privacy Policy, Facebook was not longer able to track the user activities of people who opt out of the tracking.
But to stay in business Facebook came up with a new way of tracking which is known as Conversion API.

## [Mixpanel](Mixpanel)
- [Dashboard](https://mixpanel.com/project/1305204/view/20473/app/users)
- track user + event management
- events can be viewed with properties on user profile
- Live events tracking ✅

## [MoEngage](Moengage)
- [Convex Document](https://docs.google.com/document/d/1FgRO8P9BUZEXUOCQfTN1m5EoogzNcWPakogHs9H6fww/edit#heading=h.u6fin22lpwu7)
- Dashboard - https://dashboard-03.moengage.com/v4/#/developers/activity
- track user + event management
- events can be viewed with properties on user profile (Activity Tab)
- Live events tracking ✅
