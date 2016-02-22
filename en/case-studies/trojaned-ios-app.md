# Trojaned iOS app installs

This case study will examine the conditions leading up to, techniques used and impacts of an attacker installing tojaned versions of iOS apps on a target's iPhone.

## Apple's Walled Garden

Apple tightly controls the iOS ecosystem, in particular how apps are distributed via the App Store. While this has lead to some frustration from app developers, tinkerers and security researchers, it has certainly reduced the impacts on malicious apps as it's very difficult to install them on traget devices. An app needs to either be distributed via the App Store or signed with special certificate issued by Apple to a developers and then loaded onto thei device via iTunes or a special link but requiring user confirmation. Contrast this to Android where developers have many distribution channels and device owners can configure the device to install "untrusted" apps.

If an attacker wants to install malicious apps on a target's iPhone, they either need to trick the user into accepting the Developer Signed application or gain physical access to the device to install the app directly.

## iPhone Frenzy
In September 2014, Apple released the iPhone 6 and 6 Plus to the public. As with previous iPhone releases, the device was highly anticiapted and soght after. In the United States, that meant either waiting in long lines or being back ordered for a few weeks.

However, in foreign countries it is far more difficult to acquire a recent iPhone. Demand is extremely high and people are will to pay significant premiums to aacquire a device. A new iPhone is also a status symbol so often time successful business executives or government officials will be the reciepient of a new device. This could be a device they purchased, often usinf their connections, or simply a gift.

## Conditions for compromise
The iPhone frezy presented a perfect opportunity to target an successful individual. The attacker knew of the individuals desire for a new iPhone 6 and took advantage of the situation.

The attacker purchased an iPhone 6 and while they have physical possession, they setup the device for the individual. This was likley viewed as a sign of courtesy so the successful individual could begin using the device as soon as they recieved it.

Since the attacker had physical access to the device, they created trojaned versions of popular apps and installed them on the device for the individual including:

* Chrome
* Skype
* Facebook

The apps targeted and collected sensitive data from the device and sent the data back to the attacker via their command and control (C2) servers.
