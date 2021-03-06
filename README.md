# RNTester

The RNTester showcases React Native views and modules.

## Running this app

Before running the app, make sure you ran:

    git clone https://github.com/facebook/react-native.git
    cd react-native
    npm install

### Running on iOS

Mac OS and Xcode are required.

- Open `RNTester/RNTester.xcodeproj` in Xcode
- Hit the Run button

See [Running on device](https://facebook.github.io/react-native/docs/running-on-device.html) if you want to use a physical device.

### Running on Android

You'll need to have all the [prerequisites](https://github.com/facebook/react-native/tree/master/ReactAndroid#prerequisites) (SDK, NDK) for Building React Native installed.

Start an Android emulator ([Genymotion](https://www.genymotion.com) is recommended).

    cd react-native
    ./gradlew :RNTester:android:app:installDebug
    ./packager/packager.sh

_Note: Building for the first time can take a while._

Open the RNTester app in your emulator.

See [Running on Device](https://facebook.github.io/react-native/docs/running-on-device.html) in case you want to use a physical device.

### Running with Buck

Follow the same setup as running with gradle.

Install Buck from [here](https://buckbuild.com/setup/install.html).

Run the following commands from the react-native folder:

    ./gradlew :ReactAndroid:packageReactNdkLibsForBuck
    buck fetch rntester
    buck install -r rntester
    ./packager/packager.sh

_Note: The native libs are still built using gradle. Full build with buck is coming soon(tm)._

### Running on Windows

Visual Studio 2015 or higher is required, with Windows 10 SDK 10.0.10586 or higher.

- Open `RNTester\RNTester.sln` in Visual Studio
- Set the StartUp project to `RNTesterApp`
- Press F5 or Start from Visual Studio

## Built from source

Building the app on iOS, Android and Windows means building the React Native framework from source. This way you're running the latest native and JS code the way you see it in your clone of the github repo.

This is different from apps created using `react-native init` which have a dependency on a specific version of React Native JS and native code, declared in a `package.json` file (and `build.gradle` for Android apps).
