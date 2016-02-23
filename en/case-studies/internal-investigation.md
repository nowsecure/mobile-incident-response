# Internal Investigation
A number of incidents may occur within an organization that require a team to perform an internal investigation. The IR team should follow a similar process for these internal incidents as they would any other. In this section, we discuss a number ways in which a mobile device may be involved in an internal corporate investigation.

## Departing employee data theft
When an employee leaves an organization, it is important to have a process in place to properly disconnect access to corporate resources as well as ensure that no corporate data resides on that individual's mobile device. One of the challenges in mobile involves BYOD versus a corporate-owned device. In a BYOD scenario, the IR team may not have direct access to the device or artifacts needed to properly investigate an incident. With a corporate owned device, the specific incident details may vary, but the general steps would involve:

* Forensic acquisition of data on device
* Collection of network traffic transmitted from device
* Analysis of artifacts to determine whether data theft had occurred

An example scenario may involve using advanced SQLite recovery techniques to retrieve deleted SMS records, call logs, or other form of communication that may assist in the investigation. Documented communication with co-workers or individuals outside of the organization may prove useful. Performing a timeline analysis of the files that reside on the device can also be a helpful piece of evidence in any type of investigation. As discussed in Chapter 2, there are tools available that can provide a listing of all files that exist on the device as well as when they were created, modified, or accessed. By narrowing this list to the specific timeframe in question, an investigator can get a good understanding of the actions that took place on the device during that time. An example timeline analysis might show that a PDF file called "Company Confidential Data" was created at 10:15am, and an e-mail sent at 10:16am. Following that up with additional e-mail analysis could provide that "Company Confidential Data.PDF" was e-mailed to a user outside of the organization.



