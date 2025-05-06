# iOS
iOS related stuff

## ■ XCODE
Download Xcode from [stackoverflow](https://stackoverflow.com/questions/10335747/how-to-download-xcode-dmg-or-xip-file)


## ■ CERTIFICATES (.p8 vs .p12/.pem)
### Apns Auth Key vs Apns Auth Certificate 
using an APNS authentication key (.p8 file) or a provider certificate (.p12/.pem file). The .p8 key method is recommended because it doesn’t expire and can be used for multiple apps under the same Apple Developer account.

### Creating .cer -> .p12 -> .pem (.pem is required by MoEngage Push Notification)
1) Log in to the Apple Developer Portal, go to "Certificates, Identifiers & Profiles," create a new APNs certificate for sandbox under your app’s identifier, and download the .cer file.
2) Import the .cer file into Keychain Access by dragging it into the app or using: security import certificate.cer -k ~/Library/Keychains/login.keychain. In Keychain Access, find the certificate, right-click, and export it as a .p12 file (set a password).
3) Open Terminal and use OpenSSL to convert the .p12 file to .pem: ```openssl pkcs12 -in push_cert.p12 -out push_cert.pem -nodes``` (-legacy | in the end if required). Enter the .p12 password if prompted. The certificate_key.pem file contains the certificate and private key for sandbox push notifications.

## ■ IDS
### App ID [[->]](https://developer.apple.com/help/account/manage-identifiers/register-an-app-id)

An **App ID** is a string used to identify one or more apps from a single development team. The string consists of two parts, the **Team ID** and the **bundle ID** separated by a period (.). The Team ID is supplied by Apple, while the bundle ID is supplied by the developer.

https://savyour.com/.well-known/apple-app-site-association

        "appIDs": [
          "T5H73HWLMW.com.disrupt.savyour"
        ],


### Apple (app store) ID [[->]](https://developer.apple.com/help/app-store-connect/reference/app-information/#:~:text=Apple%20ID)

https://apps.apple.com/pk/app/savyour-cashback-discounts/id1237114277

https://appstoreconnect.apple.com/apps/1237114277/distribution

## ■ WEBSITES

- https://appstoreconnect.apple.com/

- https://developer.apple.com/account/resources/certificates/list


