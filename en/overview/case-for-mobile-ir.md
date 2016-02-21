# The Case for Mobile Incident Response

## Mobile Incident Response
Mobile devices have already sufficently penetrated enterprises to warrant full support in an incident response strategy. They have access to sensitive data and impact the operations of an enterprise. And, like all technolgy, they have security flaws which expose the enterprise to risk.

While most enterprises have some level of incident response plans in place, very few have developed processes and tools to respond to a mobile incident. This is a clear gap that security teams must address.

In the section, we will demonstrated that mobile apps and devices are increasingly:

* the focus on government regulation and law enforcement
* possess significant security and provacy flaws
* are the target of cyber criminal and nation state attacks
* receive very little security focus and investment from enterprises

## Regulation and Law Enforcement
In the previous section, we explored a few examples of regulations that cover incident response. However, smartphones are a relatively new technology and at best are addressed broadly in a few of these regualted industries. This means that the industry is largely self-regulated today and, unfortunately, there are many mobile device and app security issues.

If these issues persist and become a larger problem, it will ultimately lead to regulation and law enforcement. This is something the mobile industry should strive to avoid and attempt to address these issues within the ecosystem. This can be achieved far more quickly and efficiently than government regulations.

### FTC v Wyndham
In 2008, Wyndham Worldwide Corporation experineced several security incidents resulting in the loss of credit card data. The impact of this data breach was over $10.6 million in fraud loss. The Federal Trade Commission filed a complaint in federal court against Wyndham under Section 5 of the FTC Act for unfair method of competition. 

Wyndham fought the FTC suit but the District Judge ruled in favor of the FTC. Wyndham appealed the decision but in August 2015, the U.S. Court of Appeals for the Third Circuit affirmed the district court, upholding the FTC's data protection authority.  

Judge Thomas Ambro stated:

> A company does not act equitably when it publishes a privacy policy to attract customers who are concerned about data privacy, fails to make good on that promise by investing inadequate resources in cybersecurity, exposes its unsuspecting customers to substantial financial injury, and retains the profits of their business. [^6]

While this ruling does not directly involve mobile devices or apps, it is significant for several reasons:

