# Categories of Mobile IR Tools

It's helpful to characterize mobile incident response tools into four broad categories:

1. Continual Analysis
2. Device Acquisition
3. Analysis

In this section, we will describe these categories of tools and provide more detailed examples. In the subsequent sections, we will walk through the process of setting up an environment to use a variety of mobile IR tools, as well as provide a descriptive list of those that are open source, free, and briefly explore commercial tools.

## Continual Analysis
The ideal scenario when responding to a mobile incident, is to have had tools and procedures already in place to proactively log data that may be useful during an investigation. The purpose of this category of tools is to provided a baseline for device properties and behavior in four main areas that make up the mobile attack surface:

  1. System (e.g., operating system, jailbreak status)
  2. Configuration (e.g., passcode, encryption)
  3. Apps (e.g., installed, updated, removed)
  4. Network (e.g., security, DNS poisoning, SSL certificates)

## Device or Data Acquisition
This category discuss the steps that must be taken to properly handle the device, prevent any changes to the data, and properly acquire the data from the device. 

Device Triage: OS, installed apps, running processes

Data acquisition tools are used to forensically recover the disk or memory contents from a device and store it as a copy into an external file. This file, or "image" of the data, can then be used during the analysis phase. The purpose of creating a forensic image of a device is to have a duplicate copy to run analysis tools against so that the original evidence remains pristine. The following are a list of various types of device or data acquisition tools.

**Logical**

A logical technique extracts allocated data and is typically achieved by accessing the file system. Allocated data simply means that the data is not deleted and is accessible on the file system.

**Backup**

Techniques are available on both iOS and Android devices to perform a backup of the operating system. On iOS, a backup is performed either via iTunes or iCloud, and stored on the user's computer or cloud account, respectively. On Android, backups can be performed through a 3rd party application, or using the android debug bridge (adb) command. Backups essentially include the same type of data that is recovered through a logical acquisition. Backups may be useful as an examiner if you don't have access to the physical device, or if you are looking to recover historical data that might be stored in an old backup, but no longer exist on the device.

**Physical**

Physical techniques target the physical storage medium directly and these do not rely on the file system itself to access the data. There are advantages to this approach, the most significant being that physical techniques may provide access to deleted data. The file systems often only mark data as deleted or obsolete and do not actually erase the storage medium unless needed. As the physical forensic techniques provide direct access to the storage medium, it is possible to recover not only the allocated data but also the unallocated (deleted or obsolete) data. With encryption on the latest devices/operating systems, physical acquisitions are more difficult to perform than they used to be.

**Proxying network traffic**

Collecting a sample of network traffic from an access point that a mobile device is connected to will allow for additional network analysis to analyze protocols used by various applications/services running on the device and determine if there are any unknown or insecure protocols in use.

**Image verification**

In digital forensics, examinations are performed on the original media only if absolutely necessary. In most cases, a forensic copy is made, and the examiner will analyze that image, so as to not modify the original media. In order to show that the working copy contains the same data as the original, it has become a best practice to create a unique signature for both the original and the copy by using a hash algorithm. If the values match, this technique shows that the forensic image is in fact a copy of the original. Most commercial tools will report either an MD5 or SHA1 hash value, two different algorithms, both of which are used for the same purpose. Linux commands can also be used to determine either of these values on an image or file using commands such as md5sum or sha256sum. Note that image verification will only be successful during the physical acquisition process.

## Analysis
Once the data has been acquired from the device using the techniques above, a number of analysis tools can be used to locate the target information.

### Forensic Analysis
**Timeline analysis**

Several tools are available that can be run against a disk image and will list out each and every file within the file system, both allocated and unallocated. From this list, the tool creates a timeline of events that have occurred on the device. This process is typically run against a hard drive, but can also be used on physical image file retrieved from a mobile device. The resulting timeline will show the file name, whether it was created, modified, or accessed, the date and time this event occurred, and other pieces of information that might be significant to an investigation. There are thousands, and sometimes hundreds of thousands of files on these devices, so having the ability to sort by time is an important step in this process. Timelines are typically the most useful when an investigator has a specific time frame to narrow down the choices. 

**Searching**

Once a physical image of a device is acquired, there are various tools that can be used to further analyze that image and search for specific keywords or other data. One of these methods involves the use of the Linux “strings” command. When run against a file (or even a full disk image), strings will extract printable characters that are at least four characters long. This command can be used against individual database files to potentially view and recover deleted data. Another method that allows the examiner to search for data is the use of a hex editor. By viewing a disk image within a hex editor, the examiner has the ability to jump to a specific area within the image. For example, if a particular e-mail address is of unique interest in a case, this address can be searched across the entire dmg. The examiner can then analyze the surrounding content.

**File Carving**

This process scans an entire disk for specified file signatures in order to recover files or file fragments from the disk. Using this method, both deleted and undeleted files can be recovered since the process focuses on the content of the files rather than its metadata. This is a popular technique used in forensic examinations, as it has been largely successful in recovering deleted photos, e-mails, text messages, and other important data. File carving techniques are built into some forensic analysis tools; however, there are open-source Linux tools available that will perform this action as well. These tools can be run via command line against a mobile device physical image in order to recover valuable files.

### Comparative
In any incident, it is ideal to use either current or historical data, and compare it to things like known malware, C2 servers, or app intel to identify security vulnerabilities. For example, in the event of an incident involving an imposter app existing on an app store, comparing the file signature to intelligence about known malware can help determine whether this is in fact a malicious or legitimate application. This comparitive process canl help an organization perform mobile app reputation monitoring, and will determine any unauthorized use of their brand.

### Malware analysis
A common incident involving mobile is that the device is "acting strange." In these cases, the user can't always identify what the problem is, just that something is happening such as increased battery drain or certificate errors on the device. In this event, the device should be forensically imaged, analyzed, and if possible, network analysis performed. If malware is suspected, the analyst would need to review the resulting artifacts to locate the potential malware. Once identified, this application should first be compared to intelligence against known malware, then static and dynamic code analysis should be performed to determine whether the app is truly malicious.

### Network analysis
Analysis of capture network traffic is important as it could reveal unique findings, such as personal or corporate data being transmitted insecurely. It is important to understand what data is being transmitted, where it is going to in terms of the organization that owns the server, and what countries that data is being sent to. As an incident responder, if you have access to baseline or historical device data, this is ideal. You may then be able to identify whether the mobile device was connected to any insecure WiFi access points, observe SSL re-signing, etc.
