# A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first Internet worm (dubbed the Morris Worm) and became part of computer security history by:

1. Unleashing the first large scale denial-of-service (DoS) attack on the Internet
2. Impacting an estimated (and refuted) 10 percent of computers on the Internet at that time (6,000 impacted)
3. Being the first person prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response in such a distributed environment led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The goal of the CERT organization was to provide the central hub for communicating and coordinating a response to security incidents. 

The [CERT/CC](https://cert.org/) flourishes today and is part of the Software Engineering Institute at Carnegie Mellon University.

## Goal of incident response
The goal of incident response is to quickly contain and mitigate an incident. A more formal definition of incident response (IR) will be helpful as we continue on in our discussion:

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^2]

## Incident response today (2016)

Today, most large government and enterprise organization have an incident response team. And government regulations increasingly mandate incident response capabilities.

For example, the Federal Financial Institution Examination Council (FFIEC) is a "formal interagency body empowered to prescribe uniform principles, standards, and report forms for the federal examination of financial institutions" [^3] that developed a system dubbed InfoBase to help introduce and educate the financial services industry on items field examiners were inspecting during audits. The [FFIEC's guidance on incident response](http://ithandbook.ffiec.gov/it-booklets/business-continuity-planning/other-policies,-standards-and-processes-/incident-response.aspx) includes a mandate to develop and integrate this discipline into the financial institution's business continuity planning process.

This is only one example of regulated industries required to have incident response plans or capabilities in place.

Other examples include:

* The healthcase industry is beholden to a [HIPAA incident response regulation](http://www.hhs.gov/hipaa/for-professionals/faq/2002/what-does-the-security-rule-require-a-covered-entity-to-do-to-comply/index.html) that "requires a covered entity to implement policies and procedures to address security incidents" 
* The payments industry must comply with [PCI DSS incident response requirements](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3.pdf) [PDF] (section 12.10) that require organizations to "implement an incident response plan," and "Be prepared to respond immediately to a system breach"
* The financial services industry has multiple regulatory acts and bodies overseeing it including the FDIC and [Gramm-Leach-Bliley Act incident response standards](https://www.fdic.gov/regulations/laws/rules/2000-8660.html) that "require the service provider to take appropriate actions to address incidents of unauthorized access to the financial institution's customer information, including notification to the institution as soon as possible of any such incident, to enable the institution to expeditiously implement its response program"
* Federal agencies are regulated under the Federal Information Security Management Act of 2002 that includes [FISMA incident response regulations](http://www.gao.gov/assets/670/662901.pdf) [PDF] requiring agencies to develop, document, and implement an information security program (FISMA Act of 2002, Pub. L. No. 107-347, Title III, Dec. 17, 2002).

## CERT organizations

There is a large group of resources that supporting CERTs around the world. They can be loosely organized into three types based on their sponsors:

1. Government
2. Enterprise
3. Community 

Below is a list of various organizations that often provide extensive information and at times support during an incident.

### Government-sponsored CERTs / CSIRTs

These organizations generally coordinate incident response for entire nations. 

1. [US-CERT](https://www.us-cert.gov/) (United States Computer Emergency Readiness Team)
1. [ENISA](https://www.enisa.europa.eu/) (European Union Agency for Network and Information Security)
1. [CERT](https://www.cert.org/) (CERT Division is located within the Software Engineering Institute, a federally funded research and development center at Carnegie Mellon University, the majority of their work contributes to government and national security efforts)
1. [CNCERT/CC](http://www.cert.org.cn/publish/english/index.html) (National Computer Network Emergency Response Technical Team/Coordination Center of China)

### Enterprise-sponsored CERTs / CSIRTs

These organization, while focused on a particular enterprise, have a visibile public presence and sometimes support the industry with educational information and tools:

1. [Microsoft Security Response Center](https://technet.microsoft.com/en-us/security/dn528958)
1. [Apple Product Security](https://www.apple.com/support/security/)
1. [Facebook Security](https://www.facebook.com/security)
1. [Google Application Security](https://www.google.com/about/appsecurity/)
1. [Android Security](https://source.android.com/security/index.html)

### Community

These organization provide various resources to the incident response community including threat reporting, training, certifications, conferences, and research. 

1. [FIRST](http://www.first.org/) (global Forum for Incident Response and Security Teams) 
1. [SANS Institute](https://www.sans.org/about/)
1. [Internet Storm Center](https://isc.sans.edu/) (part of SANS)

The FIRST website maintains a [contact list of incident response teams](https://www.first.org/about/organization/teams) at participating member organizations. Please note, leveraging this list for marketing is strictly prohibited. 

## Digital forensics and incident response

Incident response is closely connected with digital forensics as nearly every incident requires the collection, storage, and analysis of digital evidence.

As you explore mobile incident response more thoroughly, below are some mobile forensic resources what may be helpful:

* [Linux for Mobile Forensics](https://info.nowsecure.com/linux-101-forensics-training-download) - free training
* [JTAG for Mobile Forensics](https://info.nowsecure.com/jtag-forensics-training-download) - free training
* [Santoku Linux](https://santoku-linux.com/) - free Linux distro for mobile forensics

#### Footnotes

[^1]: https://en.wikipedia.org/wiki/Morris_worm
[^2]: What is incident response? Definition from WhatIs.com. Wed. Wed Nov 11 2015. <http://searchsecurity.techtarget.com/definition/incident-response>.
[^3]: http://ithandbook.ffiec.gov

