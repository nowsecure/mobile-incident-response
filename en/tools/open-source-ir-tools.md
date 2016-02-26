<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
  <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
</div>

# List of mobile incident response tools

There are a number of open-source tools and distributions that can be used in investigating a mobile incident or during a forensic examination.  The use of advanced Linux forensic analysis tools can help an examiner locate crucial evidence in a more efficient manner. Some of these tools are very powerful and provide the capability to quickly index, search, and extract certain types of files.

The following is a list of open source and other freely distributed tools that are available either within the Santoku Linux distribution or elsewhere, broken down by the categories discussed earlier in this chapter. While we don't cover tools that can be used to help establish an efficient IR process, there are a few open source options listed in Meirwah's [Awesome Incident Response](https://github.com/meirwah/awesome-incident-response) repo (under the "Incident Management" section). 

The tools in the following section that have already been pre-installed within Santoku will be denoted by an "S", while others mentioned will need to be manually installed in the Santoku virtual machine (VM) that you've set up. Commercial tools will be briefly discussed at the end of this section.

## Continual analysis tools
[Vulnerability Test Suite (VTS) for Android](https://github.com/nowsecure/android-vts): Scans an Android device to detect known vulnerabilities. There are two types of vulnerability tests that can be performed:

* Detection only (does not attempt to exploit)
* Detects and attempts to exploit the vulnerability

[iVerify-oss](https://github.com/trailofbits/iverify-oss): Inspects an iOS device at boot-time to identify and collect information about any changes observed that may indicate the device has been modified by a jailbreak or other type of exploit.

[X-Ray](https://labs.duosecurity.com/xray): X-Ray allows you to scan your Android device for security vulnerabilities that put your device at risk. 


## Device and data acquisition tools
This process involves not only acquiring the data from the device but also ensuring that the forensic image you've collected matches the file signature of the original (more details on this in the "[Categories of Mobile IR Tools](../mobile-ir-tool-categories.md)" section). Below is a list of tools that can be used to perform the device acquisition process, verify an image, and collect network traffic (when appropriate).

### Device acquisition
* (S) AF Logical OSE: An open source tool that was released for use by non-law enforcement personnel or other individuals interested in Android forensics. It allows an examiner to extract logical data from an Android device through content providers. Here is a [HOWTO guide](https://santoku-linux.com/howto/howto-use-aflogical-ose-logical-forensics-android/) guide for this tool.
* (S) iPhone Backup Analyzer 2:  Allows user to browse content of iOS device made by an iTunes backup (or backup performed by another tool). More details on this tool can be found in it's [repo](https://github.com/PicciMario/iPhone-Backup-Analyzer-2); otherwise, you can find this tool in Santoku under the start menu -> Santoku -> Device Forensics -> iOS Backup Analyzer 2.
* (S) libimobiledevice: Cross-platform library that uses iOS specific protocols to recover data from the device's filesystem (no jailbreak required), perform a backup/restore, retrieve device information, and more. Here is a [HOWTO guide](https://santoku-linux.com/howto/mobile-forensics/howto-create-a-logical-backup-of-an-ios-device-using-libimobiledevice-on-santoku-linux/) for this tool. You will find the tool in Santoku under the start menu -> Santoku -> Device Forensics -> libimobiledevice.
* (S) dd:  The “dd” command can be used on a device on which the examiner has root access (e.g., a jailbroken iPhone or iPad). This tool is generally used in forensics to acquire a full disk image of a hard drive, SD card, USB flash drive, or other device.
* [FROST](https://www1.informatik.uni-erlangen.de/frost): A tool set that supports the forensic recovery of scrambled telephones. 
* [Lime](https://github.com/504ensicslabs/lime): Allows for the acquisition of volatile memory from Android and other Linux-based devices.

### Image verification 
The following two checksum commands can be used to generate a digital fingerprint of a file, and in forensics, can be used to show that a physical image is an exact replicate of the data on a device at a given time. This verification proves that no files or content have been changed.

* (S) md5sum
* (S) sha256sum

### Proxying network traffic
* [Charles Proxy](https://www.charlesproxy.com/): Charles is a proxy tool that allows the user to view requests, responses and HTTP headers for HTTP and SSL/HTTPS traffic.
* (S) [Burp Suite](https://portswigger.net/burp/):  A platform for security testing web applications, but it can also be used to assess the security of mobile app communications and web services. 
* (S) [ZAP](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project): Open source penetration testing tool for finding vulnerabilities in web applications.

## Analysis tools
### Forensic analysis
  * (S) Android Brute Force Encryption: This tool can help a forensic analyst crack the pin used to encrypt an Android device (this applies to Ice Cream Sandwich and Jelly Bean versions of the Android operating system).  Here is a [HOWTO guide](https://santoku-linux.com/howto/mobile-forensics/how-to-brute-force-android-encryption/) for this tool.
  * (S) scalpel:  A file carving utility that is used to recover deleted files from a forensic image of a device (mobile or not). It recovers these files by searching a disk image for that file type's unique header and footer.
  * (S) [Sleuthkit](http://www.sleuthkit.org/): Sleuthkit is a collection of command line tools and a C library that allows you to analyze disk images and recover files from them.
  * (S) strings:  Running this command line tool against any file will provide printable characters that are at least 4 characters long from the file. Strings can really be useful when trying to locate information within a large file, such as a forensic image of a device (which can exceed 16GB depending on the size of the device). It allows for quick and efficient searching when used in combination with the "grep" command.
  * (S) hexedit: No forensic investigation is complete without a hex editor. Hexedit is built into the Santoku VM and can be used to view or manipulate the binary data within a file.

### Network analysis
The following tools can be used to analyze captured network traffic:

* (S) [Wireshark](https://www.wireshark.org/): Wireshark is a network protocol analyzer and can be used for network troubleshooting and analysis. It can also be used to understand what type of data a mobile app is sending over the network unencrypted.
* (S) [Ettercap](https://ettercap.github.io/ettercap/) is a suite of tools that are used to perform various types of man-in-the-middle attacks. 
* (S) [Nmap](https://nmap.org/) scans a server to discover hosts and services on a network and create a map using this information. Specific features include port scanning, version detection, operating system detection, and scripted interaction with the target.
* (S) [Zenmap](https://nmap.org/zenmap/) (as root) allows a user to easily run an "NMAP" scan using a graphical user interface (GUI) making it easy for beginners to use, and it includes advanced features for more experienced users.
* (S) [Chaosreader](http://chaosreader.sourceforge.net/) can be run against captured network traffic and traces TCP and UDP sessions seeking application data.
* (S) [dnschef](http://thesprawl.org/projects/dnschef/) is a DNS proxy tool for penetration testers and malware analysts. It can be used to create fake requests for a specified URL/domain and point it to a local machine as opposed to its intended server.
* (S) [DSniff](http://www.monkey.org/~dugsong/dsniff/) is a collection of tools for network and penetration testing.
* (S) [mitmproxy](https://mitmproxy.org/) allows for the interception and analysis of network traffic.
* (S) [tcpdump](http://www.tcpdump.org/manpages/tcpdump.1.html) is a command line packet analyzer.
* (S) [wifite](https://github.com/derv82/wifite) is an automated tool that is used to attack multiple WEP, WPA, and WPS encrypted networks.

### Malware analysis
The following is a list of tools that can be used to reverse-engineer Android applications, decode resources and rebuild them after modification.

* (S) [Androguard](https://github.com/androguard/androguard) is a python tool used to reverse-engineer and perform malware analysis on Android mobile applications.
* (S) [APKTool](http://ibotpeaches.github.io/Apktool/) allows a user to reverse-engineer Android .apk files.
* (S) [Smali/Baksmali](https://github.com/JesusFreke/smali/wiki) is an assembler/disassembler for the dex format used by dalvik (Android's Java VM implementation).
* (S) [AntiLVL](http://androidcracking.blogspot.com/p/antilvl_01.html)can be used to test an Android developer's protection methods against common types of attacks. 
* (S) [Bulb Security SPF](https://github.com/georgiaw/Smartphone-Pentest-Framework) is a smartphone penetration testing framework used to assess the security of a mobile device. The tool offers various types of attacks such as remote, client-side, social engineering, and post exploitation attacks.
* (S) [dex2jar](https://github.com/pxb1988/dex2jar) converts .dex files to .class files (zipped up as .jar).
* (S) [Drozer](https://github.com/mwrlabs/drozer) is a security testing framework for Android. It allows the user to search for security vulnerabilities in apps and devices by assuming the role of an app and interacting with the Dalvik VM, other apps' IPC endpoints, and the underlying operating system.
* (S) [JD-GUI](https://github.com/java-decompiler/jd-gui) is a standalone graphical utility that displays Java sources from CLASS files.
* (S) [Procyon](https://bitbucket.org/mstrobel/procyon/) is a suite of Java meta-programming tools.
* (S) [radare2](http://radare.org/r/) is a multi-platform reversing framework that can be used to disassemble and assemble many different architectures, debug with local native and remote debuggers, and perform file system forensics and data carving, among other features.


## Commercial tools
While this section focuses on open-source software (OSS), commercial tools that can also assist in a mobile IR investigation are worth mentioning.

In addition to the list of OSS process/incident management tools that we linked to above, there are also commercial tools available such as [Resilient's Incident Response Platform](https://www.resilientsystems.com/). This can be used to help automate the IR process by integrating directly with other prevention and detection systems that are already in place. It helps teams track incidents and offers dashboards and reporting features to provide status updates to various groups.

### Continuous monitoring analysis
[NowSecure's Protect mobile application](https://www.nowsecure.com/protect/), when installed in advance of a mobile incident, can help establish a device, operating system, and app baseline. When used within an organization, it provides an administrative dashboard that can allow access to aggregated security scores, network data, and vulnerability analytics. In the event of an incident, this baseline data can be used to pinpoint what went wrong and when.

[zANTI](https://github.com/Zimperium/zanti_plugins): zANTI is a mobile penetration testing toolkit that lets security managers assess the risk level of a network.

### Device acquisition / analysis
Most commercial forensics tools offer device acquisition capabilities and also offer built-in analysis tools. A sample of these tools are listed here:

* [NowSecure Forensics](https://www.nowsecure.com/forensics/) (iOS / Android)
* [Cellebrite](http://www.cellebrite.com/Mobile-forensics)
* [XRY](https://www.msab.com/products/xry/)
* [Lantern](https://katanaforensics.com/products/)
