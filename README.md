# Conversations Demo Application Overview

## This is Kotlin version of the Demo app

For the Java version you can look [here](https://github.com/twilio/twilio-chat-demo-android/tree/java).

This demo app SDK version: ![](https://img.shields.io/badge/SDK%20version-1.0.0-blue.svg)

Latest available SDK version: [ ![Latest SDK version](https://api.bintray.com/packages/twilio/releases/conversations-android/images/download.svg) ](https://bintray.com/twilio/releases/conversations-android/_latestVersion)

## Getting Started

Welcome to the Conversations Demo application.  This application demonstrates a basic conversations client with the ability to create and join conversations, add other participants (chat, SMS, WhatsApp) into the conversations and exchange text and media messages.

What you'll minimally need to get started:

- A clone of this repository
- [A way to create a Chat Service Instance and generate client tokens](https://www.twilio.com/docs/api/chat/guides/identity)
- Google Play Services library : [Follow the instructions here](https://developers.google.com/android/guides/setup)

## Building

### Add google-services.json

[Generate google-services.json](https://developers.google.com/mobile/add) file and place it under `chat-demo-android/`.

### Set the value of `ACCESS_TOKEN_SERVICE_URL`

Set the value of `ACCESS_TOKEN_SERVICE_URL` in chat-demo-android/gradle.properties file to point to a valid Access-Token server.

Create that file if it doesn't exist with the following contents:

```
ACCESS_TOKEN_SERVICE_URL=http://example.com/get-token/
```

NOTE: no need for quotes around the URL, they will be added automatically.

You can also pass this parameter to gradle during build without need to create a properties file, as follows:

```
./gradlew assembleDebug -PACCESS_TOKEN_SERVICE_URL=http://example.com/get-token/
```

### Optionally setup Firebase Crashlytics

If you want to see crashes reported to crashlytics:
1. [Set up Crashlytics in the Firebase console](https://firebase.google.com/docs/crashlytics/get-started-new-sdk?platform=android&authuser=1#set-up-console)

2. In order to see native crashes symbolicated upload symbols into the Firebase console :
```
./gradlew chat-demo-android:assembleBUILD_VARIANT
./gradlew chat-demo-android:uploadCrashlyticsSymbolFileBUILD_VARIANT
```
for example to upload symbols for `debug` build type run:
```
./gradlew chat-demo-android:assembleDebug
./gradlew chat-demo-android:uploadCrashlyticsSymbolFileDebug
```

[Read more](https://firebase.google.cn/docs/crashlytics/ndk-reports-new-sdk) about Android NDK crash reports.

3. Login into `chat-demo-android` application and navigate to `Menu -> Options -> Simulate crash` in order to check that crashes coming into Firebase console.

### Build

Run `./gradlew assembleDebug` to fetch Twilio SDK files and build application.

### Android Studio

You can import this project into Android Studio if you so desire by selecting `Import Project (Eclipse ADT, Gradle, etc)` from the menu and then build using Studio's Build menu.

### Debug

Build in debug configuration, this will enable verbose logging.

## License

MIT
