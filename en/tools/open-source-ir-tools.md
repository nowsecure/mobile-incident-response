# Open Source Mobile Incident Response Tools

There are a number of open-source tools and distros that can be used during a mobile incident or during a forensic examination process.  The use of advanced Linux forensic analysis tools can help an examiner locate crucial evidence in a more efficient manner. Some of these tools are very powerful and provide the capability to quickly index, search, and extract certain types of files.

The following is a list of open source and other freely distributed tools that are available either within the Santoku Linux distro or elsewhere, broken down by the categories discussed earlier in this chapter. The tools that have already been pre-installed within Santoku will be denoted by an "S", while others mentioned will need to be manually installed in the Santoku VM that you've set up. Commercial tools will be briefly discussed in the section that follows.

## Continuous Monitoring
* Android Vulnerability Test Suite (VTS): Scans an Android mobile device to detect known vulnerabilities. There are two types of vulnerability tests that can be performed:
  * Detection only (does not attempt to exploit)
  * Detects and attempts to exploit the vulnerability


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
* Malware Analysis


## Prevention


