# Slowpage 1.1 – build the Android APK

Read or listen to any book in small daily parts. This folder is a ready-to-build Android app.

## Easiest way: build the APK online (no Android Studio needed)
1. Create a free GitHub account and a new empty repository (for example `slowpage`).
2. Upload everything in this folder to the repository (keep the `.github` folder).
3. Open the repository's **Actions** tab. The "Build Android APK" job starts by itself (or press **Run workflow**).
4. After about 5 to 8 minutes, open the finished run and download **slowpage-apk** at the bottom. Unzip it to get `app-debug.apk`.
5. Copy the APK to your phone, open it, and allow "Install unknown apps" when Android asks.

## Build on your own computer instead
Needs Node 20+, Java 17 and Android Studio (for the Android SDK).
```
npm install
npm run prep
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
The APK appears in `android/app/build/outputs/apk/debug/app-debug.apk`.

## Compatibility
- Works on Android 5.1 and newer (API 22+), on phones and tablets, 32-bit and 64-bit.
- Needs "Android System WebView" (updated through Google Play). Very old, never-updated phones may show an old WebView; updating it fixes that.
- PDF and EPUB readers and a native text-to-speech voice are bundled, so importing books and listening work offline.

## Without an APK
`www/index.html` also runs as an installable web app: host the `www` folder on any HTTPS site, open it in Chrome on your phone and choose **Add to Home screen**.
