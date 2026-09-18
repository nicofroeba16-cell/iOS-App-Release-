# iOS Next — SideStore Distribution

This public repository contains distribution metadata and GitHub Releases for **iOS Next** only.

The private application source code is maintained separately and is not published here. No credentials, Apple signing material, provisioning profiles, tokens, private configuration, or internal development data belong in this repository.

## SideStore source

Raw source URL:

`https://raw.githubusercontent.com/nicofroeba16-cell/iOS-App-Release-/main/source.json`

SideStore deep link:

`sidestore://source?url=https%3A%2F%2Fraw.githubusercontent.com%2Fnicofroeba16-cell%2FiOS-App-Release-%2Fmain%2Fsource.json`

## App identity

- App: iOS Next
- Bundle Identifier: `de.nicofroeba16.iosnext`
- Source Identifier: `de.nicofroeba16.iosnext.source`
- Current published version: none yet
- Expected release asset name: `IOSNext-Free-unsigned.ipa`

## Publishing updates

Intended release flow:

1. Build `IOSNext-Free-unsigned.ipa` from the private iOS App repository.
2. Verify that the IPA is the explicitly approved current build.
3. Create a GitHub Release in this repository.
4. Upload the IPA as a GitHub Release asset — never store the IPA binary in Git history.
5. Record the exact IPA byte size.
6. Add the new version to the beginning of the app's `versions` array in `source.json`, preserving older versions.
7. Commit the updated `source.json`.
8. SideStore discovers the new release through the stable raw source URL.

No IPA release is published until an approved artifact is available.