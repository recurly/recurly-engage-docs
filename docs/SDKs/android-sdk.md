---
title: Android (Deprecated)
excerpt: >-
  Configuration guide for the Recurly Engage Android SDK, enabling native prompt
  display and usage tracking in your mobile and TV apps.
deprecated: true
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The **Recurly Engage Android SDK** provides support for Android phones, tablets, TVs, Fire Tablets, and Fire TV. The SDK automatically handles display of modals (popups, video popups, and banners) and related user-triggered events. Inline prompts are accessible via helper functions with the necessary metadata for rendering within chosen areas of the app.

# Key benefits

* **SDK integration**: Seamlessly embed prompts and track events across Android form factors.
* **Automatic UI handling**: Built-in support for modals, banners, and inline prompts without manual UI code.
* **Broad device support**: One SDK for phones, tablets, and TV devices.

# Key details

The Recurly Engage Android SDK brings the ability to monitor consumption and show configured prompts within your native Android apps.

## Install the SDK

The Engage Android SDK includes support for mobile, tablet and TV devices. The latest SDK version as well as the source code of an example app is available [here](https://github.com/redfast/redfast-sdk-android/releases). Please reach out to your customer success manager if you would like the keys needed to run the example app.

There are two options with installing the SDK: Add a dependency to an existing Gradle/Maven config, or add the local SDK packages.

### Gradle/Maven Config

**Gradle**

```java
// settings.gradle
dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
    mavenCentral()
    maven { url 'https://jitpack.io' }
  }
}

// dependency
dependencies {
  // amazon devices with inapp billing support
  "amazonImplementation"("com.github.redfast.redfast-sdk-android-build:redfast-sdk-amazon:v2.3.0")

  // google devices with inapp billing support
  "googleImplementation"("com.github.redfast.redfast-sdk-android-build:redfast-sdk-google:v2.3.0"

  // google devices without inapp billing support
  "noiapImplementation"("com.github.redfast.redfast-sdk-android-build:redfast-sdk-noiap:v2.3.0")

  // google devices without inapp and push support
  "coreImplementation"("com.github.redfast.redfast-sdk-android-build:redfast-sdk-core:v2.3.0")

}
```

**Maven**

```java
// Maven pom.xml
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>

// dependency
<dependency>
  <groupId>com.github.redfast.redfast-sdk-android-build</groupId>
  <artifactId>redfast-sdk-google</artifactId> // or redfast-sdk-amazon, redfast-sdk-noiap, redfast-sdk-core
  <version>v2.3.0</version>
</dependency>
```

### Local package

**Steps:**

1. Download the latest .aar files from [here](https://github.com/redfast/redfast-sdk-android/releases)
2. Create folder “libs” under “src/main”
3. Add .aar libraries to “libs” folder
4. Add library as a dependency in “build.gradle”. Example:

```kotlin
"implementation"(files("src/main/libs/redfast-google-release.aar"))
"implementation"(files("src/main/libs/redfast-amazon-release.aar"))
```

4. For the`google-sdk.aar`library, it is also required to add the Android billing library dependency. Example:

```kotlin
"implementation"("com.android.billingclient:billing:6.0.1")
"implementation"("com.android.billingclient:billing-ktx:6.0.1")
```

5. Enable the following features in `build.gradle`:

```kotlin Kotlin
buildFeatures {
  viewBinding = true
  dataBinding = true
}
```

## Initialize Engage

In the your app's main activity or application file, add the following line and replace with your appID and the userID of the current user. The appID is available on the Settings > Application screen within Pulse.

```kotlin Kotlin
PromotionManager.initPromotion([appID], [userID])
```

## Trigger popup via screen name

Allow the Engage SDK to display a popup on a specific Screen Name. Add the following line in the activity or fragment's onCreate function:

```kotlin
override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
  ...
  PromotionManager.setScreenName(binding.root, "ViewController") {
        when (it.code) { // PromotionResult
          ...
        }
    }
}

// PromotionResult:
//   val code: PromotionResultCode,
//   val value: deeplink,
//   val meta: metadata

// PromotionResultCode:
//   timeout,
//   declined,
//   abort,
//   accepted,
//   notApplicable,
//   notSupported,
//   disabled,
//   holdout,
//   button1, // User clicked button 1 (primary button, used in both modal and inline)
//   button2, // User clicked button 2 (secondary button, modal only)
//   button3, // User clicked button 3 (tertiary button, modal only)
//   dismiss // User dismissed the modal/inline (available for both modal and inline)

```

## Trigger popup via button click

Allow the Recurly Engage SDK to display a popup configured with a Screen Name and Click ID. Add the following line in the button's click handler:

```kotlin
PromotionManager.getTriggerablePrompts(screenName = "home", clickId = "clickId", type = PathType.MODAL) {
  val item = it.asList().firstOrNull()
  item?.let { prompt ->
    PromotionManager.showModal(promptId = prompt.id, requireContext()) {
      Log.d("HomeFragment", "${it.code}")
    }
  }
}
```

## Retrieve inline prompts

The SDK provides a function to retrieve a collection of inline items that are configured to trigger based on a Screen Name and/or Click ID. The properties of each Prompt object may be used to render the inline prompt in the appropriate location.

```kotlin
PromotionManager.getTriggerablePrompts("ScreenName", "ClickId") { prompts ->
  prompts.firstOrNull()?.let {
    /* Inline Prompt Image - based on device settings, one of:
      rf_settings_bg_image_android_os_fire_tv_composite
      rf_settings_bg_image_android_os_tablet_composite
      rf_settings_bg_image_android_os_phone_composite
    */
    val bgImage = it.bgImage
    // Device Metadata - rf_metadata
    val deviceMeta = it.deviceMeta
    // Deeplink - rf_settings_deeplink
    val deeplink  = it.deeplink
    // Confirm Button Color - rf_retention_confirm_button_text_color
    val button1Color = it.button1Color
    // Second Button Color - rf_retention_confirm_button_2_text_color
    val button2Color = it.button2Color
    // Cancel Button Color - rf_retention_cancel_button_text_color
    val button3Color = it.button3Color
    // All of the properties related to Timer
    // rf_settings_close_seconds
    val timerSeconds = it.timerSeconds
    // rf_settings_close_seconds
    val timerText = it.timerText
    // rf_settings_timer_font_size
    val timerTextFontSize = it.timerTextFontSize
    // rf_settings_timer_font_color
    val timerTextFontColor = it.timerTextFontColor
    // All of the properties
    val properties = it.properties
 
    // Following methods will report the interaction to Redfast:
    // Invoke when inline prompt is shown to user
    it.impression()
    // Invoke when user dismisses prompt
    it.dismiss()
    // Invoke when user declines prompt (Button 3)
    it.decline()
    // Invoke when timerSeconds expire and prompt is dismissed
    it.timeout()
    // Invoke if the "holdout" property is "true". This is normally automatically invoked.
    it.holdout()
    // Invoke when Button 1 is pressed
    it.click()
    // Invoke when Button 2 is pressed
    it.click2()
  }
}
```

## Deep link to a media asset

You can insert deeplink key-value pairs in Pulse. When the user invokes the CTA, you can utilize these key-value pairs to send the user to a specific media asset within the app.

The deeplink value is saved in the completion callback from your `setScreenName`, `buttonClick`, and `getInlines`

## Access custom metadata

Custom key-value pairs can be added to an item via Pulse. These values may be used to perform an action that is not the typical media asset deep link, like sending the user to a registration screen.

The meta data json is saved in the completion callback from your `setScreenName`, `buttonClick`, and `getInlines`

## Send usage tracking event

Use this to send custom events using the SDK. If configured as a tracker within Pulse, these custom events can be used to target prompts at specific sets of users.

```kotlin
PromotionManager.customTrack("[customTrackId]")
```

## Set UserId

You may change the userid after the SDK has been initialized, for example, when the user authenticates mid session. Note that it may take several seconds for the user's prompts to refresh.

```kotlin
PromotionManager.setUserId("[New userID]")
```

## Debug view

The SDK provides a debug view modal, in which you can use the onscreen keyboard to either reset the current user or set a new user id.

To trigger the debug view for a specific screen, you can call the `PromotionManager.showDebugView` function.

## External libraries

Common

```
    com.squareup.moshi:moshi-kotlin:1.9.2
    com.squareup.moshi:moshi-kotlin-codegen:1.9.2
    com.squareup.retrofit2:retrofit:2.6.2
    com.squareup.retrofit2:converter-moshi:2.6.2
    com.squareup.okhttp3:okhttp:4.2.2
    com.squareup.okhttp3:logging-interceptor:4.2.2
    org.jetbrains.kotlinx:kotlinx-coroutines-android:1.7.1
    org.jetbrains.kotlinx:kotlinx-coroutines-core:1.7.1
    com.github.bumptech.glide:glide:4.16.0
    com.google.code.gson:gson:2.8.9
```

Conditional

```
Google IAP: 
    com.android.billingclient:billing:6.0.1
    com.android.billingclient:billing-ktx:6.0.1
    
Amazon IAP:
    amazon/in-app-purchasing-2.0.76.jar
```

<br />