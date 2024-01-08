# NSPanelPro-Config

Based on the great work of Blakadder and others.

- https://blakadder.com/nspanel-pro/
- https://blakadder.com/nspanel-pro-sideload/
- https://blakadder.com/nspanel-pro-secrets/
- https://blakadder.com/android-panel-webview/

# Basics

1. activate `adb` via cable & activate remote control
  1. see https://blakadder.com/nspanel-pro-sideload/#disassembly
  2. run `adb connect <ip>` and `adb tcpip 5555`
1. set NSPanel in Zigbee router mode (ewe Link app) ⚠️ will reset the panel and all settings, do that first!
1. install ultra small launcher
  1. see https://blakadder.com/nspanel-pro-sideload/#install-a-launcher
  2. run `adb install ultra-small-launcher.apk`
  3. use launcher with `adb shell input keyevent 3`
1. navigation bar https://blakadder.com/nspanel-pro-sideload/#enable-navigation-bar

2. https://de.softonic.com/download/fake-gps-location/android/post-download
   https://fake-gps-location.de.softonic.com/android/download
   
1. install Home Assistant companion
  1. download apk from [latest release](https://github.com/home-assistant/android/releases): https://github.com/home-assistant/android/releases/latest/download/app-full-release.apk
  2. run `adb install app-full-release.apk`
1. install nspanel pro tools https://blakadder.com/nspanel-pro-secrets/#nspanel-pro-tools
  1. download
1. mock location https://blakadder.com/nspanel-pro-secrets/#mock-location

# Nice to Have

1. change tts https://blakadder.com/nspanel-pro-secrets/#upgrade-tts-voice
2. https://companion.home-assistant.io/docs/notifications/notifications-basic/#text-to-speech-notifications
1. startup sound https://blakadder.com/nspanel-pro-secrets/#turn-off-startup-sound


# Cleanup

1. uninstall unused apps https://blakadder.com/nspanel-pro-secrets/#debloat-apps
2. ´adb shell pm uninstall --user 0 com.android.gl2jni´
1. ```
   adb shell pm uninstall --user 0 com.rockchip.devicetest
   adb shell pm uninstall --user 0 com.android.gl2jni
   adb shell pm uninstall --user 0 com.eWeLinkNSPro.dev
   ```
