# SilverFox InControl – releases

Public download location for the SilverFox InControl Android app. The app reads
`version.json` from this repo (`main` branch) and offers an update when its
`versionCode` is higher than the installed one.

## Publishing a new version

1. In the app repo, bump `versionCode` and `versionName` in `app/build.gradle.kts`
   (`versionCode = major*100 + minor`, e.g. 0.6 → 6, 1.0 → 100).
2. Build a signed release APK with the **same signing key** as before
   (Android refuses to install an update signed with a different key).
3. Create a GitHub Release here with tag `InControl-X.Y` and attach the APK named
   `InControl_X.Y.apk`. The release must be **published**, not a draft.
4. Update `version.json` (versionCode, versionName, url, notes) and commit to `main`.

Apps notice the new version the next time they are opened
(raw.githubusercontent.com may cache `version.json` for a few minutes).
