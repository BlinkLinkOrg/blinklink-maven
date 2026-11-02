# blinklink-maven — agent notes

A Maven repository served by GitHub Pages: the platform starters, the spec artifacts, the collector's ingest client
and the Android feed SDK. What is published is the `com/blinklink/` tree itself (`README.md` lists the main
artifacts). Writers:
- `blinklink-platform-starters/scripts/publish.sh`: commits `com.blinklink.platform:* <version>`.
- `blinklink-platform-spec/scripts/publish-spec.sh` (the module repos reuse it): commits
  `com.blinklink.platform:<artifactId> <version>`.
- `blinklink-feed-android/scripts/publish-maven.sh`: commits `com.blinklink:blinklink-feed:<version>` and pushes
  without pulling first, so pull here before running it.
- The collector's ingest client (`com.blinklink:blinklink-collector-ingest-client`) is deployed from its own repo and
  committed by hand.

## Rules of the repo

- **A published version is immutable.** Never edit, move or delete a version directory; a change is a new version.
- Finishing a publish that stopped half-done by hand: only `maven-metadata.xml` files may be modified, and every new
  path must be a fresh version directory.
- Top-level docs (`README.md`, `CLAUDE.md`) are edited by hand; keep the README's artifact list in step when a new
  artifact appears.

## Ship

The publish scripts commit and push to `main` themselves. A hand commit (docs, a finished publish) goes to `main`
after review (`/ship`).
