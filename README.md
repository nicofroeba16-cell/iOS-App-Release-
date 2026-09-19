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
6. Read the GitHub Release `published_at` timestamp and write it to the new `source.json` version entry as `YYYY-MM-DDTHH:MM:SS` in UTC. Never publish a new version with a date-only `YYYY-MM-DD` value.
7. Add the new version to the beginning of the app's `versions` array, preserving older versions.
8. Validate that the newest version timestamp is not later than the GitHub Release `published_at` timestamp and is not in the future.
9. Commit the updated `source.json`.
10. SideStore discovers the new release through the stable raw source URL.

SideStore treats timed release values as UTC. The feed must use the exact GitHub Release publication time rather than a calendar date; otherwise a date-only value can become an unintended midnight-UTC countdown.

No IPA release is published until an approved artifact is available.
