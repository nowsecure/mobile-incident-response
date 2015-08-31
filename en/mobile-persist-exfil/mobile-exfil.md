# Mobile Exfiltration

Exfiltration
- is used here as the extraction of data by covert or overt (e.g., hide in plain sight) means.
- while persistence provides ability to return to the target, exfiltration is about how the data may be stolen from the target

Mobile devices are both consumers and producers of large amounts of data. At any given time devices are sending photos, video, text messages, communicating over varied protocols including HTTP/HTTPS/WebRTC and otherwise making a flurry of network connections. This level of communication may act as a perfect cover under which to blend into normal communications to exfiltrate sensitive data.

TODO: insert or refer to average number of connections a device makes over the course of a day.

## Permitted exfil

In many cases the applications a user installs has requested a number of permissions before installation (Android) or requests access the first time its used (iOS). If the user allows the app access to sensitive data it may simply send this information over the network, perhaps caching it locally in priviate storage before doing so.

See Aetna case study.

## RATs

Remote Access Tools (RATs) provide the adversary with varied control over a target's device. Ideally the RAT is granted elevated privileges

A RAT may:
- Obtain the user's contacts
- Create native device notifications
- enable and disable GPS location tracking
- obtain user location via GPS or cellular network
- Observe and/or transform the device's stream of text messages, phone calls
- Enable and/or record/stream the microphone
- Take photographs or record/stream video
- Retrieve additional code payload
- Act as a network hop or proxy for an adversary
- Join the device to a botnet

## GPS
## Contacts


## Baseband?

replace baseband?

## Replace OS daemons?

advanced adversary
