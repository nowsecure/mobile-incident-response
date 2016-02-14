# A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first Internet worm (dubbed the Morris Worm) and became part of computer security history by:

1. Unleashing the first large scale denial-of-service (DoS) attack on the Internet
2. Impacting an estimated (and refuted) 10% of computers on the Internet at that time (6,000 impacted)
3. Being the first person prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response in such a distributed environment led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The goal of the CERT organization was to provide the central hub for communicating and coordinating a response to security incident. 

The [CERT/CC](https://cert.org/) flourishes today and is part of the Software Engineering Institute at Carnegie Mellon University.

## Incident Response Today (2016)

Today, most large government and enterprise organization have an incident response team. And government regulations increasing include mandates for incident response capabilities.

For example, the Federal Financial Institution Examination Council (FFIEC) is a "formal interagency body empowered to prescribe uniform principles, standards, and report forms for the federal examination of financial institutions" [^2] that developed a system dubbed InfoBase to help introduce and educate the finacial services industry on topics that the their field examiners inspect during audits. The [FFIEC's guidance on incident response](http://ithandbook.ffiec.gov/it-booklets/business-continuity-planning/other-policies,-standards-and-processes-/incident-response.aspx) includes a mandate to develop and integrate this discipline into their the financial instituions business continuity planning process.

This is simply one example of regulated industries which have incident response mandates. Other examples include:

* The healthcase industry includes a [HIPAA incident response regulation](http://www.hhs.gov/hipaa/for-professionals/faq/2002/what-does-the-security-rule-require-a-covered-entity-to-do-to-comply/index.html) that "requires a covered entity to implement policies and procedures to address security incidents" 
* The payments industry regulation via [PCI DSS incident response requirements](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3.pdf) [PDF] (section 12.10) that requires organizations to "implement an incident response plan. Be prepared to respond immediately to a system breach"
* The financial services industry has multiple regulatory acts and bodies overseeing them, including the FDIC and [Gramm-Leach-Bliley Act incident response standards](https://www.fdic.gov/regulations/laws/rules/2000-8660.html) "require the service provider to take appropriate actions to address incidents of unauthorized access to the financial institution's customer information, including notification to the institution as soon as possible of any such incident, to enable the institution to expeditiously implement its response program."
* Federal agencies are regulated under the Federal Information Security Management Act of 2002. [FISMA incident response regulation](http://www.gao.gov/assets/670/662901.pdf) [PDF] requires agencies to develop, document, and implement an information security program. (see FISA Act of 2002, Pub. L. No. 107-347, Title III (Dec. 17, 2002)).

## CERT Organizations

There is a large group of resources support CERTs around the world. They can be loosly organized into three types based on their sponsors:

1. Government
1. Enterprise
1. Community 

Below is a list of various organizations which often provide extensive information and at times support during an incident.

### Government-sponsored CERTs / CSIRTs

These organizations generally coordinate incident responses for entire nations. 

1. [US-CERT](https://www.us-cert.gov/) (United States Computer Emergency Readiness Team)
1. [ENISA](https://www.enisa.europa.eu/) (European Union Agency for Network and Information Security)

### Enterprise-sponsored CERTs / CSIRTs

These organization, while focused on a particular enterprise, have a visibile public presence and sometimes include supporting the industry with educational information and tools:

1. MSFT?
1. Does CMU Cert go here? Create .edu one?

### Community

1. [FIRST](http://www.first.org/) (global Forum for Incident Response and Security Teams) 
 

## Digital Forensics and Incident Response

Incident response is closely connected with forensics as nearly every incident requires the collection, storage and analysis of digital evidence.  

As you explore mobile incident response more thoroughly, these books can provide far deeper technical details on mobile forensics and security.

[^1]: https://en.wikipedia.org/wiki/Morris_worm
[^2]: http://ithandbook.ffiec.gov

