# Case Studies

Theory is great, but we often learn by example. This chapter will provide real-world case studies for common incident response scenarios you are likely to encounter. These scenarios include:

* CEOs phone is acting odd
* Mobile malware discovered on app stores
* Trojaned iOS app installs
* Internal investigation

## CEOs phone is acting weird

## Mobile malware discovered on app stores
In the fall of 2013, Jim Routh (Chief Information Security Officer at insurance giant Aetna) asked his staff to provide a list of all Aetna's mobile apps. 

This is often a surprising difficult question for a large organization to answer. Mobile apps tend to proliferate. An ambitious department within the company could hire a 3rd party developer and release a mobile app. Subsidiaries, affiliates and even unauthorized entities may publish an app that involved your company.

Ultimately, Jim worked with a third party to help identify his mobile applications. The resulting list was about 20 apps and Jim reviewed the list.

He identified an app that he was not familiar with. The name of app, Aetna++, stood out to Jim. His initial thought was that the app was developed for a marketing campaign. 

Jim decided to see who developed the application. He found that the developer was Nayem and based on his LinkedIn profile, we was a ColdFusion developer based in Hydrabad, India. He looked Nayem up in the employee directory but was unable to find him. Jim's next thought was that Nayem might be a contractor and he attempted to locate with the help of large contracting firms Aetna used. But he was still unable to locate Nayem.

At this point, Jim decided he needed to look at this from a different lens - Google. A quick Google search revealed 23 other large brands had a mobile app that used their name with a "++" appended after it. At this point, Jim suspected the app was unauthorized. 

The Aetna++ app was a clone of his existing Android app. However, the developer injected malicious code into the app and then re-deployed it to 3rd party app stores and via discussion boards.

The app, downloaded over 175,000 times, copied the 1st screen of the official Aetna app but the rest of the app was non-functioning. It also allowed a basic search for Providers that Aetna supported.


`He contacted the other 23 impacted companies and while some did not respond, many did. Then Jim had the app downloaded and analyzed.`

## Trojaned iOS app installs

## Internal investigation

