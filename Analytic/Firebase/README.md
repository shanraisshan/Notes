# Firebase
firebase/ga4

# View Events of Production Apps (Realtime Analytics)
apps that are downloaded from store

1. Side menu -> Realtime Analytics
2. View user snapshot
3. Not 100% guarenteed, your user will appear


**ANDROID ONLY**
1. Download app from playstore
2. Connect your device and run ```adb shell setprop debug.firebase.analytics.app com.example.myapp```
3. Events will appear on debug view (make sure that proguard rules are setup in the app)

# View Events of Debug Production Apps (Debug View)
generate productionDebug app (isDebuggable=true)

1. Run on emulator
2. Your device will appear on Debug View under Debug Device
3. Live events will trigger on the console 
