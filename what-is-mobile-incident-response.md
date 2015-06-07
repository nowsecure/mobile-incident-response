# Mobile Incident Response

This chapter will explore the basic concepts behind incident response including a brief history, the process, how to incorporate mobile technology and well as common incidents you are likely to encounter.

# What is Mobile Incident Response

## A brief history of incident response
On November 2, 1998, Robert Tappan Morris released the first worm on the Internet (dubbed the Morris Worm) and became part of computer security history in several infamous ways:

1. Unleashed the first large scale denial-of-service (DoS) attack on the Internet
2. Impacted an estimated (and refuted) 10% of computers on the Internet at that time (6,000 impacted)
3. First person prosecuted under the Computer Fraud and Abuse Act (CFAA)

The impact to the Internet plus the significant challenges in coordinating a response led to the creation of the Computer Emergency Response Team Coordination Center (CERT/CC) by DARPA in 1988.[^1] The [CERT/CC](https://cert.org/) flourishes today and is part of the  Software Engineering Institute at Carnegie Mellon University. 

## Defining Incident Response

It's helpful to define incident response ("IR"):

>Incident response is an organized approach to addressing and managing the aftermath of a security breach or attack (also known as an incident). The goal is to handle the situation in a way that limits damage and reduces recovery time and costs. An incident response plan includes a policy that defines, in specific terms, what constitutes an incident and provides a step-by-step process that should be followed when an incident occurs. [^2] 

While this will be covered more fully in chapter [Framework for Mobile Incident Response](mobile-incident-response-framework.md), it's helpful to start with this definition so we can clearly identify the goals of this book:

1. Demonstrate how mobile devices are attacked
2. Identify tools and processes required upfront to effectively address mobile incidents
3. Annotate NIST's "Computer Security Incident Handling Guide" with regards to mobile
4. Provide step-by-steps examples of mobile incident response through case studies and labs
5. Discuss remediation and prevention techniques 

Incident response is closely connected with digital forensics as nearly every incident requires the collection, storage and analysis of evidence.  This is a topic the authors and NowSecure employees have written about extensively since 2011:

1. [Android Forensics: Investigation, Analysis and Mobile Security for Google Android](http://www.amazon.com/Android-Forensics-Investigation-Analysis-Security/dp/1597496510) by Andrew Hoog
2. [iPhone and iOS Forensics: Investigation, Analysis and Mobile Security for Apple iPhone, iPad and iOS Devices](http://www.amazon.com/iPhone-iOS-Forensics-Investigation-Analysis/dp/1597496596/ref=pd_bxgy_14_img_y) by Katie Strzempka and Andrew Hoog
3. [Hacking and Securing iOS Applications: Stealing Data, Hijacking Software, and How to Prevent It](http://www.amazon.com/Hacking-Securing-iOS-Applications-Hijacking/dp/1449318746/ref=sr_1_1?s=books&ie=UTF8&qid=1433593160&sr=1-1&keywords=Hacking+and+Securing+iOS+Applications) by Jonathan Zdziarski
3. [Android Security Cookbook](http://www.amazon.com/Android-Security-Cookbook-Keith-Makan/dp/1782167161/ref=sr_1_1?s=books&ie=UTF8&qid=1433593041&sr=1-1&keywords=Android+Security+Cookbook) with co-author Scott Alexander-Bown
4. [Android Hacker’s Handbook](http://www.amazon.com/Android-Hackers-Handbook-Joshua-Drake/dp/111860864X/ref=sr_1_1?s=books&ie=UTF8&qid=1433593102&sr=1-1&keywords=Android+Hacker%E2%80%99s+Handbook) with co-author Pau Oliva Fora

As you explore mobile incident response more thoroughly, these books can provide far deeper technical details on mobile forensics and security.

## How is mobile IR different than traditional computers-focused IR?

Mobile is different than traditional computers (desktops, laptops and servers) for several reasons:

1. Built for individuals
2. Explosive growth
3. Always connected
4. Large attack surface
5. App store model

We will explore these differences in depth in the [Attacking Mobile Devices](mobile-attacks.md) chapter however each of these differences ultimately add up to enough to create a paradigm shift from traditional computer-based IR.


# Common Mobile Incidents
There are a number of common scenarios you will encounter when it performing IR for mobile devices:

* Internal investigation
* Malware discovered
* Device acting suspiciously

# Running reference notes

- http://www.cert.org/incident-management/csirt-development/csirt-faq.cfm?

#Citations

Let's mimic what [Wikipedia does for citations](http://en.wikipedia.org/wiki/Robert_Tappan_Morris#References). We can use their style (MLA?) and then either the ^1 approach for a footnote or just the id in brackets. The disadvantage is we might have to manually re-number links. I'm open to other ideas!

[^1]: http://www.ietf.org/rfc/rfc2350.txt (appendix c)
[^2]: Rouse, Margaret. "What Is Incident Response?" SearchSecurity. TechTarget, Inc, Sept. 2005. Web. 03 June 2015. <http://searchsecurity.techtarget.com/definition/incident-response>