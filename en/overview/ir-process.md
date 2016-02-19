# Incident Response Process

The [SANS Institute](https://www.sans.org/) has defined 6 key IR steps in their book [Computer Security Incident Handling: Step-by-Step](http://www.amazon.com/Computer-Security-Incident-Handling-Step-/dp/0972427376/ref=sr_1_1?ie=UTF8&qid=1436392071&sr=8-1&keywords=Computer+Security+Incident+Handling%3A+Step-by-Step):

1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons learned

While we will cover this topic extensively in the chapter [Framework for Mobile Incident Response](mobile-incident-response-framework.md) and build upon frameworks from both SANS and NIST, we'd like to discuss this process here at a high level and how it relates to mobile.

## Preparation
Preparing for a mobile incident involves a number of steps. First, in order to determine the risks that exist within an organization today, a mobile threat assessment should be performed. This threat assessment would involve identifying mobile assets on the corporate network, including devices, the operating system versions their running, and list of installed applications if available. This inventoried information should then be correlated with mobile security intelligence to determine vulnerabilities in devices, OS versions, leaky and insecure apps, known malware, or other risks such as malicious WiFi networks. The last step of the mobile threat assessment should be to Work the problem. Once you've collected intelligence from the mobile devices on your network, analyze that data to identify security risks, eliminate low hangout fruit, address risk that is unacceptable to your organization, document remaining risks, and prepare playbooks for each scenario.

Building your mobile IR tool box is another criticial step in the preparation process.  When an incident occurs, your team needs to be prepared with a list of tools that are specific to mobile. Chapter 2 - [Tools for Mobile Incident Response](HOW DO I LINK TO CHAPTER?) goes into depth on different categories of mobile IR tools, a list of suggested tools, and instructions on how to setup a mobile IR workstation.

Finally, you cannot fully be prepared without defining and documenting a process, and develop playbooks for each type of mobile threat scenario. Once you've developed your documentation and prepared a workstation with pre-installed tools, the preparation should not stop there. The very best way to be prepared for an incident is practice and repetition. In a later chapter, we will provide you with sample scenarios where you can walk through some practice labs.


## Identification
Identification of an incident can occur in several ways. There are varying device indicators of compromise (IOC) depending on the type of mobile incident. In some cases, a system administrator may observe increased battery drain, unusual network traffic or certificate errors. Many times, an incident may also be reported by the user, with something strange happening on their device.

Another type of mobile incident may involve mobile application reputation monitoring. If an organization observed unauthorized use of their brand or see unknown apps connecting to their transactional servers, that could indicate an incident as it relates to mobile apps.


## Containment
Once you have identified and logged an incident, it must be contained. It is preferable to have physical access to the device. If this is the case, baseline information should be captured including type of device, OS version, and list of installed apps. If appropriate, network analysis should also be considered. The full forensic acquisition of the device should then be performed before isolating it from the network to contain the problem.

## Eradication 
NEED TO UPDATE
Analyze attack artifacts, determine if threat can be removed, identify all impacted (if malware on app store), remove threat or wipe corporate data.

## Recovery
NEED TO UPDATE
* Re-provision mobile devices
* Ensure attacker didn't move laterally within your organization
* Monitor accounts and systems connected to mobile device and impacted user(s)
  * Effectiveness of social engineering attacks is greatly increased

## Lessons Learned
NEED TO UPDATE
* Determine IOCs
  * Attribution
  * Share threat intel data
* Inoculate against future attacks
  * Static signatures generally ineffective
  * Focus on anomaly detection
  * Shared insights and cross-referanceable data


