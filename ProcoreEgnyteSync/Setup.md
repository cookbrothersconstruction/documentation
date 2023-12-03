# Procore / Egnyte setup on existing project.

## Links to vendor documentation

[Egnyte article on setup within Egnyte and Procore app](https://helpdesk.egnyte.com/hc/en-us/articles/360028989871-Procore-Integration)  
[Documentation of the "Advanced Procore Integration" which doesn't actually exist](https://helpdesk.egnyte.com/hc/en-us/articles/4424854007693-Advanced-Procore-Integration)  
[Egnyte unsupported file path names](https://helpdesk.egnyte.com/hc/en-us/articles/201637074)  
[The Egnyte sync app on the Procore marketplace](https://marketplace.procore.com/apps/egnyte-sync)

## Protect against catastrophe

### Create a full backup of the Egnyte folder for this project

Use the [Procore Extracts tool](https://support.procore.com/products/procore-extracts/user-guide/tutorials/extract-project-data-using-procore-extracts) (v1.2.2) to export the project's Procore documents:

![The Procore Extracts tool](assets/procore_extracts.png)

There may be Windows file / folder name length limits so consider extracting to a short path i.e. `c:\pb\`, then compress (use 7zip as there may be special characters) and save to shared storage e.g. `T:\Shared\Backup\Procore - Egnyte sync pre-setup backups\A364 - 223 Ponsonby Road\Procore\`

### Create a full backup of the Procore document structure for this project

Use the Egnyte web portal to copy the project's Egnyte documents to shared storage e.g. `T:\Shared\Backup\Procore - Egnyte sync pre-setup backups\A364 - 223 Ponsonby Road\Egnyte\` so the copy doesn't proxy through your local machine.
  
## Preparation

### Test for bad file paths

Run the [procore_dir_walk](https://github.com/cookbrothersconstruction/procore-egnyte-dirwalk) script against project. Contrary to the wording of [Procore's documentation around rate limits](https://developers.procore.com/documentation/rate-limiting), rate limits apply to DMSAs not "unique authentication tokens" meaning running the procore_dir_walk script against a Procore environment might be limited to once or twice an hour.

Running the script will probably identify some file or folder paths which the integration would get caught up on (usually .\_DAV folders). Manually rename these paths within Procore so they are valid (.\_ to \_\_ for example). More info in the project's Github repository.


### Configure the Egnyte app within Procore

Before the sync can be enabled for a project, Egnyte's Procore app needs to be configured.

Head to Procore's App Management:  
![App Management](assets/procore_app_management_popup.png)

View Egnyte's Procore app:  
![View Egnyte app](assets/procore_app_management_list.png)

Permit access to the project under the Permissions tab:  
![App Permissions](assets/procore_egnyte_app_permissions.png)

No additional configuration is required here, as it relates to Egnytes embedded file browser.

The integration is now "enabled" on the project but not yet started.

Start the sync from Windows file explorer:  
![Start the sync from Windows](assets/explorer_start_sync.png)

Or from Egnyte's web UI:  
![Start the sync from web](assets/egnyte_start_sync.png)

You'll then be prompted to log into Procore, select your company, and the project to start syncing:  
![Choose the project to sync](assets/egnyte_start_sync_selection.png)

The status of the currently synced projects / folders can be checked via the Egnyte web UI. Note that the URL this generates expires after some time. Note that the Last Successful Sync date is in UTC.  
![Egnyte list synced projects](assets/egnyte_list_syncs.png)

# Test cases

## Test case 1 - Project in tender (AT146)

This project is still in tender so doesn't have a lot of documents. There were no file issues after the initial sync.  
Considerations:
- When the project goes live, the Egnyte folder will move. This may mean that the sync will need to be re-established, although if tied to the folder GUID, if moved via the Egnyte web UI there's a possibility the GUID might not change (this hasn't been tested)

## Test case 2 - Current project (A364)

This project had a handful of bad file paths which needed renaming before enabling the sync (.DAV folders).  
While syncing, the rate limit was hit (curiously for A392) however recovered fine the following hour.  
After syncing, there are 25 skipped files:
- 18 empty files (message: Procore rejected empty file). This should be fine.
- 3 bad file names of the format ~$filename.xlsx (message: Procore path contains unsupported characters: / \ " : < > | * ?). This is documented as a bad path format and is a temporary Excel file so should be fine.
- 4 other files (message: Unhandled error). Unsure about those, requries investigation.


# Issues and concerns

## Sync "warnings"

Active monitoring of sync status will be required, with errors and warnings investigated.  
![Egnyte List of Synced Procore projects - skipped files](assets/egnyte_sync_list_skipped.png)

## Hitting rate limits

After hitting the rate limit when syncing A364 (message: Procore quota exceeded) and the sync recoving fine, there are some new concerns around hitting these limites through normal use (once more projects are set up). Further information around this has been requested from Egnyte.


# Moving forward

## Further projects

The sync will be enabled on more projects. This will need to be staggered to monitor for errors and avoid rate limits.  
A schedule of priorities of current live projects company wide will need to be created, and an announcement made (potentially by marketing) to communicate this. Engage project managers when it's time to enable on their projects.

## Training

People will need to be informed about the sync and some form training will be required. Caleb will be doing this for the currently syncing Auckland projects. Expand on this after hearing how this goes.

## Documentation

There will be further complications during implementation so ensure that any documentation is kept up to date.


*convert this markdown document to a docx with pandoc: `pandoc -o Setup.docx Setup.md`*  
