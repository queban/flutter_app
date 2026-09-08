# Flutter Rapp

A basic Flutter counter app, set up to produce a release APK build via GitHub Actions.

## How the build works

`android/`, `ios/`, and other platform folders are not committed — the CI workflow
generates them on the fly with `flutter create . --platforms=android`, then builds
the app. This keeps the repo small while still producing a real, installable build.

On every push to `main` (or via manual "Run workflow"), [.github/workflows/build.yml](.github/workflows/build.yml)
builds a release APK and uploads it as a workflow artifact named `app-release-apk`.
Download it from the run's **Summary** page under **Artifacts**.

## Local development (optional)

Requires the [Flutter SDK](https://docs.flutter.dev/get-started/install).

```
flutter create . --platforms=android   # first time only, generates android/
flutter pub get
flutter run
```
