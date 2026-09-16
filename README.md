# AltTab Community

This GPL-3.0 fork enables every locally implemented feature without a license key. It does not write mock license data or contact the upstream license API. Official Sparkle updates are disabled because installing an upstream binary would replace the community build.

Build locally:

```sh
scripts/codesign/setup_local.sh
DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer bash ai/build.sh
open "DerivedData/Build/Products/Debug/AltTab Community.app"
```

The fork uses the distinct bundle identifier `com.dbunk903.alt-tab-macos-community`, so it does not share preferences, permissions, login items, or Keychain records with the official app. Modified versions and redistributed binaries remain subject to GPL-3.0; keep the license and provide the corresponding source.

## Maintenance

Current baseline: upstream `v11.6.1`, Community version `11.6.1.1`.

To update, merge a reviewed upstream release tag into the Community branch, retain the
Community product identity and feature behavior, and increment `CURRENT_PROJECT_VERSION`.
Run the build and the complete test suite before replacing an installed app:

```sh
DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer xcodebuild test \
  -project alt-tab-macos.xcodeproj -scheme Test -configuration Debug \
  -derivedDataPath DerivedData
```

Keep the existing local signing certificate when rebuilding: changing the certificate
changes the designated requirement and can invalidate macOS privacy grants. Verify the
finished bundle with `codesign --verify --deep --strict`. Back up the installed bundle
and preferences before replacing it. Validate window discovery and switcher open/close
on an unlocked desktop; macOS can return no accessibility windows while locked.
Official automatic updates remain disabled, so new upstream releases require this
manual merge, test, build, and installation cycle.

## Upstream project

<div align="center">

<a href="https://alt-tab.app/"><img src="docs/readme/main.svg" alt="AltTab Pro — 7.4M downloads — 15K GitHub stars — Get AltTab"/></a>

<a href="https://jb.gg/OpenSource"><img src="docs/readme/sponsor.svg" alt="Sponsored by JetBrains" width="900"/></a>

</div>
