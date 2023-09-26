<div class="cbc-md">
  
# The process for setting up a site in 1Breadcrumb

> This document outlines the processes that are to be followed throughout the lifecycle of a project as it exists in 1Breadcrumb.
> 
> Some of these tasks will be initiated or performed by the project team themselves, others will be performed by IT / Business Systems / NSCA.
>
> It is assumed that you who are reading this document have full access to all systems.


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

**Site Supervisor(s) Email Address**
Set this as the Site Manager as indicated by #5 in the setup request form submission. Multiple email addresses can be added by separating them by a comma.

> The Site Supervisor field only relates to the automatio


## TODO:
- configuring the site
- confirming site location
- permissions
- signage
- instructions to project team



</div>
