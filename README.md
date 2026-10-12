# STANDOFF TOOL — Android project

Native Java Android app targeting Android 9 (minSdk 28). No account, backend, or external library dependencies.

## Implemented
- Four tabs: Resolution, Crosshair, Presets, Settings.
- Native overlay service (`TYPE_APPLICATION_OVERLAY`) drawing Cross/Dot/Circle/T crosshair.
- Overlay permission flow and stop button; overlay window uses `FLAG_NOT_TOUCHABLE` to avoid intercepting game touches.
- Local SharedPreferences settings and JSON presets: create, apply, rename, delete, persist across app restarts.
- Resolution profiles 16:9, 4:3, 16:10, Custom are stored honestly as profiles; no fake system-resolution application.
- Accent choices and reset/clear actions.

## Important limitations
- The project has not been tested on a physical Honor 20 Pro. Some games/firmware may hide overlays or stop the service.
- The resolution profiles do not change Standoff 2's actual rendering or aspect ratio. Changing that reliably generally needs supported in-game settings or privileged tooling (e.g. ADB/root), which this app does not claim to provide.
- After changing a preset while overlay is already running, stop and start the overlay again to reload drawing parameters.
- This source archive is not an APK. Build it using AndroidIDE or another Android Gradle environment.

## Build on Android phone with AndroidIDE
1. Install AndroidIDE from its official distribution/source and open it.
2. Download/extract this ZIP on the phone, then choose **Open project** and select the `STANDOFF-TOOL` folder (the folder containing `settings.gradle`).
3. Allow AndroidIDE to install/configure its JDK and Android SDK components. Use JDK 17 if offered; Android Gradle Plugin 8.6.1 requires JDK 17 or newer. Install Android SDK Platform 35 and build tools when prompted.
4. Sync Gradle. If the app requests a Gradle wrapper, let AndroidIDE create/download Gradle 8.7 for AGP 8.6.1.
5. Run **assembleDebug** or tap Run. The debug APK is normally at `app/build/outputs/apk/debug/app-debug.apk`.
6. Install the generated APK. If Android asks, allow installation from the file manager/AndroidIDE.

## Install and enable overlay
1. Install and open STANDOFF TOOL.
2. Open **Crosshair** and configure shape/color/size/thickness/gap/opacity.
3. Tap **Запустить плавающий прицел**. Android opens the special access screen.
4. Enable **Allow display over other apps** for STANDOFF TOOL and return to the app.
5. Tap launch again. Stop it with **Отключить плавающий прицел**.

## Troubleshooting
- If overlay does not appear: check Android Settings → Apps → Special app access → Display over other apps. Some Honor battery-management settings may stop background services; do not claim guaranteed visibility in every game.
- If AndroidIDE sync fails, check that SDK Platform 35, build tools, internet access, and JDK 17+ are installed. The build has not been executed in the authoring environment because Android SDK/Gradle are not installed there.
