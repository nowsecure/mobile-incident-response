# Android Incident Response

This chapter will provide a step-by-step technical approach for responding to an Android incident. We will discuss Android security mechanisms, a tailored incident response process and a lab exercise you can complete. THe sections include:

* Android Security Model
* Android Incident Response Process
* Android Data Collection
* Android Incident Response Analysis
* Android Incident Response Lab Exercise

# Android Security Model

In this section we provide a quick overview of the Android security model.

## Access control

Android's security model has multiple dimensions including a solid foundation inherited from a Linux heritage.

Each application can be launched with its own user identifier (UID) and group identifier (GID), which allows for traditional discretionary access control (DAC) mechanisms as in most Linux systems.

The Linux capabilities system further distributes the privileges of a superuser into distinct units.

Android additionally supports mandatory access control (MAC) through Security Enhancements For Android™ (SE for Android). This mechanism enforces policies that act as a "sandbox" for Android applications.

The runtime permission model grants permissions to resources available to apps running in the managed runtimes, e.g., [Dalvik and ART](https://source.android.com/devices/tech/dalvik/).

## Application signing

## Application Distribution Channels

Android has a very open ecosystem compared to Apple. There are multiple markets with applications, everywhere from Google's Play Store to various third-party markets.

According to Google on [How Users Understand Third-Party Applications](https://source.android.com/devices/tech/security/overview/app-security.html#how-users-understand-third-party-applications):

> Android strives to make it clear to users when they are interacting with third-party applications and inform the user of the capabilities those applications have. Prior to installation of any application, the user is shown a clear message about the different permissions the application is requesting. After install, the user is not prompted again to confirm any permissions.

Therefore, a few minor configuration tweaks, and without rooting the device, third-party applications can be readily installed to the device or "side-loaded." Unlike Apple, Android devices have multiple opportunities for customization by the OEM and carriers. Therefore, devices may come with pre-installed third-party application distribution channels in addition to Google Play. 


### Google Play

The Google Play (originally the Google Play Store) is the official distribution channel operated by Google for Android devices.

Only devices that pass the [Compatibility Test Suite](http://source.android.com/compatibility/cts/index.html) are officially allowed access to Google Play. There are numerous tutorials online, however, that can assist users with installing the Play Store.

### Third-party markets
We make no attempt to enumerate all third-party markets here. 

We'll highlight a few differences between some popular third-party markets and the official Play Store.

