<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
  <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
</div>

# Trojaned iOS app installs

This case study will examine the conditions leading up to, techniques used and impacts of an attacker installing trojaned versions of iOS apps on a target's iPhone.

## Apple's Walled Garden

Apple tightly controls the iOS ecosystem, in particular how apps are distributed via the App Store. While this has lead to some frustration from app developers, tinkerers and security researchers, it has certainly reduced the impacts of malicious apps as it's very difficult to install them on target devices. An app needs to either be distributed via the App Store or signed with special certificate issued by Apple to a developers or businesses and then loaded onto the device via iTunes or a special link but requiring user confirmation. Contrast this to Android where developers have many distribution channels and device owners can configure the device to install "untrusted" apps.

If an attacker wants to install malicious apps on a target's iPhone, they either need to trick the user into accepting the Developer- or Business-signed application or to gain physical access to the device to install the app directly.

## Conditions and methods for compromise
In September 2014, Apple released the iPhone 6 and 6 Plus to the public. As with previous iPhone releases, the device was highly anticipated and sought after. In the United States, that meant either waiting in long lines or being back ordered for a few weeks.

However, in foreign countries it is far more difficult to acquire a recent iPhone. Demand is extremely high and people are willing to pay significant premiums to acquire a device. A new iPhone is also a status symbol so often time successful business executives or government officials will be the recipient of a new device. This could be a device they purchased, often using their connections, or simply a gift.

The iPhone frenzy presented a perfect opportunity to target an successful individual. The attacker knew of the individuals desire for a new iPhone 6 and took advantage of the situation.

Attackers purchased an iPhone 6 and while they had physical possession, they setup the device for the individual (who also happened to be the unsuspecting target of the attack). This was likely viewed as a sign of courtesy so the successful individual could begin using the device as soon as they received it.

Since attackers had physical access to the device, they were able to install trojaned versions of popular apps on the device including:

* Chrome
* Facebook
* Skype
* WhatsApp
* Telegram

Trojaned applications were installed alongside with non-trojaned, but pirated apps, such as Pages and Numbers productivity applications, supposedly to make the device "business-ready" and to look less suspicious.

The apps targeted and collected sensitive data and communications from the device and sent the data back to the attacker via their command and control (C2) servers.

## Trojaned iOS apps
Creating a trojaned version of a popular app is a very effective technique for compromising a device. On the device, there would be very little indication that the device was trojaned. There would be negligible impact on battery and the functionality of the app would be consistent with the valid version. 

To create a trojaned iOS app, an attacker does not need deep technical expertise. Instead, a developer with a few additional security tools could perform the following:

* Download the public app
* Decrypt the app
* Inject a dynamic library into the app bundle
* Modify app's main executable to load injected dynamic library at app launch
* Hook interesting parts of the app
* Configure the app to send intercepted data back to the attacker via a C2 server
* Re-sign the app with a Developer or Enterprise cert

At that point, an attacker with physical access to the iPhone could install the app via either an iTunes sync or by clicking on a link to the binary (via the `itms://` uri) and then trusting the app when prompted by iOS.

## Detecting and remediating a trojaned iOS app
As with any incident, you must first identify the incident. While it unlikely the individual (unless both technical and security savvy) will be able to identify a trojaned app, there are a number of signs a security analyst can look for.

Since the app is modified from the App Store version, an analyst equipped with the proper tools and information will be able to detect and determine the app is not legitimate. For example, if you review the outbound network connections from the device you would see traffic going to servers not associated with normal app traffic. There are various ways to inspect network traffic including:

* Continual analysis tools
* Netstat app
* Netstat command via a terminal app
* Proxying network traffic
* Inspecting network traffic on network device (i.e. a switch level)

Note that analysing *contents* of the data being sent (as opposed to *destination* it is being sent to) can be problematic due to the fact that TLS may (and likely to) be used to protect confidentiality and integrity of the data. In such case analyst must either take additional steps to enable traffic decryption (i.e. adding extra trusted root certificate to the device under scrutiny) or, if such device modifications are not desirable, revert to other analysis techniques.

In addition, the analyst could inspect the app bundle and see that it is a Developer- or Enterprise-signed app and thus modified from the App Store version. This is visible by inspecting the app binary directly and examining the certificate used to sign the app and its executable content.

Finally, apps not installed via App Store will not auto-update, so the user may become suspicious when other people receive app updates and they do not. Or they may search the App Store, install the original app and then wonder why they have two app icons and had to log in twice. Finally, with some continual analysis apps, the security analysts should be able to detect that a non-standard version on a popular app is installed on a device.

Once the trojan app has been identified, it is critical to quickly contain the threat. The most effective approach would be to isolate the device by turning on airplane mode or placing the device into a Faraday cage (box/bag). You would then make sure you backup the device and have a copy of the app binary for inspection. We will explore this in more detail throughout the [Framework for Mobile Incident Response](../mobile-incident-response-framework) chapter.
