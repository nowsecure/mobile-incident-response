# How is mobile IR different than traditional computers-focused IR?

While the generalized incident response process should largely not need to change to incorporate new technologies, there are unique properties of mobile devices and operating systems that pose unique challenges.

## Individual Consumer Technology

Mobile devices, unlike computers and servers, were built for individual consumers. Since individuals by definition are not concerned with managing a large number of devices, many key IT management and security requirements were not built into the devices.

Notably, individual and enterprises do not have administrative (root) access to the devices. Can't monitor. Can't develop nearly as effective tools. Race2root.

Oh, and the OS developers, OEM and wireless carriers all have the ability to get system/root access with their preinstalled apps so tons of other have access, just not you or the enterprise. And check out some of the things they do (Samsung keyboard flaw? 100s of other examples?)

Put my Learn to Love the Root spiel here?

Mention that we can't do effective mobile app security testing without root (thx Apple)?  And recognize that attackers have pretty much always found ways to get root?

Lack of visibility and tools on these devices means that an enormous amount of our data is being extracted (and often done insecurely) and the people most impacted (the individuals and the enterprises they interact with as employees or customers) have no effective visibility to this happening.

## Application Sandbox

Define application sandbox, mobile architecture

Installable applications, due to the sandbox, cannot truly protect the device due to security restrictions. This made nearly all previously  PC-based approaches to security ineffective:

* Anti-virus / Anti-malware
* DLP
* ...

## Explosive Growth

*** show chart from Ben Evans we use in our decks ***
The security industry didn't have time to mature given the explosive growth, and amplified by the new architecture and sandbox limitations.

## Connected Devices

Unlike laptops and desktops, mobile devices are almost always connected to the Internet.  They are rarely greater than 6 feet from their owner (even at night...try to find that study).  They connect to both mobile and Wi-Fi networks and other technologies exist such as bluetooth.

*** The average mobile phone (based on NS data) connected to 160 IP address a day and N countries. Show some data on where traffic is going, how much is encrypted, etc? ***

## Large Attack Surface

Mobile devices have a large attack surface. *** include mobile attack graph we have ? ***
*** Include the mobile exploitation graph we have? ***
*** include graph we have with # of actors involved in mobile devices? ***

We will explore these differences in depth in the [Attacking Mobile Devices](mobile-attacks.md) chapter.

## App store model

Do you remember when we used to install applications via CD-ROM? 3.5in floppy disks? 5 1/4? Further back than that? :-D

Well, today we generally take for granted that the App Store model has drastically changed how we install software and who develops that software.

The barrier of entry is much lower...anyone could be writing these apps. Big companies (who hopefully invest in security and QA but often don't), individuals or small companies intent to develop the next killer app or even amateurs or malicious parties that now have an incredibly effective delivery engine.

*** The average Android device in the US ships with ___ # of apps pre-installed. You can't uninstall many of them. You can disable many of them. Many of them have security and privacy flaws ***

It has never been easier to install an application on a computing device.

These differences ultimately add up sufficiently to create a paradigm shift from traditional computer-based IR.
