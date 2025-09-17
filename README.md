# NaBotA
## Setup android for VSCode
- Export Vars
    - `export ANDROID_SDK_ROOT="/home/YourUsername/Android/sdk"`
    - `export PATH=$PATH:$ANDROID_SDK_ROOT/emulator`
    - `export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools`
    - `export PATH=$PATH:$ANDROID_SDK_ROOT/tools`
    - `export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin`
- Emulator
    - List
        - `emulator -list-avds`
    - Run
        - `emulator @EmulatorName`

## Build and Run Android Application on Ubuntu
- Build 
    - `./gradlew build`
    - `./gradlew assembleDebug --offline -q --console=plain`
- Install
    - `adb install -r app/build/outputs/apk/debug/app-debug.apk`
- Run in Debug Mode
    - `adb shell am start -D -n "sh.navid.nabot/.MainActivity"`
- Show all debug logs
    - `adb logcat *:D`
- Filter
    - By package name
        `adb logcat sh.navid.nabot:D *:S`
    - Or by a specific tag your app uses (e.g. MyAppTag)
        `adb logcat -s MyAppTag:D`