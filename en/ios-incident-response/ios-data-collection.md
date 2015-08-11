# iOS Data Collection

A key part of iOS Incident Response is collecting data. Responding to an incident is very similar to putting Humpty Dumpty back together again! The more historical information you have about the device the better. To maximize the probability of success and minimize the time and cost involved, a key success factors include:

* Historical device data
* Timely collection of device data after incident

# collecting artifacts

** from Android Chapter so need to update **

* package listings with file paths, e.g., `adb shell pm list packages *f > packages.txt`
* obtain getprop e.g., `adb shell getprop > props.txt`
* extract recent access points
* obtain historical network connections if available in logs
* idea: automate the above with a "census" taker app?
* obtain `adb shell dmesg` listing to look for idiosyncrasies of odd kernel behaviors
* obtain last kmesg if possible (after kernel panic) `adb pull /dev/last_kmsg`
* dontpanic files, `/data/dontpanic`
