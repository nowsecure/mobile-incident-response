# iOS Incident Response

<!--- This chapter will provide you:

* iOS Incident Response Process
* iOS Data Collection
* iOS Incident Response Analysis
* iOS IR Exercise
* Answers - iOS IR Exercise
--->

# Introduction

Processes for incident response and digital forensics have a lot in common and iOS is no exception to this. One important difference though is that for incident response process we assume owner of the allegedly compromised device to fully comply with investigator's request to provide access to the device, such as to disclose or disable passcode. This is a subtle but very important difference, especially on iOS, where passcode protection relies on proven cryptography and, in many cases, cannot be bypassed.

This chapter opens with a general introduction to iOS system and application security and then moves on to explain iOS-specific parts of mobile incident response.

# iOS Security

iOS is easily the most secure mainstream mobile OS today. Its security mainly rests on following pillars:
* limited application distribution channels enforced via code signing  
* application isolation  

## Application Distribution Channels

iOS, unlike its major competitor, Android, is a closed system and, more importantly for security, is actually a closed *ecosystem*: Apple maintains full control over what code gets delivered to and is approved to run on the device. It does so by requiring all code to be cryptographically signed in order to run on the device and the public key used to verify signature must be signed by Apple.

There are relatively few routes through which applications can get to the iOS device, let's look at each of them in more detail.

### Apple AppStore

AppStore is by far the most popular source of applications, and is the only one for vast majority of non-enterprise users and, unlike with Android, there are no third-party applications stores. Because of this inherently centralized application distribution system Apple can -- and it actually does -- screen every application submitted to the AppStore for various indicators that it thinks signal increased threat, such as uses of private or undocumented functions or OS interfaces, attempts to access privileged data, non-compliance with Apple-prescribed policies, and so on. This application screening process is also known as AppStore review process and is notorious among iOS developers for its unpredictability, both in how long it can take and what its outcome will be.

Although Apple performs application screening (by presumably running static and dynamic analysis on the submitted binaries), it has been demonstrated in the past that this screening process can be circumvented and malicious binaries can be submitted, approved, and distributed through the AppStore (add references: Miller; Georgia Tech). So although highly unlikely, an application downloaded from AppStore can exhibit malicious behaviour.

Applications distributed via AppStore are signed with Apple's own key. The process works like this: developer builds the application, signs it with a distribution key obtained from Apple and submits for the AppStore review process. Apple checks the submission and, once happy with it, removes original signature and re-signs with AppStore distribution key.

### Enterprise Distribution

iOS applications can also be distributed outside of the AppStore. This channel is primarily meant for companies needing their line of business mobile applications that are not suitable for distribution in the AppStore. Because they do not use AppStore for distribution and thus do not go through AppStore review process, enterprise-distributed applications have inherently higher risk than AppStore-distributed ones.

Applications distributed via this channel are signed by enterprise's distribution key obtained from Apple. To qualify for such a key, enterprise must have a D-U-N-S number (few years back they used to have another requirement of at least 500 employees). Application signed by such key will run on all iOS devices provided that enterprise is in a good standing with Apple (i.e. that its distribution key hasn't been compromised and corresponding certificate hasn't been revoked). When enterprise-signed application runs for the first time, user will be prompted to trust this particular publisher.

(add screenshot)

### Development Distribution

iOS applications can also be distributed to  limited number of devices to facilitate development, debugging, and testing. This method is primarily meant for application developers. Conceptually it is similar to enterprise distribution but with one very important difference: list of devices on which application is approved to run must be known in advance, at the time when application is signed, and this list may not contain more than 100 devices.

Application prepared for development distribution embed in them (in associated provisioning profile, to be precise) a list of up to 100 UUID (unique identifier of the device). Upon application launch iOS checks if device's own UUID is in that list and terminates application if it's not.

Applications distributed via this channel are signed by developer's key obtained from Apple. To request such key, one needs to be a member of Apple Developer Program. Anyone of age 18 and above can join this program and membership is $99 a year.

## Code Signing

Code signing is a cornerstone of Apple's "walled garden" approach and is the foundation which allows to limit distribution channels as described above.

All executables that run on iOS have to be signed. Signature verification is performed when application is launched and while the application is running. Granularity for code signing is a memory page: every time an executable memory page is loaded into memory or is modified, a verification process kicks in, and if it fails the application is terminated. Pages are not signed individually; instead, each page is hashed and list of computed hashes is signed as a whole, thus forming a trusted hash directory for a given executable. There are actually two different mechanisms that iOS uses to verify code signatures:
1. Applications, services, and shared code that are part of  iOS itself do not actually contain a digital signature attached to them but rather utilize *static trust cache* -- a list of known good hashes embedded into iOS kernel. **[This is why, for example, it is not possible to take some vulnerable version of system daemon from and older iOS version and use it in a newer one (CHECK THIS)]**.
2.  Applications that are not part of iOS contain a digitally signed list of hashes of memory pages containing executable code.

In the context of incident response it is important to note that code signing provides at least some level of attribution: every executable is signed and embeds public-key certificate carrying information about the signing party.

### Entitlements

**TODO**

## Application Isolation

In addition to only allowing signed applications, iOS also enforces strong isolation between installed applications. This is achieved by means of a *sandbox* and other techniques:
* **Filesystem**. When application is installed iOS assigns it a randomly-named directory on the local filesystem (under `/private/var/mobile/Containers`) where all application's content is to be stored. Sandbox prevents application from accessing containers of other applications and severely limits access to other locations outside of application's container.  
* **Shared resources**. Direct access to shared resources is generally prohibited by a sandbox and all access requests must be brokered through intermediate system daemons. Keychain is a good example: applications cannot access `keychain-2.db` file directly and must communicate any requests to `securityd` daemon, who then perform requested action on behalf of the callee and enforces necessary isolation (by only permitting application to read its own keychain records, for example).  
* **Inter-process communication**. This aspect of multitask OS is severely crippled in iOS and applications have very limited means to communicate with each other.

## Jailbreaking

As we've looked at the security mechanisms built into iOS, some readers might got an impression that choices and restrictions Apple made to improve security can impair certain areas of functionality and usability. Unfortunately, this is true: iOS is a more locked down and less open to customizations than other mobile operating systems out there. Overcoming those limitations is one of the main reasons *jailbreaks* exist.

Jailbreaking is essentially disabling some or all of the security measures described above. This allows users to run so-called tweaks and apps that provide functionality that Apple wouldn't otherwise allow into its AppStore. Jailbreaking is also very important for iOS security research as it provides researchers with better access to iOS kernel and internal.

It is important to understand that because jailbreak disables many of the built-in security protections, devices that are jailbroken are far more likely to be affected by infected by malicious code or exploited by malicious people. Therefore it is highly recommended to institute and enforce a policy that actively prohibits use of jailbroken devices in your enterprise environment.

# Mach-O Executable File Format