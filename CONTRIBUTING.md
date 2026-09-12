# Contributing to Aether Launcher

Thanks for stopping by. This is a small solo-maintained fork (GrayDev), so the process is
deliberately lightweight.

## What this project is

An unofficial, offline-first fork of
[ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) for Android.
Upstream copyright notices must stay intact, and every fork modification must stay clearly
marked — see [LICENSE](LICENSE) (GPL-3.0).

## How to contribute

1. **Issues first** — bug reports, ideas, and questions go in
   [Issues](https://github.com/maybeagoodguy60-droid/AetherLauncher/issues).
   Include your device, Android version, app version, and steps to reproduce.
2. **Code lives on the fork branch for now** —
   [`graydev/zl3-offline`](https://github.com/maybeagoodguy60-droid/ZalithLauncher2/tree/graydev/zl3-offline).
   Open a PR against that branch (this repo will become the canonical home later).
3. **Keep the fork rules**:
   - Never remove upstream copyright/license headers.
   - Never use “ZalithLauncher” / “ZL” in new names (upstream GPLv3 name terms).
   - Keep the offline-first behavior and the self-hosted update feed intact.
   - Match the existing code style (Kotlin, Jetpack Compose).

## Building locally

```bash
git clone -b graydev/zl3-offline https://github.com/maybeagoodguy60-droid/ZalithLauncher2.git
```

Requirements: Android Studio (Bumblebee or newer), Android SDK
(min API 26, target API 34+), JDK 17. Open the project and build the
`ZalithLauncher` module (`assembleDebug -Darch=arm64` for a typical device).

## What we won't accept

- Changes that reintroduce mandatory Microsoft-account gating.
- Changes that phone home to upstream infrastructure.
- Proprietary or license-incompatible code.
