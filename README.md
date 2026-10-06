# Night Shift Physique

A personal gym split, desi no-supplement diet plan and daily tracker. Each person sets up their own profile (gender, age, height, weight, body type, goal, routine) and gets their own workout, calories, meal portions and meal times. Data stays on the phone.

This repo builds three things automatically with GitHub Actions, free:

| What | Workflow | Where to get it |
|---|---|---|
| Android app (.apk) | Build Android app | Releases page, every push to `main` |
| iOS app (.ipa, unsigned) | Build iOS app | Releases page, run it by hand from the Actions tab |
| Web app | Publish web app | `https://<your-username>.github.io/<repo-name>/` |

## One-time setup

1. **Signing key for Android.** Settings → Secrets and variables → Actions → New repository secret. Add `ANDROID_KEY_ALIAS`, `ANDROID_KEYSTORE_PASSWORD` and `ANDROID_KEYSTORE_BASE64` from your private `android-signing-secrets.txt`. Without them you still get an APK, but every update would need an uninstall, which wipes the logs.
2. **Web app.** Settings → Pages → Source: **GitHub Actions**.
3. **Run the builds.** Actions tab → pick a workflow → **Run workflow**.

## Installing

**Android:** open the Releases page on the phone, download `NightShiftPhysique.apk`, open it, and allow "Install unknown apps" for your browser when asked. Later builds install over the top and keep your data.

**iPhone:** Apple doesn't allow installing apps outside the App Store without signing. Options:
- **Free:** install the unsigned `.ipa` with [Sideloadly](https://sideloadly.io) or [AltStore](https://altstore.io) on a computer, using your Apple ID. A free Apple ID needs a re-install every 7 days.
- **Simplest:** open the web app link in Safari → Share → Add to Home Screen. It runs full screen with its own icon.
- **Paid:** an Apple Developer account ($99/year) for TestFlight or the App Store.

## Changing the app

Edit the files in `www/` (the whole app is `www/index.html`) and push to `main`. The Android build and web app update on their own.

Icons and splash screens come from `assets/`; replace those PNGs to rebrand.
