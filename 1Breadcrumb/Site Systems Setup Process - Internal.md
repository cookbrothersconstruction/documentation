<div class="cbc-md">
  
# The process for setting up a site with 1Breadcrumb

> This document outlines the processes that are to be followed throughout the lifecycle of a project as it exists in 1Breadcrumb.
> 
> Some of these tasks will be initiated or performed by the project team themselves, others will be performed by IT / Business Systems / NSCA.
>
> It is assumed that you who are reading this document have full access to all systems.
>
> This document doesn't cover:
> - Tagging and Automation
> - Custom Questions and Inductions / Induction maintenance
> - End user attendance functionality (such as checking in to a site)
> - End user host functionality (such as configure Site Announcements)


## Where does this document start?

Regardless of whether or not a project went through tender, ECI, a handshake deal, or appeared from nowhere, it will eventually get a budget and production project code and will be handed over to the project team.

At this stage the project should exist and be properly configured in Procore. Those tasks are outside the scope of this document.

Once the project team have taken ownership of the Procore project they can:


## Submission of the [Systems & Equipment Site Setup](https://forms.office.com/r/JgczdvNttj) form

> More info about this form can be found [here](https://helpdesk.cookbrothers.co.nz/a/solutions/articles/42000103367)

Upon submission this form will fire off the [Systems & Equipment Site Setup request](https://make.powerautomate.com/environments/Default-d2bbeec6-1aa1-4971-a0e0-8937a6fbeabd/flows/shared/e0c87133-2235-4a8e-8311-66907d221181/details) Power Automate Flow.

This flow creates a task in the **To do** Board of the 1Breadcrumb Project in Asana, and also sends an email to helpdesk@cookbrothers.co.nz which will create a Freshdesk support ticket.

The submitted form will provide answers to a number of questions, many of which relate to the configuration of the site in 1Breadcrumb. They are listed here for reference:

1. What is the project name?
2. What is the Project code?
3. What is the physical address of the site?
4. Who is the Project Manager for this project?
5. Who is the Site Manager for this project?
6. Standard site operating hours start from?
7. Standard site operating hours to?
8. People should not be on-site at all on the following days:
9. Do you require a new site tablet?
10. Does your site require an Internet Connection?
11. What internet access does your site require?


## Checking over the site in Procore

Although configuring Procore is a separate process, some settings should be checked before enabling the integration with 1Breadcrumb.

Specifically, ensure that **Timecard Entry**, **Man Hours Register** and **Visitor Register** are enabled on the projects Site Diary tool settings:

![Access the site diary settings](https://github.com/cookbrothersconstruction/documentation/assets/115191984/41d61ae9-7cd3-4da8-935e-ddc414c06449)

![Enabling site diary components](https://github.com/cookbrothersconstruction/documentation/assets/115191984/21db2f2e-414c-416c-ba25-ef35450cd501)

> 1Breadcrumb is configured to send attendance hours back up to the projects site diary, mapping visitor type to these three site diary components
> This is mapped (1Breadcrumb visitory type -> Site diary component):
> Employee -> Timecard Entry
> Sub-contractor -> Man Hours Register
> Visitor -> Visitor Register


## Enabling the Procore project integration with 1Breadcrumb

In order for the Procore project to appear as a site in 1Breadcrumb via the integration, permissions must be added for the project in the 1Breadcrumb Procore App settings.

Access Procore's App Management:

![Procore App Management](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e3b437d2-0868-431a-9351-a7f8d6a5dd40)

View the 1Breadcrumb App:

![View 1Breadcrumb App](https://github.com/cookbrothersconstruction/documentation/assets/115191984/af6f775e-1819-4d83-b96c-a2a96c0fefc0)

Head to Permissions:

![1Breadcrumb App permissions tab](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e7adbecb-3ee4-44e4-8a20-b5e2bb92b080)

Permit the project you are setting up:

![Permit Procore project for 1Breadcrumb integration](https://github.com/cookbrothersconstruction/documentation/assets/115191984/96214b00-5a04-45b8-8ec8-db9b6c99bf73)

The site should now be ready to appear in 1Breadcrumb


## Ensure the site appears in 1Breadcrumb

The 1Breadcrumb integration pulls newly found projects from Procore on a schedule, so after adding permissions it will eventually appear.

You can however encourage the integration to run this as soon as possible via 1Breadcrumb's integration settings:

![1Breadcrumb integration settings](https://github.com/cookbrothersconstruction/documentation/assets/115191984/8a44a9d6-3213-4310-88f1-5e377c12a44d)

Under the Procore Integration tab, hit the **Sync As Soon As Possible** icon under **Import Sites**:

![Encourage importing of sites](https://github.com/cookbrothersconstruction/documentation/assets/115191984/9bf821e2-8c18-4cc6-bf19-5e062c245da3)

> Notice that imported sites are created based on the site template **Cook Brothers Template**
>
> This applies defaults such as our standard site induction. If this needs to be modified it can be found as an **Inactive Site**


## Finishing the configuration of the site

The site will now appear in the 1Breadcrumb, can be managed, and will be identifiable by the fact it's physical address isn't confirmed:

![Unconfirmed new site](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e88417b6-b791-41e1-aef5-c05165471b77)

Click on Manage Site to continue the configuration of this site.

Starting from the top, these are the settings to enter and confirm:

**Project Settings -> Site Supervisor(s) Email Address**
Set this as the Site Manager as indicated by #5 in the setup request form submission. Multiple email addresses can be added by separating them by a comma.

> The Site Supervisor field only relates to the automations: sending notifications to Site Supervisors etc.
> 
> Permissions are configured separately and covered below


**Project Settings -> End Time Of Day**

By default (based on the template) sites will force attendees out at the end of the day. This time is configured here and can be determined by #7 from the response to the site setup form.


**Project Settings -> Site Radius and Address**

This one can be a little tricy to get right. Sometimes sites are close together or require a large geofence. Try to avoid any ovelap with existing sites, but generally make the radius large enough to keep anyone who steps outside for a sandwich inside the zone.

Generally a good minimum is 160 metres.

The site address will appear within the app and on the generated PDF instruction sheet, so keep it terse and consise if possible. The Address can be set independently to the Latitude / Longitude position.

The address provided in #3 from the site setup request form can be a guide, however this can be tweaked at any point later if you're unsure.

In order for the site location to be confirmed you need to move the map pin and submit your changes or click the red warning on the site list page:

![Confirm site location](https://github.com/cookbrothersconstruction/documentation/assets/115191984/5de2e149-0ca0-449c-a84e-5d5e15f753f4)


## Special configuration for certain sites

Some sites may have special requirements here.

As an example Les Mills in Dunedin is on the lower floor with poor GPS, is attached to a mall which site workers may visit outside of work, and is adjecent to the Dunedin Office site.
Because of this, the **Automated Attendance** settings were disabled.

Another example would be the Air New Zealand - Projects site which acts as an umbrella site for all sites within it. Because of this, the site required a large radius (2000 Metres). 1Breadcrumb can contacted to increase the radius beyond what the system normally allows.


## Roles and Permissions

Permissions to the system can be granted to user accounts in the system. Cook Brothers employees should already be loaded in as users from the Procore integration.

Permissions can be applied at two separate scopes: **Company** and **Site**

Access the permissions settings from the web portal corner dropdown menu:

![Accessing Permissions](https://github.com/cookbrothersconstruction/documentation/assets/115191984/6cced082-bf1b-4bef-bc1b-15b4415febc3)


### Company Hosts

Company Hosts have configurable access to all sites.

This includes super admins, and Health and Safety Manager, and the Exec team.

Unless all permissions are granted (super admins), apply individual access based on Roles (more info about Roles below) so that any access changes can be performed in one place.

> **It's critical to limit Company Host access, and carefully restict access to All Permissions at the Company level**
> 
> If a user were to be accidentally granted All Permissions at this level they could do quite a lot of damage, including deleting sites, and messing up inductions.
> 
> **Only The IT/BS team should have full access at this level**

Exec access is applied here but is limited only to site attendance and reporting. This is so they don't need to be added to individual sites.


### Site Hosts

Sites Hosts have configurable access to only the chosen site.

This is where you would grant Role-based access to the project team so they have appropriate access to the features within the system.

Be sure to apply access to the team for any new sites which are set up.

This should include (but not necessarily be limited to):
- Site Managers
- Project Managers
- Quantity Surveyors
- Health and Safety Coordinators
- Office Admins
- GSDs

As an example:

![YMCA Site Host example](https://github.com/cookbrothersconstruction/documentation/assets/115191984/a315474f-f6bb-4ecf-b3ac-67c822c5e595)


### Quirks

This part of the system has a few quirks to be aware of.

When searching for a user to add as a Company or Site Host, you must provide more than 3 characters in the search fields for them to populate:

Doesn't work:

![3 characters doesn't work](https://github.com/cookbrothersconstruction/documentation/assets/115191984/a514e9b3-2880-40aa-8024-fca6a35a8d5f)

Works:

![3+ characters works](https://github.com/cookbrothersconstruction/documentation/assets/115191984/2595d1cc-57f5-43a3-ba8c-1aeeff01dcca)


The integration is supposed to pull down the Site Host permissions from the Procore Project Home Roles, however this has proven unreliable so it's best to check on project setup.


### Roles and Role Permissions

The Roles (which permissions are applied to) are configured under **Company Settings -> Permission Settings -> Role Definition**.

These were initially pulled from Procore, but can be created ad-hoc (such as with the Exec role)

The general recommendation from 1Breadcrumb is that Site Hosts (Site Managers) should have all Site Permissions ticked, along with "Site Host" under Company Permissions:

![CBC Site Manager permissions](https://github.com/cookbrothersconstruction/documentation/assets/115191984/8eaa3184-39c1-4647-83ee-f4ee9ee1649a)

> Note that checking all these Site Permissions includes **Supplier Management** which we don't want users performing as supplier population happens via the Procore integration.
> 
> However, unless all Site Permissions are checked, only Evacuation Drills can be performed and not actual Evacuations. 1Breadcrumb are aware that this is an issue.


## Sending info to the project team

Now this site has a baseline setup in 1Breadcrumb you can send information to the project team.

For ease of management, create a new folder for the project in the correct region under [M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material](file://M:/One%20Team/Business%20Systems/01%20Projects/H%26S%20Systems/1Breadcrumb/Project%20specific%20material):

![New project folder for documentation](https://github.com/cookbrothersconstruction/documentation/assets/115191984/8c28a0f2-7af2-40d2-86e7-6a074a5f78d1)


### Site QR Code and Template for Lamination

First get the generated instructions from 1Breadcrumb by hitting the **Print Instructions** button on the site list:

![Print Instructions](https://github.com/cookbrothersconstruction/documentation/assets/115191984/5c50691f-f35e-41cd-b483-e62719d03a4a)

And move this into the project folder created above.


Then **copy** the `1BC QR Code Template.docx` document from [M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material](file://M:/One%20Team/Business%20Systems/01%20Projects/H%26S%20Systems/1Breadcrumb/Project%20specific%20material) into the project specific folder.

Open the Site Instructions PDF and on the second page you'll see the site QR code.

Screen cap this code (it helps for clarity, if you can, to zoom in to 500% on the PDF first), and save it in the project specific folder as `Site QR.png`.

Open the `1BC QR Code Template.docx` file from the project specific folder and paste the Site QR onto page 1:

Turning on Word Gridlines can help with alignment.

Enter the correct site code on page 2.

> Having the directional arrow and site code on the reverse will ensure that the QR code is affixed to signage in the working orientation.
>
> Having the site code on the reverse ensures the correct code, once printed, makes it's way to the correct site

Ensure the Layout of the QR code image is not interupting the document flow by setting it to "In front of text":

![QR Template Alignment](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e5f66040-bde3-46a2-ba5b-463864c3dfe2)

Save the file.

> This code will be printed, cut and laminated for fixing to the corflute signage.
>
> Ensure it's printed double-sided along the long edge.


### Offsite Instructions

In order for Trade Partners to be prepared and save time the first time they attend site, they will be sent instructions to perform the Cook Brothers Company Induction at their leisure (off-site).

Head over to Site Settings in 1Breadcrumb for this site, and expand the Offsite section, and hit **Show Offsite QRCode**:

![Offsite settings](https://github.com/cookbrothersconstruction/documentation/assets/115191984/728afb0a-1077-4185-a52e-aa59a558794f)

Right-click on the Offsite QR code and save it to the project specific folder as `Offsite QR.png`.

Hit the Copy to Clipboard button under Offsite Link and save this in the project specific folder in `Offsite Link.txt`

**Copy** the `1Breadcrumb Trade Partner Induction Instructions.docx` file from ![M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material](M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material) into the project specific folder.

Edit this file and paste in the contents of `Offsite QR.png` and `Offsite Link.txt` into the appropriate places, and enter in the site name:

So that this:

![Offsite Template](https://github.com/cookbrothersconstruction/documentation/assets/115191984/4593a7c8-e23c-48bb-8e90-4727fd1eab2f)


Becomes this:

![Offsite Template populated](https://github.com/cookbrothersconstruction/documentation/assets/115191984/bfcff162-5b02-4a8f-89de-8c08b6923511)

Resizing the QR code if necessary.


### Confirm you have all the information

It's a good idea to rename the DOCX and PDF files to include the site code and site name so that the recipients are sure what project the files relate to.

The project specific folder structure should now like like this:

![Info file structure](https://github.com/cookbrothersconstruction/documentation/assets/115191984/0aa48b4f-3ec9-4964-b6f9-baa3ad805c93)

**At this stage it's reccomended to scan each of the onsite and offsite QR codes and follow the links to ensure they are correct**


### Comms to the project team

I usually send something like the following to the porject team:

![Comms to project team](https://github.com/cookbrothersconstruction/documentation/assets/115191984/b91ac4d7-4e54-493d-b8c0-8f248c91d45c)

<hr />

Hi Team,

Please forward to more of your project team as necessary.

This site is now set up in 1Breadcrumb.

Attached is a template which should be included in engagements with Trade Partners to inform them of the system, their requirement to use it, and how to be prepared. This importantly also contains the off-site induction link which they can follow to complete the Company Induction prior to attending a site. This Company Induction will only need to be done once per user, and site-specific induction material will be completed (once) upon checking-in to the site.

Note that Trade Partner Companies need to be added to the Procore Project Directory priory to sending this out, so that they will be able to select who they work with.

Also attached is the standard site 1Breadcrumb info sheet.

Remember that there are Knowledgebase articles available for anyone who needs to know more about the 1Breadcrumb system and how we use it:
[https://helpdesk.cookbrothers.co.nz/support/solutions/42000067671](https://helpdesk.cookbrothers.co.nz/support/solutions/42000067671)

**info about the printable QR code**

Regards,

<hr />

This would usually include something specific for the project, but be sure to include:
- The standard sign-in PDF sheet
- The Trade Partner instruction document
- Link to the Knowledgebase articles
- An obvious line stating the importance of adding Trade Partner companies to the Procore project
- Unless already sorted, you probably want to also include the QR code for lamination and printing (to be done by a GSD or Office Admin)


## Kiosk Hardware

1Breadcrumb runs best as a mobile app on a tablet or a phone, however we have a number of all-in-one PC Kiosks in circulation which can be repurposed.


### Kiosk Mode

The 1Breadcrumb app and Web portal both have an option to enter Kiosk Mode. Once the app is in Kiosk Mode it should stay that way until exited by entering the signed-in user's password.

Enter Kiosk Mode via the app menu hamburger:

![Enter Kiosk Mode](https://github.com/cookbrothersconstruction/documentation/assets/115191984/b9897c32-6c5c-4913-a2b5-f92786c8b3dc)


### Tablets

A larger sized tablet is preferred as they are easier to type on, and there are more secure mounting options available.

A typical setup would be:
[Samsung Galaxy Tab A8 (10.5" display)](https://www.pbtech.co.nz/product/TABSAM20006411/Samsung-Galaxy-Tab-A8-105-Tablet---Grey-64GB-Stora)
[Secure table top stand](https://leadingsolutions.co.nz/products/tab-secure-table-top-samsung?variant=42681003311325)

It's also a good idea to get a high quality USB extension cable.

> **Note that the 1Breadcrumb app currently only operates in the portrait orientation, so any fixed tablets will need to be mounted vertically**

**Configuration**

The kiosk tablets are signed in as our kiosk@cookbrothers.co.nz Google account.

Generally we don't set a pin / passcode / lock on the device so that it can be accessed easily if it goes to slep 💤.

Skip over any annoying Samsung cruft, or settings which don't need to be enabled.

**Screen Brightness and Timeout**

To ensure accessibility especially in areas which may be hit by direct sunlight configure the tablet so:
- Display is in Dark Mode (in order to save battery if the tablets loses power)
- Turn off Adaptive Brightness (it's pretty unreliable so just put the brightness at the max)
- Set Screen timeout to the max.
- Android Developer options has a setting for Stay Awake (screen will never sleep when charging) **developer options must stay enabled to keep this setting. this can also be configured outside of developer options via the ADB tool if needed**


**App Pinning**

Android doesn't have a password protected lockdown mode, so the best option is App Pinning which can be enabled in Security -> Other security settings -> Advanced -> Pin windows

To pin the app, open the app switcher and tap on the application's icon:

![Pin an app](https://github.com/cookbrothersconstruction/documentation/assets/115191984/f0d28311-2bbc-4620-88e0-0559b5087a7c)

Then select "Pin this app":

![Pin this app](https://github.com/cookbrothersconstruction/documentation/assets/115191984/7dc04d7a-6844-419d-83b9-6f0c5768a1ad)

To exit this mode, hold the Recents and Back buttons at the same time:

![Exit pin mode](https://github.com/cookbrothersconstruction/documentation/assets/115191984/a985bf48-38fc-4094-8e6e-65987528e2db)


### All-in-one PC

An example of one of these would be a [Lenovo V530 All-in-One (24)](https://www.lenovo.com/ao/en/desktops/lenovo/v-series-all-in-ones-/Lenovo-V530-24ICB-AIO/p/11LV1VZV534?orgRef=https%253A%252F%252Fwww.google.com%252F)

The 1Breadcrumb application will need to run in a web browser, and Google Chrome is preferred.

> If reconfiguring an older PC for use as a kiosk, ensure that any links (startup apps, browser bookmarks, desktop shortcuts, etc.) relating to OnLocation are removed.

After entering Kiosk Mode in the web browser, the following URL should be used for creating any new bookmarks or shortcuts:
`https://web.1bc.app/#/KioskMode`

Don't place the browser into fullscreen mode, as when performing the Company Induction, the YouTube video needs to open in a new browser tab, and this occurring in fullscreen mode is confusing.

Although these machines are touch-screen, it can be preferred to supply a keyboard and/or mouse.


## Signage

There is corflute signage designed for affixing the site's QR code (see lamination instructions above):

![Corflute signage](https://github.com/cookbrothersconstruction/documentation/assets/115191984/108053d7-64a2-4956-a8ac-9b504ea60b0f)

This signage will be requested at the start of a project through the marketing team via the signage order form.


### The signage order form

This form currently exists as an End To End document: 4.1b Site Signage Order Form.xlsx and has been modified to include the above signage request and is in place in the file structure templates regionally in Egnyte, and the Procore project templates.


### Stockpiles

This Signage is intended to be reused with a new QR, and these often end up in the yard or transferred to a new site.

Additionally each region should retain a small stockpile of these signs for those who don't follow the signage order form.


## The integration back to Procore

The other side of the integration is 1Breadcrumb to Procore. This occurs for a couple of components of the 1Breadcrumb system.

### Export of checkins

Attendance is pushed up to the Procore Project Site Diary. Like the integration of other components this is not realtime and occurs on a schedule (around once per hour).
Depending on the visitor type (Employee, Subcontractor, Visitor), the integration is configured to export attendance into one of the 3 Procore Site Diary buckets (Timecard, Manpower Log, Visitor Log respectively):

![1Breadcrumb export configuration](https://github.com/cookbrothersconstruction/documentation/assets/115191984/241cffbd-d23e-4b78-9a3c-c5739f569996)

Although having attendance posted to the Procore Site Diary is useful for Procore reports and dashboards, H&S person-hour reporting at the Exec level is based on exports of the data directly from 1Breadcrumb. Instructions for these reports can be found here [H&S Personhour reports](https://cookbrothers.egnyte.com/navigate/file/b062c1fb-327c-4609-b5b5-865f95c2512d)

1Breadcrumb will post additional information in the Comments column of the relevant site diary entry:

![Site Diary entry comments](https://github.com/cookbrothersconstruction/documentation/assets/115191984/5f242d1d-12ad-4ec5-aa78-77113e0742a0)


### Export of documents

Documentation collected by the 1Breadcrumb system is exported to the Procore Project Documents tool, under the folder 1Breadcrumb as per the 1Breadcrumb integration configuration:

![Document export configuration](https://github.com/cookbrothersconstruction/documentation/assets/115191984/025c4f01-921b-4716-b37a-e9507ca8d92d)

Inductions are currently auto-approved, so for example copies of individual Site Induction records will be seen in the Documents tool like so:

![Induction records](https://github.com/cookbrothersconstruction/documentation/assets/115191984/aee83272-df98-4632-977d-dcd20a845c49)

This data can also be pulled directly from 1Breadcrumb reporting.

## Maintenance during project lifecycle

### Procore Directory

The most critical thing to maintain throughout the project lifecycle is the maintenance of the Procore Project directory as this populates the 1Breadcrumb supplier list and allows subcontractors to select their company when they check in to a site.

There exists in Procore a company named **Company Not Listed Here**

Only the company itself needs to be added, not any individual users (unless they also need access to Procore). This is best done via "Bulk Add From Co. Directory".

![Example of loading a company to the Procore Project Directory](https://github.com/cookbrothersconstruction/documentation/assets/115191984/ac24ec78-c429-4cb3-8811-7224aa70d602)

This should be done in advance of the trade partner employees showing up to site.

This also allows time for the offsite induction material to be communicated by the project team to the trade partner company.

## Shutting down a site

It's crucial that IT / BS are looped in during site shutdown no ensure any services and connections are disabled, equipment is returned, and systems are updated.

The takedown request form is available here: https://forms.office.com/r/EWecbRyQcE

After this form is submitted, the site can be made inactive in 1Breadcrumb via the Danger Zone under site management:

![Danger Zone](https://github.com/cookbrothersconstruction/documentation/assets/115191984/26cb1e16-1122-4415-9e24-1f8c037ca8db)

**I'm unsure what affect this might have on reporting, so check that inactive sites can appear in activity reports, otherwise sites should be made inactive > 1 month after closeout**


## What specifically should not be done in the system


## Issues encountered with the system


## Issues encountered with the project teams


## Issues encountered with attendees


## Contacting 1Breadcrumb support



</div>
