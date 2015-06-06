# Mobile Incident Response

This chapter will explore the basic ideas behind incident response including a brief history, the process, how to incorporate mobile technology and well as common incidents you are likely to encounter.

# What is Mobile Incident Response

## A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first worm on the Internet and became part of computer security history in several infamous ways:

1. Unleashed the first large scale denial-of-service (DoS) attack on the Internet
2. Impacted an estimated (and refuted) 10% of computers on the Internet at that time (6,000 impacted computers)
3. First person to be prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The [CERT/CC](https://cert.org/) flourishes today and is part of the  Software Engineering Institute at Carnegie Mellon University. 

## Defining Incident Repsonse

It's helpful to define incident response:

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^2] 

Closely connected with mobile forensics. Mention (at least) AWH's 2 existing books?

Mention SANS 6 steps?

1. Preparation
2. Identification
3. Containment
4. Eradication
5. Recovery
6. Lessons learned

Mention NIST "Computer Security Incident Handling Guide" framework?

This will be covered more full in the Chapter "Framework for Mobile Incident Response" (how to make this an internal link?)

## How is mobile IR different than traditional computers?

Mobile is different. Duh!

# Common Mobile Incidents
There are a number of common scenarios you will encounter when it performing IR for mobile devices:

* Internal investigation
* Malware discovered
* Device acting suspiciously

# Running reference notes

- http://www.cert.org/incident-management/csirt-development/csirt-faq.cfm?
- http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf

#Citations

Let's mimic what [Wikipedia does for citations](http://en.wikipedia.org/wiki/Robert_Tappan_Morris#References). We can use their style (MLA?) and then either the ^1 approach for a footnote or just the id in brackets. The disadvantage is we might have to manually re-number links. I'm open to other ideas!

[^1]: http://www.ietf.org/rfc/rfc2350.txt (appendix c)
[^2]: Rouse, Margaret. "What Is Incident Response?" SearchSecurity. TechTarget, Inc, Sept. 2005. Web. 03 June 2015. <http://searchsecurity.techtarget.com/definition/incident-response>