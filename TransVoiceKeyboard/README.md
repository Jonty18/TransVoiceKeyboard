# TransVoice Keyboard 1.0.2

A custom Android IME focused on multilingual voice-to-text translation.

## Build the APK with GitHub Actions

This repository includes `.github/workflows/build-apk.yml`. GitHub Actions supplies the Java, Gradle and Android SDK build environment.

### 1. Create a GitHub repository
1. Sign in to GitHub.
2. Create a new repository, for example `TransVoiceKeyboard`.
3. Keep it empty when creating it (do not add another README).

### 2. Upload this project
Upload the **contents** of this folder so that `settings.gradle`, `build.gradle`, `.github/`, and `app/` are at the repository root.

### 3. Run the build
Open **Actions → Build TransVoice Keyboard APK → Run workflow**.

The workflow builds `app-debug.apk` and uploads it as an artifact named `transvoice-keyboard-debug-apk`.

### 4. Download the APK
Open the completed workflow run, scroll to **Artifacts**, and download `transvoice-keyboard-debug-apk`. Extract it and install `app-debug.apk` on your Android phone.

## Android requirements
- minSdk: 23
- targetSdk: 35
- compileSdk: 35
- Java: 17
- Android Gradle Plugin: 8.7.3
- Gradle: 8.9 (provided by GitHub Actions)
- ML Kit Translation: 17.0.3

## Translation languages
The language selector is restricted to languages currently listed by Google's ML Kit Translation documentation. The current project selection includes English, Tamil, Hindi, Telugu, Kannada, Bengali, Marathi, Gujarati, Chinese, Arabic, Portuguese, Russian, Indonesian, Korean, and Spanish. Malayalam and Punjabi are intentionally not listed because they are not in ML Kit Translation's current supported-language table.

ML Kit translation models are downloaded on demand. The first translation for a language pair may therefore require network access; subsequent translation can use the downloaded on-device model.

## Important voice-input note
Speech recognition is provided by Android's speech-recognition service and its available locales depend on the device/provider. Translation-language support and speech-recognition-language support are separate things.

## Project status
This package is **GitHub-build-ready source**, not a precompiled APK. The APK should be treated as verified only after the GitHub Actions build succeeds and the resulting APK is installed and tested on a real Android device.
