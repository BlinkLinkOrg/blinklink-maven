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
- `com.blinklink.platform:*` — the [Compose fleet platform starters](https://github.com/BlinkLinkOrg/blinklink-platform-starters) (bom, service-parent, ddd-archetype, starter-fragments, starter-authz, starter-events, starter-telemetry); consumed as a Maven `<repository>` at this Pages URL
- `com.blinklink:blinklink-collector-ingest-client` — the [collector's server-side ingest client](https://github.com/BlinkLinkOrg/blinklink-service-collector-v5/tree/main/collector-ingest-client) (puts server-known events such as `compose.page.served` on `blinklink.collector.ingest.v1`); consumed as a Maven `<repository>` at this Pages URL
