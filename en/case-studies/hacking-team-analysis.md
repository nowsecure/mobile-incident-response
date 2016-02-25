<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
  <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
</div>

# Hacking Team 

One challenge incident response, and more broadly security, teams face is providing the business case for investing in the necessary people, tools, training and process. This section includes information about the compromise of the notorious company Hacking Team to acheive the following:

* Provide empirical evidence that nation-states and malicious actors target mobile devices 
* Explain that there exists a market willing to pay for the ability to compromise mobile devices
* Demonstrate that vulnerabilities, technologies and companies exist that make mobile compromise possible.

Case studies such as this one will help you in making the business case for investing in mobile security and incident response.

## Hacking Team background
The Milan, Italy-based company Hacking Team markets surveillance software, called Remote Control System (RCS), to government and law enforcement agencies. The system allows a user to launch exploits against targets (including desktop computers, laptops, and mobile devices), deliver payloads, and remotely control compromised systems and/or exfiltrate data from those systems. Among other features, RCS can monitor and record communications, decipher encrypted data, and remotely activate microphones and cameras. Many people have criticized Hacking Team for selling their software to [repressive governments that violate basic human rights](https://theintercept.com/2015/07/07/leaked-documents-confirm-hacking-team-sells-spyware-repressive-countries/) and use the software to spy on citizens, activists, and journalists. Predictably, Hacking Team vehemently denied these allegations, but as the raw data and analysis definitively proves, Hacking Team was very much engaged in selling exploits to anyone who had the means to purchase them.

## Company compromise
On July 5, 2015, an allegedly unauthorized individual took control of Hacking Team’s Twitter account and posted a message stating, "Since we have nothing to hide, we’re publishing all our e-mails, files, and source code" and including a link to more than 400 GB of internal Hacking Team data. The files included company emails, customer data, and source code among other things.

The data showed that Hacking Team also sold software to private companies and [in one case](https://twitter.com/netik/status/617916052052144128) for the purposes of surveilling Android and Blackberry mobile devices. In order to install the RCS software on a targeted device without the user’s knowledge, a vulnerability on that device would need to be exploited. Emails reveal that Hacking Team recruited exploit developers and also purchased exploits that paved the way for installation of the RCS software.

In addition, [an archive of the leaked emails](https://wikileaks.org/hackingteam/emails/) provided by WikiLeaks includes an [email stating that Hacking Team worked on developing an exploit for a vulnerability in a version of the SwiftKey keyboard](https://wikileaks.org/hackingteam/emails/emailid/1028689) shipped with several Samsung Galaxy models. The email states, "Is it really exploitable? Yes. Are WE working on it? Obviously," and includes a link to an Ars Technica article, ["New exploit turns Samsung Galaxy phones into remote bugging devices](http://arstechnica.com/security/2015/06/new-exploit-turns-samsung-galaxy-phones-into-remote-bugging-devices/)," about the vulnerability discovered by NowSecure researcher Ryan Welton.

Source code allegedly recovered from the leaked data and [posted on GitHub](https://github.com/hackedteam?tab=repositories) includes RCS agents for Android, Blackberry, iOS, and Windows Phone. These agent’s capabilities included the ability to take pictures, copy events from calendars, and intercept communications such as, phone calls, SMS messages, and chat messages from apps like Skype and WhatsApp.

It was also revealed that Hacking Team possessed an Apple enterprise certificate. [Reports claim](http://www.ibtimes.co.uk/masque-attack-returns-hacking-team-leveraged-ios-vulnerability-install-fake-messaging-apps-1514317) that apps created by Hacking Team and signed with this certificate could be installed on even non-jailbroken iOS devices. This allowed Hacking Team to develop and distribute custom apps outside of the Apple App Store and without going through the typical Apple review process. Researchers found in one case that Hacking Team had created spyware hidden in the native Apple Newsstand app. 
