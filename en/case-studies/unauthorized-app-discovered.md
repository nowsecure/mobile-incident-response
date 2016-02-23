# Unauthorized app discovered 

Counterfeit apps developed by unauthorized parties and published to official or unofficial app stores (and elsewhere on the Internet) can damage a company’s brand name and put their customers at risk. As an incident responder, you may be called upon to investigate an incident involving an unauthorized app:

* Using a company’s brand name without permission
* Targeting the company’s customers
* Interacting with the company’s backend services
* Made available to the public via official app marketplaces or elsewhere on the Internet

## Aetna++ Case Study
In the fall of 2013, insurance provider Aetna’s Chief Information Security Officer (CISO) Jim Routh asked his IT staff for a list of all of the company’s mobile apps. Creating such a list can prove more difficult than it seems because mobile apps tend to proliferate. For example, an ambitious department within the company may hire a third party to develop and release a mobile app without communicating to the larger organization. Subsidiaries, affiliates and even unauthorized entities may publish an app that uses a company’s brand outright (and without explicit permission) or claims association with the company.

Jim chose to work with a third party to help identify mobile apps that used his organization’s brand. The list included approximately 20 apps. Upon reviewing the list, he was not familiar with one app in particular that caught his attention. The app’s name appended two plus signs to the company’s name (i.e., “Aetna++”), which stood out to him.

Initially, the Jim surmised that the app was developed for a marketing campaign. He began his investigation by identifying the developer of the application. The developer’s name was Nayem Junaid, and by reviewing the developer’s LinkedIn profile Jim determined Nayem was a ColdFusion developer at TechnoBrain based in Hydrabad, India. Jim set out to find Nayem in the company’s employee directory but couldn’t find any matches. Next, the he explored whether the developer was a contractor and attempted to locate Nayem with the help of a number of large contracting firms used by his company. The contracting firms did not have any record of the developer.

Jim then performed a quick Google search and found that 23 other large brands also had publicly-available mobile apps that used their brand name along with the appended "++". At this point, the he suspected the app was unauthorized.

Upon further analysis of the app, Jim discovered that the unauthorized app was a copy of Aetna’s official Android app with one difference -- the developer injected code into it. That code requested the GET_ACCOUNTS permission from Android, which allows for viewing what accounts (e.g., Google, Facebook, Twitter, and more) are enabled on a mobile device through an account manager.

In the unauthorized Aetna++ app, an ad library named com.edealya used the permission. The company eDealya claims to help advertisers serve relevant ads to a consumer based on messages posted via a number of social media platforms.

The first screen of the app matched the first screen of the official Android app and a basic search function listed providers that the company supported. The rest of the app, however, did not function. The developer had republished the unauthorized app to third-party app stores and discussion forums. Users had downloaded the unofficial app more than 175,000 times.

The CISO reached out to the other 23 affected companies to inform them of what he had found.
