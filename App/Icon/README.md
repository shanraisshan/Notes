# Icon

## ANDROID

### [Adaptive Icon](https://developer.android.com/develop/ui/views/launch/icon_design_adaptive) | User Theming

In the following scenarios, the home screen doesn't display the themed app icon on Android 13 (API level 33), and instead displays the adaptive or standard app icon:

1. If the user doesn't enable themed app icons.
2. If your app doesn't provide a monochromatic app icon.
3. If the launcher doesn't support themed app icons.

### Turn On (Mobile)
Unlock Developer Options | Go to Settings>Wallpaper & style | Toggle Themed icons ON

### Development
1. Convert your app icon png to svg using https://www.freeconvert.com/png-to-svg
2. Include in Android Studio. Goto drawable folder>Right Click>New Vector Asset>Select icon.svg>Rename to ic_launcher_monochrome
3. This will be generated under drawable folder, include in anydpi-v26/ic_launcher.xml as ```<monochrome android:drawable="@drawable/ic_launcher_monochrome" />```



## GENERATE
https://easyappicon.com/
