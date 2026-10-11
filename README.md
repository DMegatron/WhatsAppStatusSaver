# WhatsApp Status Saver (Android)

Native Kotlin Android app with a home-screen widget. It reads status media only from a folder the user explicitly selects, then copies selected images/videos to the device's public `Pictures/WhatsApp Statuses` collection.

## Build without Android Studio (GitHub Actions)

This project includes `.github/workflows/build-apk.yml`, which builds the APK in GitHub's cloud runners.

1. Sign in to GitHub and create a new **public** repository (for example `WhatsAppStatusSaver`). Public repositories allow Actions to run without needing a paid plan.
2. Upload the contents of this ZIP to the repository's root. Make sure `app/`, `build.gradle.kts`, `settings.gradle.kts`, and `.github/` are at the root, not nested inside another folder. GitHub's web interface supports **Add file → Upload files**.
3. Open the repository's **Actions** tab. Select **Build Android APK**, then **Run workflow** if it has not started automatically.
4. Wait for the workflow to finish successfully. Open the completed run and download the `WhatsAppStatusSaver-debug-apk` artifact.
5. Extract the downloaded artifact ZIP on your phone and tap `app-debug.apk` to install. Android may ask you to allow installation from that browser/file manager.

Keep in mind that a public repository makes the source code public. Do not upload secrets or personal data.

## Android storage limitation

On current Android versions, apps generally cannot silently read WhatsApp's private or restricted folders. On first launch, choose WhatsApp's `.Statuses` folder using Android's Storage Access Framework. If it is hidden, enable **Show hidden files** in the picker's menu. WhatsApp may store statuses in different locations depending on its version and device. This app does not bypass Android's access controls.

## Use

1. Install the app and open it.
2. Tap **Choose WhatsApp Status Folder** and select the `.Statuses` folder.
3. Tap **Refresh**, select one or more entries, then tap **Save selected**. **Save all** is also available.
4. Add the **Status Saver** widget from your launcher's Widgets menu. Tapping it opens the app.

Saved files are copied to `Pictures/WhatsApp Statuses` and are visible to gallery apps. The app doesn't upload files or require a WhatsApp login.
