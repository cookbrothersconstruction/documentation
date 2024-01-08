# Recruitment testing notes

## Notes

- Access to the recruitment module is controlled via security groups
- We will want to review the "recruitment stages"
- Hiring managers can be "collaborators" or specific "recruitment stages"
- Jobs posted can be assigned to teams (but only one), assume this means they'll be on that team if they become an employee
- We will need to define hiring process evaluation sections and questions. These can be templated.
- There is an option to "enable overall rating" on evaluation sections. Unsure what this means exactly.
- A hiring manager is separate from a collaborator in the recruitment process?
- Hiring managers and collaborators need to enable EH MFA in order to access the recruitment module
- If there is contract negotiation, when is the contract issued (candidate is not onboarded at this stage, so perhaps negotiation happens through recruitment module. contracts are templated anyway).

## Configuration
- Seek and TradeMe require a bit of configuration
- Candidate sources
- Experience levels

## Testing
- Dogfood this for the Systems Engineer role (as manual entry for now, without job boards)
- Will need to set up a hiring manager / collaborators to see how that looks

## Reference check process

**Request for reference check details (sent to candidate)**
![Reference check email sent to candidate](https://github.com/cookbrothersconstruction/documentation/assets/115191984/0dd116b2-73c3-4874-a64d-f47c57f84aae)

This onboards the candidate into _SWAG_ which we might not want:
![Candidates forced into SWAG upon automated reference checks](https://github.com/cookbrothersconstruction/documentation/assets/115191984/d1e83d8e-4075-41c8-bbc6-84be6656277d)

Completing your profile can be skipped, however you do get prompted to do it again.

I couldn't get any further than this:
![SWAG having unhandled routes](https://github.com/cookbrothersconstruction/documentation/assets/115191984/2842867f-7a07-4a36-b1a6-260115a39045)

## Sending emails to the candidate via EH

These appear without all the EH boilerplate which is nice:
![Clean candidate emailing](https://github.com/cookbrothersconstruction/documentation/assets/115191984/32eb1dea-56de-41ed-b729-0a2b57c978a0)

Responses from the candidate go straight to the sender email addres (e.g. ben.dawson@cookbrothers.co.nz) but also do get tracked in EH activity.
