# React Native
most used hybrid platform for application building

# Key Points
1. When opening iOS react native project into Xcode, Go to Project->ios>select project.xcworkspace(white)
2. Opened a new proj in Xcode, In Targets->Signing & Capabilities->No Development Team selected (You cannot run on iOS Device)
3. Set Bundle Identifier, Sign in your account at XCode, and Auto certificate will appear
4. https://developer.apple.com/account/resources/identifiers/list = bundle identifier will appear here within a day

# Issues in Implementation

## [Bottom Tab Navigator](https://reactnavigation.org/docs/bottom-tab-navigator/)
1. ```npm install``` doesn't include following in Android + iOS, need to add this manually
2. Android app/build.gradle
```
apply from: "../../node_modules/react-native-vector-icons/fonts.gradle"
```
3. iOS Info.plist 
```
<key>UIAppFonts</key>
<array>
    <string>Ionicons.ttf</string>
</array>
```
