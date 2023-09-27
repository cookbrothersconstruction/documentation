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

For ease of management, create a new folder for the project in the correct region under [M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material](M:\One Team\Business Systems\01 Projects\H&S Systems\1Breadcrumb\Project specific material):

![New project folder for documentation](https://github.com/cookbrothersconstruction/documentation/assets/115191984/8c28a0f2-7af2-40d2-86e7-6a074a5f78d1)



## TODO:
- instructions to project team (separte document for PMs around mainting the Procore Project Directory)
- hardware
- signage
- the integration back up to Procore (site diary and documents, and quirks around this)
- shutting down a site
- FAQ (issues encountered with the system, project teams, or )
- contacting 1Breadcrumb support



</div>
