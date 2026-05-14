# Caret for macOS

Public release channel for **Caret**, an agentic terminal for macOS.

- Latest release: https://github.com/caretagi/caretcode-desktop/releases/latest
- Sparkle appcast: https://github.com/caretagi/caretcode-desktop/releases/latest/download/appcast.xml

This repository only hosts notarized DMG builds and the Sparkle appcast.
Source lives in a separate repository.

## Install

1. Download the latest `Caret-<version>-<build>.dmg`.
2. Open the DMG and drag **Caret** to Applications.
3. Launch Caret. Auto-updates run in the background via Sparkle.

## Verifying a download

Each release is signed with the team's Developer ID Application certificate
(team `4T3ZXB8C4V`) and notarized + stapled by Apple. To verify locally:

```sh
spctl --assess --type open --context context:primary-signature -vv path/to/Caret-*.dmg
codesign --verify --deep --strict --verbose=2 /Applications/Caret.app
```

The corresponding Sparkle EdDSA signature is in the same release's
`appcast.xml`, and the running app verifies it before installing an update.
