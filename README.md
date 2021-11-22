## Android on TinkerEdgeR

###1. Download android image from [Asus web page](https://tinker-board.asus.com/download-list.html). At the time, it was Android 9 (1.0.6)

###2. Flash it:
- If flashing for first time, follow [instructions](https://tinker-board.asus.com/doc_er.html#Flashing_the_Tinker_Edge_R)
- Having Debian already installed:
`adb restart bootloader`

### 3. Download apps from [APKMirror](https://www.apkmirror.com/):
- [Google Account Manager, "gsf.login"](https://www.apkmirror.com/apk/google-inc/google-account-manager/google-account-manager-7-1-2-release/google-account-manager-7-1-2-android-apk-download/)
- [Google Services Framework, "gsf"](https://www.apkmirror.com/apk/google-inc/google-services-framework/google-services-framework-9-6794505-release/google-services-framework-9-6794505-android-apk-download/)
- [Google play Services, "gms"](https://www.apkmirror.com/apk/google-inc/google-play-services/google-play-services-21-21-16-release/google-play-services-21-21-16-100400-378233385-android-apk-download/)
- [Google Play Store, "vending"](https://www.apkmirror.com/apk/google-inc/google-play-store/google-play-store-25-9-19-release/google-play-store-25-9-19-21-0-pr-380694501-2-android-apk-download/)

### 4. Upload apps to device:
`adb root`  
`adb remount`  
`for x in *apk; do adb push $x /system/priv-app; done`

### More useful commands:
`adb logcat`  
`adb shell pm clear com.android.browser`  
`adb shell 'pm list packages -f' | sed -e 's/.*=//' | sort`