1. Mobile apps are required to publish a privacy policy through multiple mechanisms including the Terms of Serivce for Apple's App Store and Google Play as well as various privacy laws including [California's Online Privacy Protection Act](http://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=BPC&division=8.&title=&part=&chapter=22.&article=) and the European Union's [Data Protection Directive (95/46/EC)](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=CELEX:31995L0046:en:HTML);
2. A compromise involing a mobile deivce or app would likely trigger the "investing inadequate resources in cybersecurity" unless the company performed security testing and had an incident response policy in place to minimize the impact of any breach.

The combination of the FTC v Wyndham ruling plus a widespread lack of investment in mobile security does not bode well for enterprises benefiting from mobile devices and apps.

## Mobile Devices and Incident Response Trends
Over the past 3 decades, the process of incident response has matured. Bruce Schneier, a respected security technologist, wrote about evolution and future of IR in his popular [Schneier on Security](https:/
/www.schneier.com/blog/archives/2014/11/the_future_of_i.html) [^1] blog. He identified broad focuses in each decade since the 1990s starting with protection, then moving into detection and finally focused on response by the 2010s.

He reflected that in recent years, new IR products and services are being developed and implemented due to three important trends:

1. Devices and data now regularly reside outside the control of IT departments (mobile, cloud, etc.)
2. Attack and threats are far more sophisticated and effective
3. Companies continue to under-invest in protection and detection, increasing the need for response

Each of these trends are very much a reality in the mobile ecosystem and worth exploring further.

## Controling mobile devices and data
Mobile technology, by its very definition, lives outside the traditional defined IT boundries such as local networks and firewalls. This dramatically impacts the enterprises ability to control both the devices and, perhaps more importantly, the data residing on them.  

### Device ownership and data storage
Increasing, the mobiles devices which impact an enterprise's security are neither purchased nor managed by the IT department. Some quick examples of this include:

* Employee BYOD
* Contractors
* Vendors and supply chain
* Customers

![Where can attackers find your mobile data?](../assets/where-is-your-mobile-data.png)

While the recent trend in enterprise mobile security has been to deploy management software such as MDM, EMM and similar on BYOD scenarios, this is clearly a strategy that will not scale to your vendors, supply chain and customers. 

### Network perimeter
Clearly mobile devices defy traditional network policy enforcement since they do not exclusively reside on the corporate network. By design, mobile devices likely have a least two and generally more ways they can connect to networks.

The obviosuly netowrk connection not directly controlled by the enterprise is the mobile phone network. Todya 4G networks are fast and very prevelant and many individuals simply use the mobile operators network over corporate-provided Wi-Fi.

The next most common accessible networks are provided via Wi-Fi. This generally includes a network provided by the enterprise (and thus a controlled ingres/egress point where a company can exert oversight or control) but also a home network and then various networks available to the general public. These could include Wi-Fi access point provided by retail stores (Starbucks, for example), airports, city-wide public networks, home-based Wi-Fi via companies like Comcast via their XFINITY service and, unfortunately, malicious networks that are controlled by attackers.

While cellular and Wi-Fi networks are the most common paths to network access, there are additional techniques including:

* Bluetooth networks
* Tethering over USB
* Near Field Communication (NFC)
* GPS (a form of radio-based network traffic)

Suffice to say, there are many ways for mobile devices can connect to networks and very few of them provide enterprises with control over the traffic. While some IT departments and mobile security solutions attempt to backhaul all mobile traffic over a device or per-app VPN, this technique will ultimately fail due to a number of causes discussed in the next section.

### Privacy implications
There is a growing backlash from device owner regarding mobile device management tools, techniques and their impact on privacy. In some instances, the legal teams at large enterprises are also pushing back against solutions which intercept or collect significant personal information as it becomes a liability for them. 

The biggest challenges are best examined exploring the impacts on a single technique. For this example, let's examine how a device or per-app VPN impacts a mobile device:

1. Initial setup is cumbersome
1. Re-connecting to the VPN is frustrating and time consuming
1. A VPN slows down many network connections, espeically on a higher latency mobile network
1. Additional battery drain is incurred
1. Personal privacy is significantly imapcts
1. Enterprises have access to sensitive employee data (e.g. Internet searches, app traffic and geo-location) which can place significant liability on the enterprise
1. These solutions are not possible outside of employees and perhaps contracts (though the later is unlikely)

The trend in mobile devices and applications is clearly towards an ecosystem where the IT and security departments have very little control over the devices.

## Effectiveness of attacks and threats

As mobile devices and apps proliferate, cyber criminals and actors focused on espionage (with both intellectual property and national security objetives) are clearly following the trend. They recognize that a significant amount of data they are targeting is now present and at times more accessible to them on mobile devices. 

While early mobile attacks were farily trivial and frankly lazy, recent trends have revealved a more sophisticated and sustained effrot to thwart mobile defences. While we will explore this topic thoroughly in the [Attacking Mobile Devices](../mobile-attacks/README.md) chapter, it is helpful to provide several examples here. 

### Mobile Threats

Let's start off looking at mobile threats. This category includes vulnerabilities discovered in mobile hardware, operating systems and applications which an attacker could take advantage of. 

Educating enterprises decision makers about the risks of mobile threats and attacks is a critical first step to addressing the issues. However, mobile attack are under-reported for several reasons:

1. Due to lack of visibility, many individuals and enterprises are not aware an attack occurred
1. In server-side attacks, enterprise may be compelled to disclose the breach due to consumer protection laws however it is unlikely a targeted mobile attack would trigger such action  

For these reasons, the most effective resources available today to educate individuals and enterprises about mobile risks are identifying the threats which could expose them to compromise.

#### Android Security Threats

Android encompasses a deep intertwined ecosystem including Google/Android, OEMs, wireless carriers and app developers. In this brief overview, we will provide examples of several publicly known Android security threats.  

##### Andorid Stagefright vulnerability

In September 2015, Zimprium researcher Joshua Drake ([@jduck](https://twitter.com/jduck/)) disclosed a vulnerability impacting nearly all Android devices since Android 1.5 which could allow an attached to remotely execute code on the device. The flaw was discovered in the Stagefright library, shared coded that Android devices use to process media files. By employing fuzzing techniques, it was discovered that specifically crafted media files including images, audio and video files sent to the device would crash libstagefright and provide the attacker with the ability to compromise the device.

Joshua coordinated with the Android Security team and patches were submitted to the AOSP and shared in advance with Android partners. However, the patches were not fully effective in mitigating the flaws and additional research uncovered new attack vectors. In addition, due to the complexity to deploying changes to the fragmented Android ecosystem, most users remain vulnerable to the threat.

Note: if you own or manage risk for Android devices, you can determine if the device is vulnerable to Stagefight or other know flaws by running the [VTS for Android app]. The app, developed by the NowSecure Research Team, is fully [open sourced](https://github.com/nowsecure/android-vts/) and is actively maintained.

##### Samsung keyboard vulnerability

In June 2015, NowSecure researcher Ryan Welton ([@Fuzion24](https://twitter.com/Fuzion24)) presented at [BlackHat London](https://www.blackhat.com/ldn-15/summit.html#abusing-android-apps-and-gaining-remote-code-execution) [^4] and exposed a serious flaw in over [600 million Samsung devices](https://www.nowsecure.com/keyboard-vulnerability/). [^5] Despite following a responsible and coordinated disclosure process over the course of 9 months, the flaw was ultimately misunderstood by Samsung and at the time of the disclosure, there was no patch that users or enterprises could apply. 

To make matters worse, the insecure application was signed with system privledges granting the app and thus the attacker significant access to teh device and data through remote code execution. The app could not be disabled and regular checked for updates over the network, the trigger necessary to launch the attack. Anyone attacker with a position on the network between the endpoint and the SwiftKey update server could execuate this attack.

#### App example

The Google Play store had 1.6 million apps available for download as of July 2015. [^10] Many of the apps actually contained security flaws so it's difficult to even choose one example. 

In January 2016, Jake VanDyke spent a week reviewing video cameras and the mobile apps that can remotely control the camera. After examining some of the most popular cameras on Amazon, Jake noted that [every camera-and-app combination I tested included at least one security flaw](https://www.nowsecure.com/blog/2016/01/06/insecurity-cameras-and-mobile-apps-surveillance-or-exposure/) that concerned him. The various apps exhibited numerous flaws including:

* Sensitive data transmitted without encryption including username, password and geolocation
* Unencrypted communications allowing someone to adjust camera settings, format the SD card, access stored photos and videos and initiate the recording of audio or video
* Sending the WPA2 key for the network it was connected to
* Vulnerable to Man-in-the-Middle attacks

Hopefully it's clear from this single example that security flaws in mobile apps create significant exposure and risk for not only the individuals using the apps but the enterprises they interact with and work for.

#### iOS Security Threats

Apple is incredibly effective in how they position and market the security of iOS devices. And there are indeed many excellent security features built into the platform. However, Apple developers are just as susciptiple to creating security flaws as any other developer. 

A key difference between Apple's approach to security and Google's approach with Android is the availability of core Android source code (via the Android Open Source Project) for community inspection. This open approach has resulted in more flaws being identified and patched at the core of Android. However, when examining iOS code, seecurity researchers have to employ different techniques, often requiring more time and effort. 

Based on Apple's effective marketing and the lack on open source code for inspection, many people in the IT industry believe that Apple is more secure. However, the the real answer is far more nuanced but can be quantitatively analyzed by examining publicaly available vulnerability data.

##### Apple iOS CVEs

The Common Vulnerablilty and Exposure system maintained bt MITRE was designed to provide visibility to flaws exposed in IT systems. You can filter the data by vendor and operating system which provides visibility to the quantity and category of CVEs for Apple iOS and Android:

![iOS CVEs from 2007 - 2016](../assets/iOS-CVEs-2007-2016.png)

Figure 1: [iOS CVEs from 2007-2016](http://www.cvedetails.com/product/15556/Apple-Iphone-Os.html?vendor_id=49)

![Android CVEs from 2009 - 2016](../assets/Android-CVEs-2009-2016.png)

Figure 2: [Android CVEs from 2009-2016](http://www.cvedetails.com/product/19997/Google-Android.html?vendor_id=1224)

Clearly Apple developers fair no better than any other developer in writing secure code. And the closed nature of their system means far fewer eyes are available to insect and find security flaws. If your strategy for mobile security is to simply rely on the Apple iOS platform, you should strongly consider additional layers of protection.

##### Apple's iOS 9 Security Updates

It is also revealing to examine Apple's own security page for flaws they patched in each new version. I applaud Apple and other technology companies for the transparency in posting these updates but it certainly contrasts with the security marketing Apple publishes.

In particular, in the initial iOS 9 release, [Apple patched over 70 security flaws](https://support.apple.com/en-us/HT205212), many of the quite serious. There is also a history of making rapid release just after a major release to patch serious security flaws found by researchers in the new update. For example, Apple has had over 10 pin-bypass flaws over the years, a visibile example that many end users quickly understand. The ability for an attacker to circumvent the lock screen on iOS devices broadly exposes the device and data to compromise and exfiltration. 

##### iPhone 4 hardware flaw

While most identified flaws occur in software (both the operating system and mobile apps), at times flaws are identified in the hardware of a device. This issues are extremely dangerious as there are generally no mitigations against these types of flaws. 

It has been quite some time since a flaw like this was found in an iPhone however it is worth pointing out an instance of this from the past. When Apple manufactured the iPhone 4, there was a flaw in the boot process that allowed an attacker to boot an unverified boot disk. This allowed any attacker with physical access to boot the device into a modified version of iOS that disabled the pass code and allowed full access to the operating system and the data on the device.

This flaw was obviosuly fixed in the next release of the iPhone but anyone using that device was at risk and have very little mitigations they could employ.

Considering the history of CVEs in iOS, the sheer amount of new code that goes into each release and the ever increasing complexity of the device and operating system, it should be clear that iOS will continue to have security flaws which, if exploited, place the individual and enterprise at risk.

##### iOS app security

Similar to Android, a significant part of the iOS ecosystem are the mobile apps avaialble from the App Store which in July 2015 was 1.5 million apps[^10]. Interestingly, iOS apps tend to be less secure than Android apps based on a high level security scan of 100 popular apps. Given the sample size is quite small, it is not safe to extrapolate this to the entire ecosystem but it is certainly true for the popular apps tested.

One theory is that iOS app developers place more trust in the smart phone's operating system than Android developers do. However, while iOS provides many strong security features, it cannot prevent developers from making common mistakes like sending or storing sensitive data with encryption, failing to adequately perform certificate checking or igorning other commom [mobile app security best practices](https://www.nowsecure.com/resources/secure-mobile-development/). 

### Mobile Attacks

Unlike mobile threats, mobile attacks identify actual instances of mobile threats being exploited in the wild. While these examples are less frequent, they make the strongest case for enterprises to invest in mobile security and incident response. These attacks fall broadly into these categories:

* Known malware
* Targeted attacks
* Weaponizations of mobile threats 

In the [Case Studies](../case-studies/README.md) chapter we will provide deeper examination of real world mobile attackes. However, it is useful to provide examples of several known mobile attacks.

#### Mobile Malware

Mobile malware is the most common form of mobile attacks, in particualr because they are far easier to identify by examining mobile apps. While all mobile attacks are undesirable, mobile malware is the most benign of the categories listed above. We will provide an example of malware on both iOS and Android.

##### Apple iOS XCodeGhost attack

In late 2015, researchers from Palo Alto uncovered modified versions of XCode, the development environment for iOS, avaiavle on multiple websites in China. XCode is a large download and developers in China would often choose cached versions of XCode hosted in China to improve download times.

Attackers sezied this opportunity and modified XCode so that when developers complied and ultimately deployed thier applications to the App Store, malicious code was automatically included in the applications. The malicious code would exfiltrate private data from the iOS devices after the app was installed and run.

Apple identified the affected applications and immediately removed them from the App Store. They published the list of apps on their website and worked closely with the developers to ensure a new version was pushed to the App Store quickly. Some of the apps extremely popular and the full impact of the attack is likley not yet understood.

##### Android SimpleLocker Malware

The Android ecosystem has been a larger target of mobile malware than any other smart phone to date. As such, choosing an example malware to discuss is actually a difficult task. In our Mobile IR Case Studies section, we will explore the outbreak of a [malicious app targeting Aetna customers](../case-studies/mobile-malware-discovered.html) and how the incident was handled. For this overview, though, we will discuss a piece of malware that falls into the "Ransonware" category.

In June 2014, a number of security companies ([Sophos](https://nakedsecurity.sophos.com/2014/06/06/cryptolocker-wannabe-simplelocker-android/) | [Blue Coat](https://www.bluecoat.com/security-blog/2014-06-06/simplelocker-android-ransomware-encrypts-files)) began reporting on and analyzing a newly discovered instance of malware dubbed SimplerLocker.

The inital attack vector appeared to be fake porn sites that promoted the user to download and install a video player. [^9] After installtion, the app launches and immediately takes over the screen, presenting a threatening message and demading payment to decrypt the users files. The back button is disabled and if the user hits the Home button, the app rapidly re-launches. During this time, the app encrypts images (PNG, JPEG) and plain text files (TXT) on the device's media storage. It also leverages the TOR network for it's Command and Control (C2) traffic.

We will study this malware more closely in the Lab Exercises included in this book.  

#### Weaponizing mobile threats

While security problems in mobile apps and operating systems as well as malicious apps are grounds for concern, a more nefarious threat exists. It is generally accepted that it is nearly impossible to prevent a targeted attack against an invdividual or organization. As such, any evidence of organziations enabling or performing targeted attacks is a area of great concern.

##### ZERODIUM's Million Dollar iOS 9 Bug Bounty
Zerodium, is a privately held, venture backed company that positions itself as "the premium acquisition program for zero-day exploits and advanced cybersecurity research."[^11] On September 15, 2015 they announced a $1 million dollar bug bounty for iOS. The bounty would be paid out for any individual or team that "creates and *submits to ZERODIUM an exclusive, browser-based, and untethered jailbreak for the latest Apple iOS 9* operating system and devices"[^12]. While this alone should cause significant concern given the size of the bug bounty and the specific criteria, what's truly distrubing is that on November 1, 2015 Zerodium acknowledged that one team won the prize.[^11].

Of course, the natural question is what does Zerodium then do with the zero-day? Accoring to their FAQ, they:
> analyze and document the vuln, and provide that plus protective measures and security recommendations to clients as part of their Security Research Feed[^13]

Zerodium also answers the next logical question of who their clients are: "ZERODIUM customers are major corporations in defense, technology, and finance, in need of advanced zero-day protection, as well as government organizations in need of specific and tailored cybersecurity capabilities."

Of particular concern is the reference to government organizations and tailored cybersecurity capabilities which likely means targeted attacks. While it would be niave to assume governemnt agencies are not involved in such activities, the public acknowledgment of this should greatly inform the risk organziations of major corporations.

Finally, it's quite telling to see the payout ranges for different types of exploits and systems. In particular, mobile devices are positioned as highest payout category.

![Zerodium Payout Ranges](../assets/zerodium_prices.png)
Figure 3: Zerodium Payout Ranges[^14]

##### Hacking Team 
While Zerodium is in the business of buying and then re-selling exploits, we do not have a deep look at their internal operations nor their customers. However, in July 2015 the compromise of Italian firm Hacking Team exposed not only the internal operations of a company weaponizing and selling exploits but their customer list including soverign nations with documented human rights violations against reporters and activists. Until the time of the compromise, Hacking Team adamently denied they sould their software to any countires with documented human rights violations. However, the compromise and then exposure of 400GB of [Hacking Team emails](https://wikileaks.org/hackingteam/emails/) and files revealed that Hacking Team was [weaponizing mobile security flaws](https://wikileaks.org/hackingteam/emails/emailid/1028689) and selling them to governments around the world. 

We explore the [Hacking Team case study](../case-studies/hacking-team-analysis.html) in more detail but a key takeaway for security professionals is that attackers see value in targeting mobile devices and there are not only techniques for doing this but companies whose business model is to "sell offensive intrusion and surveillance capabilities to governments, law enforcement agencies and corporations." [^8] 

## Under-investing in security
In the final incident response trend pointed out by Bruce Schneier, companies are clearly under-investing in mobile security which greatly increases the need to a effective incident response.

In an IBM sponsored study in 2015, the Ponemon Institue found that:
> Among the more than 400 organizations studied — nearly 40 percent of which were Fortune 500 companies — almost 40 percent of them aren’t scanning the code in their apps for security vulnerabilities, leaving the door wide open to the potential hacking of sensitive user, corporate and customer data. The average organization tests fewer than half of the mobile apps it builds, and a whopping 33 percent of companies never test their apps. [^7]

Instead of taking a survey, NowSecure released their [2016 Mobile App Security Study](https://www.nowsecure.com/blog/2016/02/11/2016-nowsecure-mobile-security-report-now-available/) which analyzed at 400,000 Android apps and found:

* 24.7 percent of mobile apps include at least one high risk security flaw
* The average device connects to 160 unique IP addresses every day
* 35 percent of communications sent by mobile devices are unencrypted
* Business apps are three times more likely to leak login credentials than the average app
* Games are one-and-a-half times more likely to include a high risk vulnerability than the average app

# The Case for Mobile Incident Response
Hopefully this section outlines a clear care for moobile incident response. Mobile devices have deeply permeated all facets of the enterprise and exhibit unique characteristics that necessitate a strong incident response capablilty. These charasteristics include:

* Government regulatory and law enforcement bodies are beginning to require and enforce mobile security;
* Mobile devices and data are increasingly outside the control of IT
* Cyber criminals and nations states are targeting mobile devices
* Mobile apps and devices possess a large number of security and privacy flaws
* Enterprises continue to under-invest in mobile security

#### Footnotes
[^1]: The Future of Incident Response - Schneier on Security. Web. Wed Oct 21 2015. <https://www.schneier.com/blog/archives/2014/11/the_future_of_i.html>.
[^3]: 3nd footnote
[^4]: Black Hat London 2015 | Summit. Web. Wed Oct 21 2015. <https://www.blackhat.com/ldn-15/summit.html#abusing-android-apps-and-gaining-remote-code-execution>.
[^5]: NowSecure. Samsung Keyboard Security Risk Disclosed: Over 600M+ Devices Worldwide Impacted  | NowSecure. Web. Wed Oct 21 2015. <https://www.nowsecure.com/keyboard-vulnerability/>.
[^6]: http://www2.ca3.uscourts.gov/opinarch/143514p.pdf
[^7]: https://securityintelligence.com/mobile-insecurity/
[^8]: https://en.wikipedia.org/wiki/Hacking_Team
[^9]: http://securitywatch.pcmag.com/mobile-security/324666-mobile-threat-monday-android-ransomware-encrypts-your-files-don-t-pay-up
[^10]: http://www.statista.com/statistics/276623/number-of-apps-available-in-leading-app-stores/
[^11]: https://www.zerodium.com/
[^12]: https://www.zerodium.com/ios9.html
[^13]: https://www.zerodium.com/faq.html
[^14]: https://www.zerodium.com/program.html
