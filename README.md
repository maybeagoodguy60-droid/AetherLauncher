<div align="center">

# ⚡😤 Aether Launcher (AL)

**Minecraft: Java Edition on Android — your accounts .. your rules.**

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Android%208.0%2B-3DDC84?logo=android&logoColor=white)](https://github.com/maybeagoodguy60-droid/AetherLauncher)
[![Version](https://img.shields.io/badge/version-3.0.0-orange.svg)](https://github.com/maybeagoodguy60-droid/AetherLauncher)
[![Status](https://img.shields.io/badge/status-unofficial%20fork-yellow.svg)](https://github.com/maybeagoodguy60-droid/AetherLauncher)
[![Issues](https://img.shields.io/github/issues/maybeagoodguy60-droid/AetherLauncher.svg)](https://github.com/maybeagoodguy60-droid/AetherLauncher/issues)

![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-4285F4?logo=jetpackcompose&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?logo=gradle&logoColor=white)
![JNI](https://img.shields.io/badge/JNI-C%2FC%2B%2B-8A2BE2.svg)

> [!WARNING]
> **Unofficial modified build.** Aether Launcher is a community fork and is **not affiliated with,
> endorsed by, or connected to** the ZalithLauncher2 authors. If you want the official app,
> get [ZalithLauncher2](https://github.com/ZalithLauncher/ZalithLauncher2) instead — seriously,
> it's excellent, and this fork wouldn't exist without it.

</div>

## Why does this fork exist?

Stock launchers increasingly tie *playing a game you own* to *being logged into a vendor account*.
Aether exists for one stubborn idea: **if the game can run offline, the launcher should let it.**
No Microsoft account. No gatekeeping. Your device, your accounts, your call.

Everything else — the name, the IDs, the update feed — follows from keeping that promise
without stepping on upstream's toes.

## Features

- 🔓 **Offline-first accounts** — offline and third-party (authlib-style) accounts always work.
  Microsoft login still exists, purely optional. Nobody is locked out for not having one.
- 🆔 **Clean coexistence** — application ID `org.graydev.aetherlauncher` installs next to stock
  ZalithLauncher2 with zero signature conflicts. Try both, keep whichever you like.
- 📡 **Self-hosted updates** — the in-app updater talks only to GrayDev-controlled endpoints.
  No silent instructions from anyone else's server, ever.
- 🔏 **Independently signed** — release builds carry their own GrayDev key and are minified
  to stock-like sizes (~170 MB arm64).
- 🎨 **Same launcher you know** — full ZalithLauncher2 feature set underneath: versions, mods,
  controls, renderers, plugins. Nothing ripped out.

## Under the hood

| Layer | Technology |
|---|---|
| UI | Kotlin + Jetpack Compose + Material Design 3 |
| Game bootstrap | PojavLauncher-derived core (upstream) |
| Native bridges | C via JNI/NDK (GL/EGL/OSMesa context bridges) |
| Auth | Microsoft (OAuth device flow), offline UUID, third-party Yggdrasil servers |
| Build | Gradle Kotlin DSL, per-ABI splits, R8 minification on release |
| Min SDK / Target | Android 8.0 (API 26) / API 34 |

By file count the codebase is ~55% Kotlin UI/app code, with Java interop and a compact C
layer where the JVM meets the GPU. If you want the full tour, the code lives on the
[fork branch](https://github.com/maybeagoodguy60-droid/ZalithLauncher2/tree/graydev/zl3-offline)
until it moves here.

## Honest notes — read before installing

- **No public release yet.** Anything floating around is a CI debug artifact, not a release.
  Debug builds are unminified, debuggable, and carry a `.debug` app ID — fine for testing,
  not what am to ship or anything again am working on this solo 😅.
- **This is a one-maintainer fork.** GrayDev builds and signs it; there are no other
  contributors yet, no QA team, no SLA. Bug reports are genuinely welcome
  ([Issues](https://github.com/maybeagoodguy60-droid/AetherLauncher/issues)) — that's how this gets better.
- **Minecraft itself is still Mojang's.** This launcher doesn't include the game and doesn't
  change how offline/online servers validate you. Servers in online-mode still need a real account;
  that's Mojang's rule, not ours, and no launcher can (or should) bypass it.
- **Update checks are quiet by design.** Until a release is published, the updater reports
  “already latest.” That's intentional, not broken.

## Project layout

- **This repo** — project home: docs, license, releases (when published).
- **Code development** — currently on the
  [`graydev/zl3-offline`](https://github.com/maybeagoodguy60-droid/ZalithLauncher2/tree/graydev/zl3-offline)
  branch of the fork; this repo becomes the canonical home when the code moves over.
- **Update data** — [`AetherLauncher-Info`](https://github.com/maybeagoodguy60-droid/AetherLauncher-Info).

## Building

```bash
git clone -b graydev/zl3-offline https://github.com/maybeagoodguy60-droid/ZalithLauncher2.git
# Open in Android Studio (Bumblebee+, JDK 17) and build the ZalithLauncher module.
# See CONTRIBUTING.md for the full notes.
```

## Contributing

Small project, simple rules — [CONTRIBUTING.md](CONTRIBUTING.md).
Security reports: [SECURITY.md](SECURITY.md).

## Acknowledgements

- **MovTery and all ZalithLauncher2 contributors** — authors of the upstream project.
  Upstream copyright notices are preserved throughout the code; go star them.
- The **PojavLauncher team**, respect to these guys.
- **HMCL**, from which parts of the auth logic originate (credited in-source).
- Every translator contributing through upstream Web late. 😁 

## License

**GNU General Public License v3.0** — [LICENSE](LICENSE).
Upstream copyright retained; fork modifications marked. If you redistribute a build of this,
the same rules apply to you — that's the deal that keeps all of this open.


## Activity

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/maybeagoodguy60-droid/AetherLauncher/output/github-contribution-grid-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/maybeagoodguy60-droid/AetherLauncher/output/github-contribution-grid-snake.svg">
  <img alt="Contribution graph snake animation" src="https://raw.githubusercontent.com/maybeagoodguy60-droid/AetherLauncher/output/github-contribution-grid-snake.svg">
</picture>
