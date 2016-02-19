# List of Tools

There are a number of open-source tools and distros that can be used during a mobile incident or during a forensic examination process.  The use of advanced Linux forensic analysis tools can help an examiner locate crucial evidence in a more efficient manner. Some of these tools are very powerful and provide the capability to quickly index, search, and extract certain types of files.

The following is a list of open source and other freely distributed tools that are available either within the Santoku Linux distro or elsewhere, broken down by the categories discussed earlier in this chapter. The tools that have already been pre-installed within Santoku will be denoted by an "S", while others mentioned will need to be manually installed in the Santoku VM that you've set up. Commercial tools will be briefly discussed in the section that follows.

## Continual Analysis
* [Android Vulnerability Test Suite (VTS)](https://github.com/nowsecure/android-vts): Scans an Android mobile device to detect known vulnerabilities. There are two types of vulnerability tests that can be performed:
  * Detection only (does not attempt to exploit)
  * Detects and attempts to exploit the vulnerability
* [X-Ray](https://labs.duosecurity.com/xray): X-Ray allows you to scan your Android device for security vulnerabilities that put your device at risk. 
* [zANTI](https://github.com/Zimperium/zanti_plugins): zANTI is a mobile penetration testing toolkit that lets security managers assess the risk level of a network 


## Device and Data Acquisition
* Device Triage
* Acquisition
  * (S) AF Logical OSE
  * (S) iOS Backup Analyzer 2
  * (S) libimobiledevice
  * (S) dd:  The “dd” command can be used on a device where the examiner has root access, such as a jailbroken iPhone or iPad. This tool is generally used in forensics to acquire a full disk image of a hard drive, SD card, USB flash drive, or other device. 
* Image Verification: 
  * (S) md5sum
  * (S) sha256sum
* Proxying network traffic
  * (S) [Wireshark](https://www.wireshark.org/): Wireshark is a network protocol analyzer.
  * [Charles Proxy](https://www.charlesproxy.com/): Charles is an proxy tool that allows the user to view requests, responses and HTTP headers for HTTP and SSL/HTTPS traffic. 

## Analysis
* Forensic Analysis
  * (S) Android Brute Force Encryption
  * (S) ExifTool
  * (S) scalpel
  * (S) Sleuthkit
  * (S) strings:  When run against a file (or even a full disk image), strings will extract printable characters that are at least four characters long. This is a command-line tool can be used against individual database files to potentially view and recover deleted data. Another method that allows the examiner to search for data is the use of a hex editor. By viewing a disk image within a hex editor, the examiner has the ability to jump to a specific area within the image. For example, if a particular e-mail address is of unique interest in a case, this address can be searched across the entire dmg. The examiner can then analyze the surrounding content.
  * hex editor
* Behavioral Analysis
* Comparative Analysis
* Network Analysis:
  * (S) Burp Suite
  * (S) Ettercap
  * (S) ZAP
  * (S) Zenmap (as root)
  * (S) Chaosreader
  * (S) dnschef
  * (S) DSniff
  * (S) mitmproxy
  * (S) tcpdump
  * (S) wifite
  * (S) Wireshark
  * Charles Proxy

* Malware Analysis
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

* Continual Analysis
* Device Acquisition / Analysis:  Most commercial forensics tools offer both the ability to perform a device acquisition as well as built in analysis tools.
  * [NowSecure Forensics](https://www.nowsecure.com/forensics/) (iOS / Android)
  * [Cellebrite](http://www.cellebrite.com/Mobile-forensics)
  * [XRY](https://www.msab.com/products/xry/)
  * [Lantern](https://katanaforensics.com/products/)
* Prevention?

## Tool Comparison Chart (Will probably remove this section...)

Tool | OSS | Free | Commercial
------------ | ------------- | ------------- | -------------
Android VTS | :white_check_mark: | |
X-Ray | :white_check_mark: | |
zANTI | :white_check_mark: | |
Android Logical OSE |  | :white_check_mark: |
iOS Backup Analyzer 2 | :white_check_mark: | |  
libimobiledevice | :white_check_mark: | |
dd | :white_check_mark: | |

