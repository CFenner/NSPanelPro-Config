# NSPanelPro-Config

Based on the great work of Blakadder and others.

- https://blakadder.com/nspanel-pro/
- https://blakadder.com/nspanel-pro-sideload/
- https://blakadder.com/nspanel-pro-secrets/
- https://blakadder.com/android-panel-webview/

⚠️ Register the device with eWe Link app before activating the developer mode!!!

## Activating Android Debug Bridge

⚠️ You will not be able to run any updates after this so easily (see [nspanel_pro_roottool_apk](https://github.com/seaky/nspanel_pro_roottool_apk)), so do that first. E.g. ZigBee router mode requires v2.2.

- connect a USB cable to the device
- run `adb connect <ip>` and `adb tcpip 5555`

see https://blakadder.com/nspanel-pro-sideload/#disassembly

## Switch NSPanel to ZigBee router mode

⚠️ This resets the panel, so do that first.

⚠️ This required at least v2.2 of the eWe Link app. If you happen to have the adb active and a lower version, [this](https://github.com/seaky/nspanel_pro_roottool_apk) might help.

- Open the eWe Link app on the phone
- select the device (eweLinkController app needs to  be running on the panel)
- select settings via `...`
- select pilot functions
- select ZigBee mode
- activate `router mode`

Device will restart and will be reset. 

## Install Ultra Small Launcher

1. download [`ultra-small-launcher.apk`](https://blakadder.com/assets/files/ultra-small-launcher.apk)
2. run `adb install ~/Downloads/ultra-small-launcher.apk`
3. use launcher with `adb shell input keyevent 3`
4. select ultra small launcher

see https://blakadder.com/nspanel-pro-sideload/#install-a-launcher

## Enable Navigation Bar

1. open `settings`
2. select `display`
3. activate `show status bar`

see https://blakadder.com/nspanel-pro-sideload/#enable-navigation-bar

## Disable Startup Sounds

1. select `settings`
2. select `sound`
3. select `advanced`
4. disable `charging sounds`

see https://blakadder.com/nspanel-pro-secrets/#turn-off-startup-sound

## Enable Android Developer Settings

1. open `settings`
2. select `system`
3. select `about`
4. tab on `build number` till developer settings are activate (~7 times)

## Enable Day / Night Mode

tba

## Enable GPS

1. download https://de.softonic.com/download/fake-gps-location/android/post-download
2. run `adb install ~/Downloads/...`
3. open `settings`
4. select `system`
5. select `developer options`
6. under `debugging` select `app for simulated location`
7. select `Fake GPS`
8. open `Fake GPS` app and select your location

see https://blakadder.com/nspanel-pro-secrets/#mock-location
  https://fake-gps-location.de.softonic.com/android/download

## Install Home Assistant Companion App

1. download [`app-full-release.apk`](https://github.com/home-assistant/android/releases/latest/download/app-full-release.apk) from [latest release](https://github.com/home-assistant/android/releases/latest) 
2. run `adb install ~/Downloads/app-full-release.apk`

In the HA app settings you should activate `full screen mode` and `display always on`. Also disable *Home Assistant Cloud* to avoid getting *localhost* banned.

### Updating

From time to time the app should be updated.

1. download [`latest release`](https://github.com/home-assistant/android/releases/latest/download/app-full-release.apk)
1. run `adb connect <ip>`
1. run `adb install -r ~/Downloads/app-full-release.apk`

## Install NSPanel Pro Tools

1. download apk from https://github.com/seaky/nspanel_pro_tools_apk/releases/latest
2. run `adb install ~/Downloads/...`

see https://blakadder.com/nspanel-pro-secrets/#nspanel-pro-tools

## Change TTS Engine
 
1. download `Speech Services by Google arm64-v8a` from https://www.apkmirror.com/apk/google-inc/google-text-to-speech-engine/
2. run `adb install ~/Downloads/com.google.android.tts_googletts.google-speech-...`
1. change engine at `settings > bedienungshilfen > text-in-sprach-ausgabe`

Use notifications for TTS: https://companion.home-assistant.io/docs/notifications/notifications-basic/#text-to-speech-notifications

see https://blakadder.com/nspanel-pro-secrets/#upgrade-tts-voice

## Remove Unused Apps

1. ```
   adb shell pm uninstall --user 0 com.rockchip.devicetest
   adb shell pm uninstall --user 0 com.android.gl2jni
   adb shell pm uninstall --user 0 com.eWeLinkNSPro.dev
   adb shell pm uninstall --user 0 com.smatek.test
   adb shell pm uninstall --user 0 acr.browser.barebones
   adb shell pm uninstall --user 0 com.android.music
   adb shell pm uninstall --user 0 com.DeviceTest
   adb shell pm uninstall --user 0 com.cghs.stresstest
   ```

see https://blakadder.com/nspanel-pro-secrets/#debloat-apps
