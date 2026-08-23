# AltTab Community

This GPL-3.0 fork enables every locally implemented feature without a license key. It does not write mock license data or contact the upstream license API. Official Sparkle updates are disabled because installing an upstream binary would replace the community build.

Build locally:

```sh
scripts/codesign/setup_local.sh
ai/build.sh
open "DerivedData/Build/Products/Debug/AltTab Community.app"
```

The fork uses the distinct bundle identifier `com.dbunk903.alt-tab-macos-community`, so it does not share preferences, permissions, login items, or Keychain records with the official app. Modified versions and redistributed binaries remain subject to GPL-3.0; keep the license and provide the corresponding source.

## Upstream project

<div align="center">

<a href="https://alt-tab.app/"><img src="docs/readme/main.svg" alt="AltTab Pro — 7.4M downloads — 15K GitHub stars — Get AltTab"/></a>

<a href="https://jb.gg/OpenSource"><img src="docs/readme/sponsor.svg" alt="Sponsored by JetBrains" width="900"/></a>

</div>
