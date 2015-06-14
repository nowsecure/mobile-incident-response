# Android Incident Response

This chapter will provide you:

* Specific steps to do Android IR case 
* HOWTO step by step example
* Lab Exercise (image and data to be downloaded from NS website)

ideas below


# high level
- distinguish between pre-root vs post-root incident response steps
- knowledge of prior configuration information helpful -- e.g., was device already rooted before incident
- develop a decision tree
- decide early, is goal legal action vs experiment conditions (e.g., honey potting).
- ideally try to decide/conclude whether the malicious software is still present or has been removed, if theory is that it has been removed, what artifacts might be left behind
- need to constantly track current rooting landscape. what privilege escalation exploits are currently available, what is the model of the attacker
- modeling the attacker
  - are we talking about a spouse spying or nation state?

# collecting artifacts
- package listings with file paths, e.g., `adb shell pm list packages -f > packages.txt`
- obtain getprop e.g., `adb shell getprop > props.txt`
- extract recent access points
- obtain historical network connections if available in logs
- idea: automate the above with a "census" taker app?
- obtain `adb shell dmesg` listing to look for idiosyncrasies of odd kernel behaviors
- obtain last kmesg if possible (after kernel panic) `adb pull /dev/last_kmsg`
- dontpanic files, `/data/dontpanic`

# device integrity
- looking for device integrity violations
  - easier to do when you have crowd-sourced data about system files (checksums, package listings, etc), apps that come pre-installed.
- could the incident have occurred due to OEM installed, or other factory installed software
- look for blown fuses or other tells?


