# Linux Servers

We have a number of Linux servers which had been built to server various purposes.

The configuration of these is well documented in the wiki, however this document is an overview of these servers, what they do, and what should happen with them.

Be warned this document was written in a day without any prior experience with these servers

> In addition to what's listed below, most if not all of the servers running web services do not have HTTPS / SSL enabled. They easily could as I believe we have a wilcard cert, alternatively just use LetsEncrypt.
>
> Many of these servers are also using old / potentially known or brute forceable passwords that grant root access.
>
> Along with all of these servers requiring updates, they're also all on the vSphere host which itself requires updates.

## FileServer

**DNS Name:** `fileserver.cookbrothers.co.nz`

**IP Address:** `192.168.100.13`

**Machine type:** _vSphere VM_

**Accessible:** _Yes - "File Server ssh (rclone backup)" in 1Password_

**Function:** _Connects to Egnyte via WebDAV, and as an rclone cron job which copies the filesystem locally_

**Importance:** _Medium_

_Justification_

- Although Egnyte is a SaaS and they should have their own backups, they're also a bit shit. Regardless keeping an in-house off-site (site being Egnyte) backup is a good thing.
- If we ever want to move away from Egnyte then having our own full copy of all files can only be a good thing.
- This server was already set up and configured (by Harry) including instructions to open it to the internet if that was ever needed.
- This essentially costs nothing to run.

**Risk:** _Medium_

_Justification_

- Although not currently exposed to the internet, this server does contain **all** our files.
- In recent, under-resourced times, this server hasn't received any updates. There's a good chance that installing updates might cause the server to require some mild reconfiguration.
- I can't be sure that Harry made the best choices around the tech stack running on this server, and configured it in a secure way. Even if fully patched there may still be attack vectors.
- Making any serious changes on this server requires a high level of Linux skill


**Actions**

- Keep it running
- When the ben.dawson password no longer works, follow `these` instructions to switch to a new account.
- Currently nothing notices when the backup job fails, although the rclone output is logged. This could probably be tracked by Loki.



## FogServer

**DNS Name:** fog.cookbrothers.co.nz

**IP Address:** _192.168.100.27_

**Machine type:** _vSphere VM_

**Accessible:** _Yes - "Fog Server ssh (imaging server)" in 1Password_

**Function:** _Machine imaging_

**Importance:** _Low_

_Justification_

- Imaging computers this way is a pain
- In the past non-HP computers would get an HP image and be a bit fucked
- It's faster just to set laptops etc up manually


**Risk:** _Medium_

_Justification_

- Although not currently exposed to the internet, this server hasn't been updated and https://fog.cookbrothers.co.nz points to a default Apache2 page indicating that it's poorly configured.
- It does not contain any sensitive information, however is on the server network and could probably be hacked.


**Actions**

- Shut it down (alternatives are fixing it, or finding something better)


## Monitor (Prometheus, Grafana, Loki)

**DNS Name:** _prometheus.cookbrothers.co.nz_

**IP Address:** _192.168.100.98_

**Machine type:** _vSphere VM_

**Accessible:** _Yes - "Grafana ssh (monitoring server)" in 1Password_

**Function:** _Logging, monitoring and alerting stack_

**Importance:** _High_

_Justification_

- Actually super useful, especially for knowing when a host drops out and resource monitoring
- Also super useful for log collection, otherwise who knows when something sus is happening on a server


**Risk:** Medium

_Justification_

- This relies on an open-source agent running on our servers. If there is ever an exploit in the agent that would be a concern. Maybe worth looking in to checking in on agent versions and updating.
- There's a lot to this stack, and any serious reconfiguration / making a better job of it, would require PhD level Linux skills.


**Actions**

- Keep it running as it's quite useful


## PWM

**DNS Name:** _pwm.cookbrothers.co.nz_

**IP Address:** _192.168.100.53_

**Machine type:** _vSphere VM_

**Accessible:** **NO**

**Function:** _Allows for password resetting of on-prem AD accounts, and setting of password security questions_

**Importance:** _Low_

_Justification_

- No one uses it
- It's way more likely someone will have issues with MFA
- Once AD is in Azure, one would assume there is proper self-service password features available


**Risk:** _High_

_Justification_

- This server has access to our active directory
- It hasn't received updates
- It's running a questionable stack
- It's exposed to the internet


**Actions**

- Shut it down (after Xmas just in case someone uses it)
- If it's functionality is needed find a better solution


## WazuhOSSEC

**DNS Name:** _ossec.cookbrothers.co.nz_

**IP Address:**  _192.168.100.10_

**Machine type:** _vSphere VM_

**Accessible:** _Yes "Wazuh-OSSEC Intruder Detection" in 1Password_

**Function:** _Collects data from agents for the purposes of intrusion detection_

**Importance:** _High_

_Justification_

- This was an initiative from Harry to monitor for getting hacked etc. and was part of improving our security rating after our security audit.
- Similar to Prometheus / Grafana / Loki, this at least provides something in this space.


**Risk:** _Medium_

_Justification_

- Server is newer but hasn't received recent updates.
- Runs agents which might get exploited, so someone might want to check that.


**Actions**

- Keep in running
- Systems Engineer to assess viability + improvements


## SQLServerTest1

**DNS Name:** _sqltest1.cookbrothers.co.nz_

**IP Address:** _192.168.100.56_

**Machine type:** _vSphere VM_

**Accessible:** _Yes - "Ben Dawson SSH key" in 1Password_

**Function:** _MySQL server for pulling data from 3rd party services such as Procore for in-house reporting_

**Importance:** _Medium_

_Justification_

- The previous BSM (me) saw and still sees value in this approach (in combination with system and process improvements).
- Procore reporting is limited, and this has potential to warehouse our Procore data.
- There's a chance that an in-house database server will come in handy for (for example) storing imported / historically archived Finbuild data

**Risk:** _Medium_

_Justification_

- This server requires updates.
- This is just a test server and not production ready, that said it does contain Procore Inspections, and potentially lentune data.
- MySQL / database authentication is used
- Requires a high level of Linux and programming knowledge to utilize


**Actions**

- Team to make a call. Code is on GitHub


## Wiki

**DNS Name:** _wiki.cookbrothers.co.nz_

**IP Address:** _192.168.100.8_

**Machine type:** _vSphere VM_

**Accessible:** _Yes - "Wiki ssh" in 1Password_

**Function:** _Hosts the comprehensive IT wiki_

**Importance:** _High_

_Justification_

- Contains a wealth of knowledge around IT systems, configuration, issues, contacts, etc.


**Risk:** _High_

_Justification_

- Server has not received recent updates.
- Server is exposed to the internet.
- Server contains information and details around networks, security, and server configuration.
- Server web stack is questionable.


**Actions**

- Keep it alive and keep using it.
- Consider moving it to a more modern system that looks better and is easier to maintain.


## UnifiNetworkDN

**DNS Name:** _unifinwdn.cookbrothers.co.nz_

**IP Address:** _192.168.100.37_

**Machine type:** _vSphere VM_

**Accessible:** _Yes "UnifiNWDN ssh" in 1Password_

**Function:** _Hosts the UniFi network controller in Dunedin_

**Importance:** _High_

_Justification_

- Multiple access points require a controller and it has to be hosted somewhere, and Linux is free.


**Risk:** _Medium_

_Justification_

- Needs updates, and is a network controller.
- Access points also need updates


**Actions**

- It's fine, keep it around.
