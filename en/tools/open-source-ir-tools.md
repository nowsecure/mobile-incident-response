# List of Tools

There are a number of open-source tools and distros that can be used during a mobile incident or during a forensic examination process.  The use of advanced Linux forensic analysis tools can help an examiner locate crucial evidence in a more efficient manner. Some of these tools are very powerful and provide the capability to quickly index, search, and extract certain types of files.

The following is a list of open source and other freely distributed tools that are available either within the Santoku Linux distro or elsewhere, broken down by the categories discussed earlier in this chapter. While we don't cover tools that can be used to help establish an efficient IR process, there are a few open source options listed in Meirwah's [Awesome Incident Response](https://github.com/meirwah/awesome-incident-response) repo (under the "Incident Management" section). 

The tools in the following section that have already been pre-installed within Santoku will be denoted by an "S", while others mentioned will need to be manually installed in the Santoku VM that you've set up. Commercial tools will be briefly discussed in the section that follows.

## Continual Analysis
[Android Vulnerability Test Suite (VTS)](https://github.com/nowsecure/android-vts): Scans an Android mobile device to detect known vulnerabilities. There are two types of vulnerability tests that can be performed:
* Detection only (does not attempt to exploit)
* Detects and attempts to exploit the vulnerability

[iVerify-oss](): Inspects an iOS device at boot-time to identify and collect information about any any changes observed that may indicate the device has been modified by a jailbreak or other type of exploit.

[X-Ray](https://labs.duosecurity.com/xray): X-Ray allows you to scan your Android device for security vulnerabilities that put your device at risk. 


## Device and Data Acquisition
This process involves not only acquiring the data from the device, but also ensuring that the forensic image you've collected matches the file signature of the original (more details on this in the "[Categories of Mobile IR Tools](../mobile-ir-tool-categories.md)" section). Below are tools that can be used to perform the device acquisition process, as well as a set of tools to collect network traffic, if appropriate.

### Device Acquisition
* (S) AF Logical OSE: An open source tool that was released for use by non-law enforcement personnel or other individuals interested in Android forensics. It allows an examiner to extract logical data from an Android device through content providers. Here is a [HOWTO](https://santoku-linux.com/howto/howto-use-aflogical-ose-logical-forensics-android/) guide for this tool.
* (S) iPhone Backup Analyzer 2:  Allows user to browse content of iOS device made by an iTunes backup (or backup performed by another tool). More details on this tool can be found in it's [repo]()https://github.com/PicciMario/iPhone-Backup-Analyzer-2); otherwise, you can find this tool in Santoku under the start menu >> Santoku >> Device Forensics >> iOS Backup Analyzer 2.
* (S) libimobiledevice: Cross-platform library that uses iOS specific protocols to recover data from the device's filesystem (no jailbreak required), perform a backup/restore, retrieve device information, and more. Here is a [HOWTO guide](https://santoku-linux.com/howto/mobile-forensics/howto-create-a-logical-backup-of-an-ios-device-using-libimobiledevice-on-santoku-linux/) for this tool, and can be found in Santoku under the start menu >> Santoku >> Device Forensics >> libimobiledevice.
* (S) dd:  The “dd” command can be used on a device where the examiner has root access, such as a jailbroken iPhone or iPad. This tool is generally used in forensics to acquire a full disk image of a hard drive, SD card, USB flash drive, or other device.
* FROST
* LiME

### Image Verification: 
* (S) md5sum
* (S) sha256sum

### Proxying network traffic
* [Charles Proxy](https://www.charlesproxy.com/): Charles is an proxy tool that allows the user to view requests, responses and HTTP headers for HTTP and SSL/HTTPS traffic. 
* (S) [Burp Suite](https://portswigger.net/burp/):  A platform for security testing web applications, but can also be used to assess the security of mobile app communications and web services. 
* (S) [ZAP](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project): Open source penetration testing tool for finding vulnerabilities in web applications.

## Analysis
### Forensic Analysis
  * (S) Android Brute Force Encryption: Can help a forensic analyst crack the pin used to encrypt an Android device (this applies to Ice Cream Sandwich and Jelly Bean OS versions).  Here is a [HOWTO guide](https://santoku-linux.com/howto/mobile-forensics/how-to-brute-force-android-encryption/) for this tool.
  * (S) scalpel:  A file carving utility that is used to recover deleted files from a forensic image of a device (mobile or non).  It recovers these files by searching a disk image for that file type's unique header and footer.
  * (S) [Sleuthkit](http://www.sleuthkit.org/): A collection of command line tools and a C library that allows you to analyze disk images and recover files from them.
  * (S) strings:  Running this command line tool against any file will print its printable characters that are at least 4 characters long. Strings can really be useful when trying to locate information within a large file, such as a forensic image of a device (can be 16GB or more, depending on the size of the device). It allows for quick and efficient searching when using in combination with the "grep" command.
  * (S) hexedit: No forensic investigation is complete without a hex editor. Hexedit is built into the Santoku VM, and can be used to view or manipulate the binary data within a file. 

### Network Analysis:
* (S) [Wireshark](https://www.wireshark.org/): Wireshark is a network protocol analyzer.
* (S) Ettercap
* (S) Zenmap (as root)
* (S) Chaosreader
* (S) dnschef
* (S) DSniff
* (S) mitmproxy
* (S) tcpdump
* (S) wifite
* (S) Nmap

### Malware Analysis
* (S) Androguard
* (S) AntiLVL
* (S) APKTool
* (S) Baksmali
* (S) Bulb Security SPF
* (S) dex2jar
* (S) Drozer
* (S) Jasmin
* (S) JD-GUI
* (S) Procyon
* (S) radare2
* (S) Smali

## Commercial Tools
While the focus of this chapter was mainly on OSS, it is worth mentioning the commercial tools that can also assist in a Mobile IR investigation. 

In addition to the list of OSS Process/Incident Management tools that we linked to in the previous section, there are also commercial tools available such as [Resilient's Incident Response Platform](https://www.resilientsystems.com/). This can be used to help automate the IR process, by integrating directly with other prevention and detection systems that are already in place. It helps teams track incidents and offers dashboards and reporting reatures to provide status updates to various groups.

### Continual Analysis
[NowSecure's Protect mobile application](https://www.nowsecure.com/protect/), when installed in advance of a mobile incident, can help establish a device, OS, and app baseline. When used within an organization, it provides an administrative dashboard that can allow access to aggregated security scores, network data, and vulnerability analytics. In the event of an incident, this data can then be used to pinpoint what went wrong and when.

[zANTI](https://github.com/Zimperium/zanti_plugins): zANTI is a mobile penetration testing toolkit that lets security managers assess the risk level of a network 

### Device Acquisition / Analysis:  Most commercial forensics tools offer both the ability to perform a device acquisition as well as built in analysis tools.
* [NowSecure Forensics](https://www.nowsecure.com/forensics/) (iOS / Android)
* [Cellebrite](http://www.cellebrite.com/Mobile-forensics)
* [XRY](https://www.msab.com/products/xry/)
* [Lantern](https://katanaforensics.com/products/)

