# Issuing an Individual Employment Agreement in Employment Hero using an Advanced Document Template

## When do we issue a contract

An IEA (or any document template) can be issued at a few different points.

### At the end of the Recruitment module

At the final stages of the Recruitment module, a candidate will be moved into the **Hired** bucket:

![Moving a candidate into Hired](https://github.com/cookbrothersconstruction/documentation/assets/115191984/149c4df3-0879-4535-8bd0-32cc9c9536a1)

Once in the **Hired** bucket, the **Onboard** option will appear:

![Onboarding a candidate from Hired](https://github.com/cookbrothersconstruction/documentation/assets/115191984/4c1da739-fb1b-4f94-a478-242d97d78bf0)

Note that some Fields needed to be collected at this step:
- Location
- Start date
- Industry standard job title

Also note that this newly recruited employee does not need to be added to any teams, and no checklists will need to be triggered, as this will occur after the employee has accepted and signed their IEA.

The next step in this process is entering Pay Details:

![Entering Pay Details](https://github.com/cookbrothersconstruction/documentation/assets/115191984/79bd35a7-171f-47a1-b3cc-5daadbdb338a)

Note that:
- Pay rate is required here, as is the Esct Rate % (which is calculated)
- Automatically enroll in KiwiSaver (or not, or ineligible)

At the end of this step there is a button to **Issue Contract**:

![Issue Contract button](https://github.com/cookbrothersconstruction/documentation/assets/115191984/330cef1f-089c-4f2c-90f8-991a633e0339)

This will take you to the Select Contract screen. This section is unique to sending document templates for contracts and provides additional functionality over the standard "Bulk Issue Documents" method, such as drafting the contract without auto-populated fields, finalizing / confirming the contract as the candidate will see it, and modifying the email which is sent to the candidate.

The first step is to select the contract which is **Cook Brothers Construction - Individual Employment Agreement**:

![Selecting the IEA](https://github.com/cookbrothersconstruction/documentation/assets/115191984/69570f08-bae8-4ee7-82da-65d487d7e44e)

This is where any missing information (in pink) can be filled in, and optional blocks or sections can be removed. Even though these pink fields have defaluts, this is a good opportunity to confirm these values:

![Setting variables](https://github.com/cookbrothersconstruction/documentation/assets/115191984/0d3b464e-fa60-4acf-b381-0da66e918a47)

Any of these variables that shouldn't exist can have their text removed:

![Removing text from variables](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e0e47a05-dab7-40f6-8827-d3d33a4f5889)

Note that when doing this, don't hit enter after modifing the text as this will insert a new line. Instead simply click outside the field.

Finally, if you want someone else's name to appear as the sending signatory then modify this at the end of the document (the signature can be inserted on the next step):

![Modifying the sender](https://github.com/cookbrothersconstruction/documentation/assets/115191984/30195e9f-7d02-4394-84a6-e3803ad0798b)

After hitting **Continue** you will be taken to the **Finalise Contract** step.

On this step you can toggle the option to **Highlight variables** which will show you which variables you have modified:

![Highlight variables](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e5400917-5d2e-4e7b-a5c3-e18c96d09069)

At the end of this page you will **Finalise Document**

Another Sending signatory can be selected here, however you can also upload an image of a signature:

![Fish Signature](https://github.com/cookbrothersconstruction/documentation/assets/115191984/6a19ca0f-afa3-47fd-ac27-44c1e38321ad)

You can then modify the email content which will be sent to the new employee. Just make sure it includes the `!password_url`. This can be edited globally as an email template.

From there you can save this as a draft, or email the document immediately.

If you have selected a sending signatory, then the contract will first be sent to that sending signatory (e.g. the hiring manager).
This emails looks like so:

![Sending signatory email](https://github.com/cookbrothersconstruction/documentation/assets/115191984/12e10b8f-dbe2-4970-b168-1c298d8c7d07)

When the signatory follows the link in this email they will be taken to the document against the new employee's proifle and can enter their own signature at the bottom before accepting:

![Hiring manager signing the contract as a sender](https://github.com/cookbrothersconstruction/documentation/assets/115191984/cb6e946f-4f27-4e15-90e9-d9fbeed952a7)

The document will then be sent to the recipient (candidate).


> Note that when changing fields when issuing the contract (such as entering address line 1), this information will be included in the document but **is not** automatically set against the new employee's profile
>
> Meaning that there may still be missing information that may need to be populated by someone with access to modify the employee's profile (or the employee themselves)

> If you don't hit **Email document** or if you select **Hard copy**, then you have the option of hitting **Save As Draft**
>
> This will create the employee's profile and save the document as a **Draft** against their HR Documents.
>
> The document can then be edited which takes you back to the contract issuing flow where you can send the document and email to the employee.


## Issuing a document manually

Document Templates (of which the IEA is one) can also be issued outside of the recruitment flow. In this case an employee profile must already exist.

This is performed in the system via **Compliance -> Bulk Issue Documents**:

![Bulk issue](https://github.com/cookbrothersconstruction/documentation/assets/115191984/d185805e-bdc7-4abb-9f75-c7fc2e75e213)

> You may choose to do this if the candidate has declined the contract.
>
> In this case they have left the recuitment module and technically exist as an employee.

### How this differs from the **Contract Issuing** flow when ending the **Recruitment** process

The user interface is different here, as bulk issuing may relate to documents other than a contract:

![Bulk Issuing flow](https://github.com/cookbrothersconstruction/documentation/assets/115191984/e640115e-32cf-46a8-9f66-b388c6908b99)

Documents can be issued to more than one employee at a time by selecting them on the first step **Select personnel**

On the second step you would select the template, in this case **Cook Brothers Construction - Individual Employment Agreement**

The third step **Edit base document** allows you to fill in variables and select optional blocks in the contract, however the main differece here is that the auto-populated variables can not be edited like they can in the **Issue Contract** flow:

![Edit base document](https://github.com/cookbrothersconstruction/documentation/assets/115191984/5f99a92a-5ba3-4ee2-8b99-17f565656e7a)

Although the variables can be manually edited in the **Review documents** step, it's a good idea to check that the auto-populated fields are set against the employ profile.

These variables are:
- First Name
- Last Name
- Full-time / Part-time / Casual
- Start Date
- Job Title
- Address Line 1 (although this block can be removed in favour of the Email Address block)
- Address Line 2 (although this block can be removed in favour of the Email Address block)
- City (although this block can be removed in favour of the Email Address block)
- State (although this block can be removed in favour of the Email Address block)
- Postcode (although this block can be removed in favour of the Email Address block)
- Manager Job Title (**meaning the employee profile must have the correct manager set**)
- Location
- Salary
- Probation Period

Every other variable is editable directly on the document.

You can still preview the resulting document in the **Review documents** step:

![Preview during bulk issue](https://github.com/cookbrothersconstruction/documentation/assets/115191984/8559049b-3151-4a72-8de1-8f9cfe8d7c94)

You can manually edit any variables (including auto-populated variables) via the **Edit** action:

![Manually edit underlying document](https://github.com/cookbrothersconstruction/documentation/assets/115191984/763ff6d7-76f3-418e-aaa2-2be3e63d7dfe)


## Next steps

- When contract is returned, confirm employee details, add to teams and fire checklists
