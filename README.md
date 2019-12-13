DALi Android JNI
================

This uses the new [Android Studio CMake plugin](http://tools.android.com/tech-docs/external-c-builds) with C++ support.
For how to use Android Studio, refer to [Android Studio CMake](https://codelabs.developers.google.com/codelabs/android-studio-cmake/index.html)

Pre-requisites
--------------
- Android Studio with [NDK](https://developer.android.com/ndk/) bundle.

Getting Started
---------------
You can skip 1 - 4 steps by cloning only dali-view-android and dali-view-example repos in dali folder and running dali-view-android/build.sh to clone and build everything for you automatically!
1. Download [Android Studio](http://developer.android.com/sdk/index.html).
   * Choose Linux (64-bit) version of on Linux.
   * Extract Studio in path/to/studio.
   * Run: path/to/studio/android-studio/bin/studio.sh.
   * Install SDK in path/to/sdk.
   * Choose standard installation, leave default components checked, download.
2. Install the Android NDK:
   * In the Android studio window, go to *Configure* -> *SDK Manager*, check Android SDK Location: path/to/sdk. You will use this for the ANDROID_SDK environment variable later on.
   * Download Android NDK following instructions in the [Download the NDK and Tools](https://developer.android.com/ndk/guides#download-ndk) section only.
   * Once installed, note the NDK path for the environment variable later on. path/to/ndk is the folder containing ndk-build. Usually, it is path/to/sdk/ndk-bundle.
3. Create a folder called **dali** and then change to that folder. Currently, it is important that you call it **dali**.
4. Clone the following repos in this folder from https://github.com/dalihub/:
   * **dali-core**, checkout branch **devel/master**.
   * **dali-adaptor**, checkout branch **devel/master**.
   * **dali-toolkit**, checkout branch **devel/master**.
   * **android-dependencies**, checkout branch **master**.
   * **dali-view-android**, checkout branch **master**.
   * **dali-view-example**, checkout branch **master**.
5. Optional. Update dali-view-example/local.properties
   ```
   sdk.dir=path/to/sdk
   ndk.dir=path/to/ndk
   ```
7. If you have a proxy update dali-view-example/gradle.properties
   ```
   #http proxy setup
   systemProp.http.proxyHost=<proxy host>
   systemProp.http.proxyPort=<proxy port>

   #https proxy setup
   systemProp.https.proxyHost=<proxy host>
   systemProp.https.proxyPort=<proxy port>
   ```
8. Launch the studio after setting the enviroment variables: path/to/studio/android-studio/bin/studio.sh.
   * Import project from dali/dali-view-example folder using AndroidStudio.
   * Select *File* -> *New* -> *New Module* -> *Import .JAR/.ARR Package* and choose *dali-view-android/daliview/build/outputs/aar/daliview-release.aar*. It will add daliview library to your project.
     Right click on *app* in Project view and choose *Open Module Settings*. Select your application module (*app*) and choose *Dependencies*. Select and add daliview module.
   * Choose *Make Project*. Should build the application.

