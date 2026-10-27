# Steerradar Android Studio Project (JDK 27)

Android WebView app that opens https://shr1varakala.github.io/Steerradar/

## Versions
- Gradle JVM: **JDK 27** (select your installed `openjdk-27` in Android Studio)
- Gradle distribution: **9.8.0** (Java 27 support begins in Gradle 9.8)
- Android Gradle Plugin: **9.4.0**
- Android SDK Platform / compileSdk: **35**
- Java source/target compatibility: **17** (intentional: Android bytecode compatibility)
- Application ID: `com.steerradar.mobile`

## Open project
1. Extract the ZIP and **File > Open** the **SteerradarAndroid** folder (contains `settings.gradle`, `app/`).
2. In **File > Settings > Build, Execution, Deployment > Build Tools > Gradle** select `openjdk-27`.
3. Sync Gradle. The `app` module should appear after successful sync.
4. Run > Edit Configurations > Android App > Module: `app` > Launch: Default Activity.
5. Select a device and Run, or Build > Build Bundle(s) / APK(s) > Build APK(s).
6. Debug APK is written to `app/build/outputs/apk/debug/app-debug.apk`.

## Gradle wrapper limitation
`gradle/wrapper/gradle-wrapper.properties` is included, but the wrapper JAR is not bundled because this environment cannot download it. **Do not run `./gradlew` yet**. Install Gradle 9.8.0 locally, configure Android Studio to use that Gradle installation if prompted, or use the included GitHub Actions workflow which installs Gradle 9.8.0 automatically. Once Gradle is available, generate wrapper files with `gradle wrapper --gradle-version 9.8.0`.

## GitHub Actions
Push the Android project files to a repository. Open Actions > Build Android APK > Run workflow; download the artifact. This workflow uses Java 27 and Gradle 9.8.0.

## Limitations
An APK was **not** compiled or tested here. AGP 9.4/Gradle 9.8/JDK 27 compatibility needs local confirmation during sync/build. Java 27 *source and target* is intentionally not configured. This WebView wrapper requires internet, and native Web Bluetooth is not implemented. WebRTC/microphone/camera permissions are not enabled by default.
