# MoEngage Push Notification


## Dashboard (Test Push)

send test push notification from

1. Menu->Engage->Campaign (https://dashboard-02.moengage.com/v4/#/campaigns/all)
2. Create Campaign->Push->One Time

![moengage-test-push.jpg](!/moengage-test-push.jpg)

## Payload

payload is different from FCM, check from key `push_from` and map `gcm_title` and `gcm_alert`
```
{
  originalPriority: 2,
  priority: 2,
  sentTime: 1744982953270,
  data: {
    "push_from": "moengage",
    "gcm_title": "MOENGAGE TITLE",
    "gcm_alert": "Buy Now",
    "type": "products",
    "slug": "3-jogger-shorts-black",
    "gcm_activityName": "com.android.main.MainActivity",
    "gcm_campaign_id": "000000000000000022087563_L_0",
    "moe_channel_id": "moe_default_channel",
    "moe_app_id": "RPZ3I8PIPNOW0RZLQRNTAKMU_DEBUG",
    "moe_push_service": "fcm",
    "moe_cid_attr": "{\"moe_campaign_channel\": \"Push\", \"moe_delivery_type\": \"One Time\", \"campaign_version_no\": 1, \"moe_campaign_id\": \"000000000000000022087563\", \"sent_epoch_time\": 1744986048}",
    "gcm_notificationType": "normal notification"
  },
  from: '819811173704',
  messageId: '0:1744982953280018%37d032bc49efb69d',
  ttl: 129600,
  collapseKey: '000000000000000079899852_L_0'
}
```

FCM PAYLOAD EXAMPLE

```
 {
    "notification": {
        "android": {},
        "body": "Product Detail",
        "title": "FCM TITLE"
    },
    "originalPriority": 2,
    "priority": 2,
    "sentTime": 1744986689762,
    "data": {
        "type": "products",
        "slug": "3-jogger-shorts-black"
    },
    "from": "819811173704",
    "messageId": "0:1744986689773310%37d032bc37d032bc",
    "ttl": 2419200,
    "collapseKey": "com.squatwolf.staging"
}
```

## Implementation

### Android (issue in react native implementation)

Need to add build() in Android native code, to make this run. Otherwise Push won't work
https://developers.moengage.com/hc/en-us/articles/22105190881044-Getting-Started-with-React-Native-SDK

### iOS (issue in react native implementation)

Not getting ios callback





