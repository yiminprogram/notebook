# ADB COMMAND

ADB(Android Debug Bridge) command

- `adb connect <ip>`  
  connect to device

- `adb shell pm list packages`  
  list all packages

- `adb shell pm clear <package name>`  
  clear app data

- `adb shell dumpsys package <package>`  
  list package info

- `adb shell am start -n <package>/<activity>`  
  start app

- `adb push <file> <path>`  
  push file to device

- `adb shell am start -a android.settings.APPLICATION_SETTINGS`  
  open system settings

- `adb shell am start -a com.android.settings.APPLICATION_DEVELOPMENT_SETTINGS`
  open developer settings

- `adb shell am force-stop <package>`  
  force stop app

- `adb shell pm clear <package>`  
  clear app data

- `adb uninstall <package>`  
  uninstall app

- `adb shell screencap -p /sdcard/image.png`  
  screen capture

- `adb pull /sdcard/image.png D:/test/`  
  pull file
