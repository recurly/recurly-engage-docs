---
title: Android
excerpt: >-
  Configuration guide for the Recurly Engage Android SDK, enabling native prompt
  display and usage tracking in your mobile and TV apps.
deprecated: false
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

The Recurly Engage Android SDK supports mobile, tablet, and TV devices. The latest SDK version and example app source code are available [here](https://github.com/redfast/redfast-sdk-android/releases). Contact your Customer Success Manager for access keys to run the example.

### Gradle/Maven configuration

**Gradle**

```gradle
// settings.gradle
dependencyResolutionManagement {
  repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
  repositories {
    mavenCentral()
    maven { url 'https://jitpack.io' }
  }
}

// dependencies
dependencies {
  amazonImplementation("com.github.redfast.redfast-sdk-android-build:redfast-sdk-amazon:v2.2.1.3")
  googleImplementation("com.github.redfast.redfast-sdk-android-build:redfast-sdk-google:v2.2.1.3")
}
```

**Maven**

```xml
<!-- pom.xml -->
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>
<dependencies>
  <dependency>
    <groupId>com.github.redfast.redfast-sdk-android-build</groupId>
    <artifactId>redfast-sdk-google</artifactId> <!-- or redfast-sdk-amazon -->
    <version>v2.2.1.3</version>
  </dependency>
</dependencies>
```

### Local package

1. **Download** the latest `.aar` files from [here](https://github.com/redfast/redfast-sdk-android/releases).

2. **Create** a `libs` folder under `src/main`.

3. **Add** the `.aar` libraries to the `libs` folder.

4. **Add** them as dependencies in `build.gradle`:

   ```gradle
   implementation(files("src/main/libs/redfast-google-release.aar"))
   implementation(files("src/main/libs/redfast-amazon-release.aar"))
   ```

5. For Google IAP support, **also add**:

   ```gradle
   implementation("com.android.billingclient:billing:6.0.1")
   implementation("com.android.billingclient:billing-ktx:6.0.1")
   ```

6. **Enable** viewBinding and dataBinding:

   ```gradle
   buildFeatures {
     viewBinding = true
     dataBinding = true
   }
   ```

## Initialize Recurly Engage

In your app’s main activity or Application class, initialize the SDK with your AppID and UserID (found under **Settings > Application** in Pulse):

```kotlin
PromotionManager.initPromotion("[Your AppID]", "[Your UserID]")
```

## Trigger popup via screen name

In your activity or fragment’s `onCreate`:

```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    PromotionManager.setScreenName(binding.root, "HomeScreen") {
        when (it.code) {
            PromotionResult.timerExpired,
            PromotionResult.declined,
            PromotionResult.abort,
            PromotionResult.accepted -> {
                // handle each case
            }
            else -> { }
        }
    }
}
```

## Trigger popup via button click

```kotlin
PromotionManager.getTriggerablePrompts(
    screenName = "home",
    clickId = "click_purchase",
    type = PathType.MODAL
) { prompts ->
    prompts.firstOrNull()?.let { prompt ->
        PromotionManager.showModal(prompt.id, requireContext()) { result ->
            when (result.code) {
                PromotionResult.accepted,
                PromotionResult.declined,
                PromotionResult.timerExpired,
                PromotionResult.abort -> {
                    // handle each case
                }
                else -> { }
            }
        }
    }
}
```

## Retrieve inline prompts

```kotlin
PromotionManager.getTriggerablePrompts("ScreenName", "ClickId") { prompts ->
    prompts.firstOrNull()?.let { prompt ->
        // Access properties
        prompt.impression()
        prompt.dismiss()
        prompt.decline()
        prompt.timeout()
        prompt.holdout()
        prompt.click()
        prompt.click2()
    }
}
```

## Deep link to a media asset

Configure deep links in Pulse. Access them via callbacks for `setScreenName`, `buttonClick`, or `getTriggerablePrompts`.

## Access custom metadata

Decode custom metadata:

```kotlin
val meta = prompt.deviceMeta?.decodeValue(Meta::class.java)
```

## Send usage tracking event

```kotlin
PromotionManager.customTrack("[customTrackId]")
```

## Set UserId

Update the user ID mid-session:

```kotlin
PromotionManager.setUserId("[New UserID]")
```

## Debug view

Show the debug modal:

```kotlin
PromotionManager.showDebugView(this)
```

## External libraries

```text
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
```text
Google IAP:
  com.android.billingclient:billing:6.0.1
  com.android.billingclient:billing-ktx:6.0.1

Amazon IAP:
  amazon/in-app-purchasing-2.0.76.jar
```
```
Google IAP: 
    com.android.billingclient:billing:6.0.1
    com.android.billingclient:billing-ktx:6.0.1
    
Amazon IAP:
    amazon/in-app-purchasing-2.0.76.jar
```