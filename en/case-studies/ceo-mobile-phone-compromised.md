<div class="cta-banner">
  <a class="cta-banner-pdf" href="https://info.nowsecure.com/IRforAndroidandiOS_PDFRequest.html">Read PDF<i class="fa fa-file-pdf-o"></i></a>
  <a class="cta-banner-update" href="https://info.nowsecure.com/IRforAndroidandiOS_Updates.html">Receive Updates<i class="fa fa-bell-o"></i></a>
</div>

# Compromise of company executive's phone
One of the likely mobile device scenarios an incident response analyst will encouter is the potential compromise of an executive's phone. Mobile devices have become very personal and individuals are acutely aware of minor changes in the device behavior. When a mobile device is acting oddly, it is likely that company executives will turn the device over to the security team fofr investigation.

These are incredibly challenging cases since there are so many factors that could cause a device to act in a different manner. Very few orginaztions have the [continual analysis tools](../tools/mobile-ir-tool-categories.md) in place to help understand how the device state changed.

And finally, company executives tend to be incredibly busy, mobile and often times impatient. This is clearly an area where incident response teams want to ensure they have the proper tools and training in place to quikly identify and remediate incidents.

## Invalid email certificate
The CEO and the Co-founder of a technology company experienced problems syncing their email over a weekend in early 2016. When the iOS Mail app was launched, it would intermittently throw a certificate error. In this particular case, the CEO was technical and actually captured screenshots which are very help to help determine the sepcific errors encounered:

>Cannot Identify Server Identity

>The identity of "imap.gmail.com" cannot be verified by Mail. Review the certificate details to continue.

![Certificate Error on iOS Mail](../assets/iOS-Mail-Certificate-Error.jpg)

The Gmail app for iOS would not sync email as well but it dropped the connection silently.

The certificate was self signed and had a common name of "servers.afyonn.com" and was set to expire in Oct 2016:

![Self Signed Certificate presented to iOS Mail](../assets/servers-afyonn-com-certificate-error.png)

## Additional investigation
Since this anomaly was impacted two specific devices, further analysis was warranted. The CEO reported an incident to the company's security team and additional data collection and analysis was performed.

It was determined that a non-standard DNS server was active at the executive's home. This DNS was located outside of the country and was not part of the infrastructure of their ISP.

The home router was inspected and several security concern was discovered, including a known password and some remote management interfaces enabled.

The team was able to capture the TLS negotiation at a later time so the full certificate chain was available for inspection.

## Inconclusive findings
Clearly there was an incident of concern occurring on the co-foudners' devices. Like many incident, it was difficult to determine the root cause. The steps propsed by the incident response team included:

* Take the home router offline
* Analyze the router for signs of compromise
* Attempt to capture the incident live and collect more data
* Forensically acquire and analyze the devices
* Wipe the devices and re-provision
* Issue a new home router, secure according to best practices

In the incident, it was helpful to have security aware individuals. However, in most situations this is not a likely scenario. Even with the technical capabilities of the impacted individuals, it still took several days to identify, analyze and remediate the incident.
