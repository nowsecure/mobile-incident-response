<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
    <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
  <a class="cta-banner-update" href="https://www.blackhat.com/us-16/training/mobile-incident-response-ir-for-android-and-ios.html">&nbsp;Mobile IR Training @ Black Hat&nbsp;<i class="fa fa-external-link"></i></a>
</div>

# Incident response process

The [SANS Institute](https://www.sans.org/) has defined six key IR steps in their book [Computer Security Incident Handling: Step-by-Step](http://www.amazon.com/Computer-Security-Incident-Handling-Step-/dp/0972427376/ref=sr_1_1?ie=UTF8&qid=1436392071&sr=8-1&keywords=Computer+Security+Incident+Handling%3A+Step-by-Step):

1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons learned

While we will cover this topic extensively in the chapter [Framework for Mobile Incident Response](mobile-incident-response-framework.md) and build upon frameworks from both SANS and NIST, we'd like to discuss this process here at a high level and relate it to mobile specifically.

## Preparation
Preparing for a mobile incident involves a number of steps. First, in order to determine the risks that exist within an organization today, a mobile threat assessment should be performed. Part of this threat assessment involves identifying mobile assets on the corporate network. Mobile assets include devices, operating system versions running on those devices, and applications installed on those devices if available. This inventory should then be correlated with mobile security intelligence. That intelligence will include device vulnerabilities, operating system vulnerabilities, information about leaky and insecure apps, known malware, and other risks such as known malicious Wi-Fi networks. The last step of the mobile threat assessment is mitigating the risk identified as a result of your inventory and correlation with threat data. Once you've collected intelligence from the mobile devices on your network, analyze that data to identify security risks, eliminate low hangout fruit, address risk that is unacceptable to your organization, document remaining risks, and prepare IR playbooks for each scenario.

Building your mobile IR tool box is another criticial step in the preparation process.  When an incident occurs, your team needs to be prepared with a list of tools that are specific to mobile. Chapter 2 - [Tools for Mobile Incident Response](../tools/README.md) - goes into detail about different categories of mobile IR tools, lists suggested tools, and provides instructions on how to setup a mobile IR workstation.

Finally, you cannot fully be prepared without defining and documenting a process, and developing playbooks for each type of mobile threat scenario. Once you've developed your documentation and prepared a workstation with pre-installed tools, preparation should not stop there. The very best way to be prepared for an incident is practice and repetition. In a later chapter, we will provide you with sample scenarios where you can walk through some practice labs.


## Identification
Identification of an incident can occur in several ways. There are varying device indicators of compromise (IOC) depending on the type of mobile incident. In some cases, a system administrator may observe increased battery drain, unusual network traffic, or certificate errors. Many times, a user may report an incident when noticing something strange occurring on their device.

Another type of mobile incident may be indentified by mobile app reputation services (MARS). MARS scour app stores (official and third-party) and the Internet for mobile apps using a company's brand name. If an organization is alerted to unauthorized use of their brand in a mobile app or sees unknown apps connecting to their transactional servers, this might indicate an incident relating to mobile apps.


## Containment
Once you have identified and logged an incident, it must be contained. It is preferable to have physical access to the device, which can be a challenge with mobile. If access to the device is obtained, baseline information should be captured including type of device, operating system version, and a list of installed apps. If appropriate, network analysis should also be considered. The full forensic acquisition of the device should then be performed before containing the incident by isolating the device from the network.

## Eradication 
Artifacts collected from the mobile device, router, or network packet capture must then be analyzed in an effort to determine whether the threat can be removed. At this step, it is important to identify all impacted users or devices, remove the threat, and/or wipe corporate data if necessary.  

## Recovery
Steps should then be taken to bring any systems that were shut down during the incident back online. This includes re-provisioning mobile devices. The recovery process should also include ensuring attacker didn't move laterally within your organization and pro-actively monitoring accounts and systems connected to the impacted mobile device and impacted users.  During this phase, the effectiveness of social engineering attacks is greatly increased, so ensure that your employees are properly educated and trained in this area.


## Lessons learned
The final step in the IR process is just as important as those before it. The purpose of the lessons learned phase is to summarize what went wrong, what worked, and most importantly, what can be improved. A debrief with the team should take place to identify recommended policies and procedures changes and user education.  The team should discuss the indicators of compromise and determine how to best inoculate against future attacks by focusing on anomaly detection as well as shared insights and cross-referencable data available publicly or from other organizations.

