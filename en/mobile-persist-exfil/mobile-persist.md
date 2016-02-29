# Mobile Persist

This section discusses mechanisms that provide an adversary a persistent presence on a device.

From @dw's [spreadsheet](https://docs.google.com/spreadsheets/d/1_LU0FG2unZpIwQsjXIhqi8TF-uYul0PYQOEctvICXyI/edit#gid=1944709954), adapted from a MITRE document.

## Device startup

Configuring a program to run when the device starts.

### Android

#### native code
- add to init script

#### runtime
- use `BOOT_COMPLETED` broadcast message

### iOS
- launchd plist files
- voip app background type

