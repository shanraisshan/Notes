# Palm Store
transsion - palm store

# Claiming App
https://dev.transsion.com/doc/en/console/applicationClaim/

## App Signing Process
1) open cmd (as admininstrator)
2) ```cd C:\Program Files\Java\jdk-20\bin``` (jar signer)
3) ```jarsigner -verbose -keystore F:\Download\palm-store\savyour_keystore.jks -signedjar F:\Download\palm-store\devSignVerify\app-release-signed.apk F:\Download\palm-store\devSignVerify\app-release-unsigned.apk savyour```
4) enter password (Signing ✓)
5) to verify -> ```keytool -printcert -jarfile F:\Download\palm-store\devSignVerify\app-release-signed.apk```

