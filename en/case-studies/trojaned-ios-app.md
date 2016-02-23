# Trojaned iOS app installs

This case study will examine the conditions leading up to, techniques used and impacts of an attacker installing tojaned versions of iOS apps on a target's iPhone.

## Apple's Walled Garden

Apple tightly controls the iOS ecosystem, in particular how apps are distributed via the App Store. While this has lead to some frustration from app developers, tinkerers and security researchers, it has certainly reduced the impacts on malicious apps as it's very difficult to install them on traget devices. An app needs to either be distributed via the App Store or signed with special certificate issued by Apple to a developers and then loaded onto thei device via iTunes or a special link but requiring user confirmation. Contrast this to Android where developers have many distribution channels and device owners can configure the device to install "untrusted" apps.

If an attacker wants to install malicious apps on a target's iPhone, they either need to trick the user into accepting the Developer Signed application or gain physical access to the device to install the app directly.

## Conditions and methods for compromise
In September 2014, Apple released the iPhone 6 and 6 Plus to the public. As with previous iPhone releases, the device was highly anticiapted and soght after. In the United States, that meant either waiting in long lines or being back ordered for a few weeks.

However, in foreign countries it is far more difficult to acquire a recent iPhone. Demand is extremely high and people are will to pay significant premiums to aacquire a device. A new iPhone is also a status symbol so often time successful business executives or government officials will be the reciepient of a new device. This could be a device they purchased, often usinf their connections, or simply a gift.

The iPhone frenzy presented a perfect opportunity to target an successful individual. The attacker knew of the individuals desire for a new iPhone 6 and took advantage of the situation.

The attacker purchased an iPhone 6 and while they had physical possession, they setup the device for the individual. This was likley viewed as a sign of courtesy so the successful individual could begin using the device as soon as they recieved it.

Since the attacker had physical access to the device, they were able to install trojaned versions of popular apps on the device including:

* Chrome
* Skype
* Facebook
* WhatsApp

The apps targeted and collected sensitive data and communications from the device and sent the data back to the attacker via their command and control (C2) servers.

## Trojaned iOS apps
Creating a tojaned version of a popular app is a very effective technique for compromising a device. On the device, there would be very little indication that the device was trojaned. There would be negligable impact on battery and the functionality of the app would be consistent with the valid version. 

To create a tojaned iOS app, an attacker does not need deep technical expertise. Instead, a developer with a few additional security tools could perform the following:

* Download the public app
* Decrypt the app
* Inject a dynamic library into the app bundle
* Load the dynamic library at run time
* Hook interesting parts of the app
* Configure the apo to send intercepted data back to the attacker via a C2 server
* Re-sign the app with a Developer or Enterprise cert

At that point, an attacker with physical access to the iPhone could install the app via either an iTunes sync to clicking on a link to the binary (via the itms:// uri) and then trusting the app when prompted by iOS.

## Detecting and remediating a trojaned iOS app
As with any incident, you must first identify the incident. While it unlikely the individual (unless both technical and security savvy) will be able to itendify a trojaned app, there are a number of signs a security analyst can look for.

Since the app is modified from the App Store version, an analyst equipped with the proper tools and information will be able to detect and determine the app is not legitimate. For example, if you review the outbound network connections from the device you would see traffic going to servers not associated with normal app traffic. There are various ways to inspect network traffic including:

* Continual analysis tools
* Netstat app
* Netstat command via a terminal app
* Proxing network traffic
* Inspecting network traffic on network device (i.e. a switch level)

In addition, the analyst could inspect the app bundle and see that it is a Developer Signed app and thus modified from the App Store version. This is visible by inspecting the app binary directly and examining the certificate used to sign the app.

Finally, the developer app will not auto-update like App Store apps. So, the user may become suspicious when other people receive app updates and they do not. Or they may search the App Store, insall the original app and then wonder why they have two app icons and had to log in twice. Finally, with some continual analysis apps, the security analysts should be able to detect that a non-standard version on a popular app is installed on a device.

Once the trojan app has been identified, it is critical to quickly contain the threat. The most effective approach would be to isolate the device by turning on airplane mode. You would then make sure you backup the device and have a copy of the app binary for inspection. We will explore this in more detail throughout the [Framework for Mobile Incident Response](../mobile-incident-response-framework) chapter.
