<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
  <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
</div>

# A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first Internet worm (dubbed the Morris Worm) and became part of computer security history by:

1. Unleashing the first large scale denial-of-service (DoS) attack on the Internet
2. Impacting an estimated (and refuted) 10% of computers on the Internet at that time (6,000 impacted)
3. Being the first person prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response in such a distributed environment led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The goal of the CERT organization was to provide the central hub for communicating and coordinating a response to security incident. 

The [CERT/CC](https://cert.org/) flourishes today and is part of the Software Engineering Institute at Carnegie Mellon University.

## Goal of Incident Response
The goal of incident response is to quickly contain and mitigate an incident. It is helpful to provide a more formal definition of incident response ("IR"):

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^2]

## Incident Response Today (2016)

Today, most large government and enterprise organization have an incident response team. And government regulations increasing include mandates for incident response capabilities.

For example, the Federal Financial Institution Examination Council (FFIEC) is a "formal interagency body empowered to prescribe uniform principles, standards, and report forms for the federal examination of financial institutions" [^3] that developed a system dubbed InfoBase to help introduce and educate the financial services industry on topics that the their field examiners inspect during audits. The [FFIEC's guidance on incident response](http://ithandbook.ffiec.gov/it-booklets/business-continuity-planning/other-policies,-standards-and-processes-/incident-response.aspx) includes a mandate to develop and integrate this discipline into their the financial instituions business continuity planning process.

This is simply one example of regulated industries which have incident response mandates. Other examples include:

* The healthcase industry includes a [HIPAA incident response regulation](http://www.hhs.gov/hipaa/for-professionals/faq/2002/what-does-the-security-rule-require-a-covered-entity-to-do-to-comply/index.html) that "requires a covered entity to implement policies and procedures to address security incidents" 
* The payments industry regulation via [PCI DSS incident response requirements](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3.pdf) [PDF] (section 12.10) that requires organizations to "implement an incident response plan. Be prepared to respond immediately to a system breach"
* The financial services industry has multiple regulatory acts and bodies overseeing them, including the FDIC and [Gramm-Leach-Bliley Act incident response standards](https://www.fdic.gov/regulations/laws/rules/2000-8660.html) "require the service provider to take appropriate actions to address incidents of unauthorized access to the financial institution's customer information, including notification to the institution as soon as possible of any such incident, to enable the institution to expeditiously implement its response program."
* Federal agencies are regulated under the Federal Information Security Management Act of 2002. [FISMA incident response regulation](http://www.gao.gov/assets/670/662901.pdf) [PDF] requires agencies to develop, document, and implement an information security program. (see FISA Act of 2002, Pub. L. No. 107-347, Title III (Dec. 17, 2002)).

## CERT Organizations

There is a large group of resources that support CERTs around the world. They can be loosely organized into three types based on their sponsors:

1. Government
2. Enterprise
3. Community 

Below is a list of various organizations which often provide extensive information and at times support during an incident.

### Government-sponsored CERTs / CSIRTs

These organizations generally coordinate incident responses for entire nations. 

1. [US-CERT](https://www.us-cert.gov/) (United States Computer Emergency Readiness Team)
1. [ENISA](https://www.enisa.europa.eu/) (European Union Agency for Network and Information Security)
1. [CERT](https://www.cert.org/) (CERT Division is located within the Software Engineering Institue, a federally funded research and development center at Carnegie Mellon University, the majority of our work contributes to government and national security efforts.)
1. [CNCERT/CC](http://www.cert.org.cn/publish/english/index.html) (National Computer Network Emergency Response Technical Team/Coordination Center of China)

### Enterprise-sponsored CERTs / CSIRTs

These organization, while focused on a particular enterprise, have a visibile public presence and sometimes include supporting the industry with educational information and tools:

1. [Microsoft Security Response Center](https://technet.microsoft.com/en-us/security/dn528958)
1. [Apple Product Security](https://www.apple.com/support/security/)
1. [Facebook Security](https://www.facebook.com/security)
1. [Google Application Security](https://www.google.com/about/appsecurity/)
1. [Android Security](https://source.android.com/security/index.html)

### Community

These organization provide various resources to the incident response community including threat reporting, training, certifications, conferences and research. 

1. [FIRST](http://www.first.org/) (global Forum for Incident Response and Security Teams) 
1. [SANS Institute](https://www.sans.org/about/)
1. [Internet Storm Center](https://isc.sans.edu/) (part of SANS)

The FIRST website maintains a [contact list of incident response teams](https://www.first.org/about/organization/teams) at participating member organization. Please note, leveraging this list for any marketing initiative is strictly prohibited. 

## Digital Forensics and Incident Response

Incident response is closely connected with digital forensics as nearly every incident requires the collection, storage and analysis of digital evidence.  

As you explore mobile incident response more thoroughly, below are some mobile forensic resources what may be helpful:

* [Linux for Mobile Forensics](https://info.nowsecure.com/linux-101-forensics-training-download) - free training
* [JTAG for Mobile Forensics](https://info.nowsecure.com/jtag-forensics-training-download) - free training
* [Santoku Linux](https://santoku-linux.com/) - free Linux distro for mobile forensics

#### Endnotes

[^1]: https://en.wikipedia.org/wiki/Morris_worm
[^2]: What is incident response? Definition from WhatIs.com. Wed. Wed Nov 11 2015. <http://searchsecurity.techtarget.com/definition/incident-response>.
[^3]: http://ithandbook.ffiec.gov

