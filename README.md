# CRomAppWhitelist
Quick setting to add your app to whitelist for Chinese Android ROM

#### Reason to create this project

Because the open of Android ecosystem and the absence of Google services in Chinese market, the Android ROM manufatured by Chinese company has a big different with the others in other part of the world.

They are deeply customized Android, when your application run on this devices, you barely know what strange behavoirs will bring to your app. These restriction can let some of the features of your app are unfunctional, it's unfriendly from the users perspectives. Here I give several examples

* app is been kill after screen off, in order to save battery
* app don't allow notification before Android 6.0
* app's service with `Service.START_STICKY` not restart after the service kill

If your app is not covering thousands and millions of users, like `Wechat`, your app is not on the whiltelist of the phone manufacture. So the only way is telling the user and guide them to add your app to the whiltelist, if your app's main features rely on some features which are disable by the ROMs.

#### How to use

```java
   AppWhitelist.settingForAutoStart(this);
   AppWhitelist.settingForBatterySaver(this);
   AppWhitelist.settingForMemoryAcceleration(this);
   AppWhitelist.settingForNotification(this);
```
Will guide the user (with a `Intent` to start the `Activity`) to setting and add to the whiltelist if the device has these features.

The component name of these activities usually obtained with the following command which run in the device shell

```sh
$ dumpsys activity activities |grep Focused
```

Currently tested devices

* Xiaomi
* Meizu
* Samsung
* Oppo
* Huawei

Patches for more devices are welcome!
