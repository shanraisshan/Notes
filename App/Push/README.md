# Push Notification
push related stuff

## Not receiving push?

Vendors kill app -> https://dontkillmyapp.com/

One Signal -> https://documentation.onesignal.com/docs/notifications-show-successful-but-are-not-being-shown

## SDKs
1. Firebase Cloud Messaging (FCM)
2. Huawei HMS Push Kit
3. Xiomi Push
4. Apple Push Notification service (APNS)
5. Amazon Device Messaging (ADM)


## Platforms
1. [Appsflyer (fcm | hms)](Appsflyer)
2. [Firebase (fcm)](Firebase)
2. [Huawei (hms)](Huawei)
3. [Mixpanel (gcm)](Mixpanel)
4. [Moengage (fcm | hms | xiomi)](Moengage)
4. [One Signal (fcm | hms)](OneSignal)
6. [Urban Airship (fcm | hms)](Airship)

## Send Push using Postman
- Download key-firebase-adminsdk-fbsvc-4aeee158f6.json (private key) from firebase console and run following in terminal
- Use printed token in firebase (valid for 1 hour only)

```
brew install --cask google-cloud-sdk
gcloud init
gcloud auth activate-service-account --key-file=key-firebase-adminsdk-fbsvc-4aeee158f6.json
gcloud auth print-access-token
```

- or simply use firebase auth in postman (authentic user with project access is required - valid for 1 hour only)
   
