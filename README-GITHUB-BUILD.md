# Build APK with GitHub Actions (phone-only)

1. Open your GitHub repository `Neon-Toolkit` in the phone browser.
2. Upload the **contents** of this project folder to the repository root. The root should directly contain `settings.gradle`, `build.gradle`, `gradle.properties`, `app/`, and `.github/`. Do not upload the outer `STANDOFF-TOOL` folder as an extra nested folder.
3. Commit the files to the `main` branch (or `master`). The workflow starts automatically after a push. You can also open the **Actions** tab, select **Build STANDOFF TOOL APK**, tap **Run workflow**, and confirm.
4. Open the workflow run and wait for the green check mark. If it fails, open the failed step and copy/screenshot the error.
5. On the successful run, scroll to **Artifacts** and download `standoff-tool-debug-apk`. GitHub downloads it as a ZIP; extract it on the phone to get `app-debug.apk`.
6. Install `app-debug.apk`. Android may ask you to allow installation from the browser or file manager.

The workflow builds a debug APK. It does not mean the app has been tested on a physical device. Do not share a public repository if you want to keep your source code private.
