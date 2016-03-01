<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
    <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
  <a class="cta-banner-update" href="https://www.blackhat.com/us-16/training/mobile-incident-response-ir-for-android-and-ios.html">&nbsp;Mobile IR Training @ Black Hat&nbsp;<i class="fa fa-external-link"></i></a>
</div>

# Unauthorized app discovered 
Counterfeit apps developed by unauthorized parties and published to official or unofficial app stores (and elsewhere on the Internet) can damage a company’s brand name and put their customers at risk. As an incident responder, you may be called upon to investigate an incident involving an unauthorized app that might do any one or more of the following:

* Use a company’s brand name without permission
* Target the company’s customers
* Interact with the company’s backend services
* Is made available to the public via app stores or elsewhere on the Internet

## Aetna++ case study
In the fall of 2013, insurance provider Aetna’s Chief Information Security Officer (CISO) Jim Routh asked his IT staff for a list of all of the company’s mobile apps. Creating such a list can prove more difficult than it seems because mobile apps tend to proliferate. For example, an ambitious department within the company may hire a third party to develop and release a mobile app without communicating to the larger organization. Subsidiaries, affiliates and even unauthorized entities may publish an app that uses a company’s brand outright (and without explicit permission) or claims association with the company.

There are hundreds of third-party app stores in existence aside from the Apple App Store and Google Play. Jeff Lenton details the mobile app store ecosystem (as well as comments on this particular case of an unauthorized mobile app) in a 2015 presentation entitled "[Understanding the Mobile Ecosystem](http://www.isaca.org/chapters5/Ireland/Documents/2015%20Presentations/Jeff%20Lenton%20-%20Understanding%20Todays%20Mobile%20App%20Store%20Ecosystem%20and%20Why%20You%20are%20at%20Risk.pdf)". The ecosystem consists of official app stores, Internet company stores, manufacturer stores, carrier or operator stores, affiliate stores, and what he terms “feral apps” that are not available on app stores at all. Keeping track of all these stores, let alone the use of a company’s brand name on those stores, is a daunting task.

Routh chose to work with a third party (RiskIQ for whom Lenton worked) to help identify mobile apps that used his organization’s brand. The list included approximately 20 apps. Upon reviewing the list, one app in particular caught Routh's attention because he was not familiar with it. The app’s name appended two plus signs to the company’s name (i.e., “Aetna++”).

Initially, the Routh surmised that the app was developed for a marketing campaign. He began his investigation by identifying the developer of the app. The developer’s name was Nayem Junaid, and by reviewing the developer’s LinkedIn profile Routh determined Junaid was a ColdFusion developer based in Hydrabad, India. Routh set out to find Junaid in the company’s employee directory but couldn’t find any matches. Next, he explored whether the Junaid was a contractor and attempted to locate him with the help of a number of large contracting firms used by Aetna. The contracting firms did not have any record of the developer.

Routh then performed a quick Google search and found that 23 other large brands also had publicly available mobile apps that used their brand name along with the appended "++." At this point, Routh suspected the app was unauthorized.

Upon further analysis of the app, Routh discovered that the unauthorized app was a copy of Aetna’s official Android app with one difference -- the developer injected code into it. That code requested the GET_ACCOUNTS permission from Android, which allows for viewing what accounts are enabled on a mobile device (e.g., Google, Facebook, Twitter, etc.) through an account manager.

The first screen of the app matched the first screen of the official Android app, and a basic search function listed providers that the company supported. The rest of the app, however, did not function. The developer had republished the unauthorized app to third-party app stores and discussion forums. Users had downloaded the unofficial app more than 175,000 times.

In the unauthorized Aetna++ app, an ad library named com.edealya used the GET_ACCOUNTS permission. The company eDealya claims to help advertisers serve relevant ads to a consumer based on messages posted via a number of social media platforms. In the end, the unauthorized app harvested log-in credentials, and [an article quotes Routh](http://www.clinical-innovation.com/topics/privacy-security/aetna-ciso-risk-based-approach-info-security) as saying the app was, “...a parasite capitalizing on Aetna’s brand equity to make money. This happens all the time.”

## Detecting and remediating an unauthorized mobile app
The same article explains that Routh recommends that in handling and preventing scenarios such as this one, companies need to acquire IT security intelligence from third-party sources, share information with their peers, and also work with state and federal entities.

As part of responding to the incident, Routh reached out to the other 23 affected companies to inform them of the unauthorized apps he found using their brand names. The third party Routh worked with, RiskIQ, also reached out to a number of advertisers to make them aware of their findings.

Obfuscating the code of mobile apps can also help make it more difficult to clone a branded app and insert malicious code into it.
