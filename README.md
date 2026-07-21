# Blinklink Maven repository

Interim Maven repository for Blinklink Android artifacts, served via GitHub
Pages (until they reach Maven Central).

Usage (`settings.gradle.kts`):

```kotlin
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven { url = uri("https://blinklinkorg.github.io/blinklink-maven") }
    }
}
```

Artifacts:

- `com.blinklink:blinklink-feed` — the [Blinklink Feed SDK for Android](https://github.com/BlinkLinkOrg/blinklink-feed-android)
