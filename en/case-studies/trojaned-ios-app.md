<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
    <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
  <a class="cta-banner-update" href="https://www.blackhat.com/us-16/training/mobile-incident-response-ir-for-android-and-ios.html">&nbsp;Mobile IR Training @ Black Hat&nbsp;<i class="fa fa-external-link"></i></a>
</div>

# Trojaned iOS app installs

This case study will examine the conditions leading up to, techniques used by and impacts of an attacker installing trojaned versions of iOS apps on a target's iPhone.

## Apple's walled garden

Apple tightly controls the iOS ecosystem and in particular, how apps are distributed via the App Store. While this frustrates some app developers, tinkerers, and security researchers; it has certainly reduced the impact of malicious apps by making it difficult to install them on target devices. An app needs to either be distributed via the App Store or signed with a special certificate issued by Apple to developers or businesses. The app then needs to be loaded onto the device via iTunes or a special link and requires user confirmation. Contrast this with Android where developers have many distribution channels at their diposal and device owners can configure the device to install untrusted apps.

If an attacker wants to install malicious apps on a target's iPhone, they either need to trick the user into accepting the developer- or business-signed application or gain physical access to the device to install the app directly.

## Conditions and methods for compromise
In September 2014, Apple released the iPhone 6 and 6 Plus to the public. As with previous iPhone releases, the device was highly anticipated and sought after. In the U.S., that meant either waiting in long lines or waiting weeks on a backorder.

In countries other than the U.S., it is far more difficult to acquire a new iPhone model. Demand is extremely high, and people are willing to pay significant premiums to acquire a device. A new iPhone is also a status symbol. Often times successful business executives or government officials will receive a new model of a device. They may purchase the device, often using their connections, or receive it as a gift.

The iPhone 6 and 6 Plus frenzy presented a perfect opportunity to target an executive or government official. 

In this case, the attacker knew of the target individual's desire for a new iPhone 6 and took advantage of the situation. The attacker purchased an iPhone 6 and, with the device in their physical possession, set the device up specifically for this individual (who also happened to be the unwitting target of the attack). The target individual's enthusiasm easily pushed aside any suspicions. The individual likely viewed this pre-configuration of the device as a courtesy so they could begin using the device as soon as they received it.

Since attackers had physical access to the device, they were able to install trojaned versions of popular apps on the device including:

* Chrome
* Facebook
* Skype
* WhatsApp
* Telegram

Trojaned applications were installed alongside with non-trojaned, but pirated, apps. Those apps included Pages and Numbers productivity apps, which also helped create the illusion that the device was "business-ready" to help in alleviating suspicion.

The apps targeted and collected sensitive data and communications from the device and sent the data back to the attacker via their command and control (C2) servers.

## Trojaned iOS apps
Creating a trojaned version of a popular app is a very effective technique for compromising a device. On the device, there would be very little indication that the device was trojaned. There would be negligible impact on battery and the functionality of the app would be consistent with the valid version. 

To create a trojaned iOS app, an attacker does not need deep technical expertise. Instead, a developer with a few additional security tools could perform the following:

* Download the public app
* Decrypt the app
* Inject a dynamic library into the app bundle
* Modify the app's main executable to load the injected dynamic library at app launch
* Hook interesting parts of the app
* Configure the app to send intercepted data back to the attacker via a C2 server
* Re-sign the app with a developer or enterprise certificate

At that point, an attacker with physical access to the iPhone could install the app via either an iTunes sync or by clicking on a link to the binary (via the `itms://` uri) and then trusting the app when prompted by iOS.

## Detecting and remediating a trojaned iOS app
As with any incident, you must first identify the incident. While it's unlikely that an individual (unless both technical and security savvy) will be able to identify a trojaned app (unless they're technology and security savvy), a number of signs might alert a security analyst to a trojaned app.

Since the app is modified from the App Store version, an analyst equipped with the proper tools and information will be able to detect and determine an illegitimate app. For example, if you review the outbound network connections from the device, you would notice traffic going to servers not associated with normal app traffic. There are various ways to inspect network traffic including:

* Continual analysis tools
* Netstat app
* Netstat command via a terminal app
* Proxying network traffic
* Inspecting network traffic on a network device (i.e., at the switch level)

Note that analysing *contents* of the data being sent (as opposed to the *destination* to which it's sent) can be problematic because it's possible, if not likely, that TLS is used to protect the confidentiality and integrity of the data. In such cases an analyst must either take additional steps to decrypt traffic (i.e., by adding an extra trusted root certificate to the device under scrutiny) or, if such device modifications are not desirable, choose alternative analysis techniques.

In addition, an analyst might inspect the app bundle and see that it is a developer- or enterprise-signed app, which means it's modified from the Apple App Store version. This can be seen by inspecting the app binary directly and examining the certificate used to sign the app and its executable content.

Finally, apps not installed via the Apple App Store will not auto-update, so the user may become suspicious when other people receive app updates and they do not. Or they may search the Apple App Store, install the original app, and wonder why two icons appear for the same app and requiring them to log in separately for each of the apps. Finally, with some continual analysis apps, the security analysts should be able to detect that a non-standard version on a popular app is installed on a device.

Once the trojan app has been identified, it is critical to quickly contain the threat. The most effective approach would be to isolate the device by enabling the device's airplane mode or placing the device into a Faraday cage (box/bag). You would then perform a device backup and secure a copy of the app binary for inspection. We will explore this in more detail throughout the [Framework for Mobile Incident Response](../mobile-incident-response-framework) chapter.
