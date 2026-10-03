# Doomsplay Android WebView wrapper

This Android Studio project loads the existing live Next.js site at `https://doomsplay.in/` in a full-screen Android WebView. It includes Android Back navigation, HTML5 video support, and immersive fullscreen video controls.

## Build an APK on Windows

1. Install **Android Studio** (stable release) from https://developer.android.com/studio.
2. Extract this project ZIP to a normal folder, for example `C:\Projects\DoomsplayAndroid`.
3. Open Android Studio → **Open** → choose the `DoomsplayAndroid` folder (the folder containing `settings.gradle.kts`).
4. Accept the Gradle sync prompts. If Android Studio asks to install Android SDK Platform 35 or Build Tools, install them from **Tools → SDK Manager**.
5. Wait for Gradle sync to finish. Connect your Android phone with USB debugging enabled, or start an emulator.
6. To test directly, press the green **Run ▶** button and select your phone.
7. To create an APK: **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
8. When the build finishes, click **locate** in the notification. The debug APK is normally at `app\build\outputs\apk\debug\app-debug.apk`. Transfer it to your phone and open it to install. You may need to allow installation from that file manager.

## Important notes

- The app is a wrapper; the Next.js website and its API routes must remain deployed and reachable over HTTPS.
- This project starts at `https://doomsplay.in/`. If your actual canonical site uses `www` or a different domain, update the URL in `MainActivity.kt`.
- The WebView allows HTTPS/HTTP page navigation to remain inside the app to support embedded video players. Only use streaming sources and content you are authorized to access and distribute.
- Video providers may block WebView, require cookies, DRM, or unsupported codecs. Test every playback source on a real Android phone; WebView cannot bypass provider restrictions.
- This is a debug-build starter. For a release APK, use **Build → Generate Signed App Bundle or APK** and keep the signing key private.
