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
