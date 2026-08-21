# Brick Game 999 — Native Android Wrapper

## Files in this bundle
- `app/src/main/AndroidManifest.xml` — vibration permission + fullscreen theme
- `app/src/main/res/layout/activity_main.xml` — fullscreen WebView layout
- `app/src/main/java/com/retro/brickgame/MainActivity.kt` — WebView setup, immersive mode, native vibration bridge
- `app/src/main/assets/index.html` — your game page (currently a placeholder — replace with your real game HTML/JS/CSS)

## Setup Steps (Android Studio)
1. Create a new project: **File → New → New Project → Empty Views Activity**, language = **Kotlin**, package name = `com.retro.brickgame`.
2. Copy `AndroidManifest.xml` into `app/src/main/`, replacing the generated one.
3. Copy `activity_main.xml` into `app/src/main/res/layout/`, replacing the generated one.
4. Copy `MainActivity.kt` into `app/src/main/java/com/retro/brickgame/`, replacing the generated one.
5. Create an `assets` folder: right-click `app/src/main` → **New → Folder → Assets Folder**. Copy `index.html` (and any game JS/CSS/images) into it.
6. Build the APK: **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
7. Find the generated APK under `app/build/outputs/apk/debug/`.

## Notes
- Replace the placeholder canvas code in `index.html` with your actual game logic. Keep the `triggerVibrate(ms)` function — call it whenever you want a vibration (e.g. on collision, score, game over).
- The bridge exposes `AndroidNative.vibrate(ms)` to JavaScript automatically; `triggerVibrate()` already wires this up with a fallback to the browser's own vibration API for testing outside the app.
