# Linux Servers

We have a number of Linux servers which had been built to server various purposes.

The configuration of these is well documented in the wiki, however this document is an overview of these servers, what they do, and what should happen with them.

## FileServer

**DNS Name**
fileserver.cookbrothers.co.nz

**IP Address**
192.168.100.13

**Machine type**
vSphere VM

**Accessible**
Yes - "File Server ssh (rclone backup)" in 1Password

**Function**
Connects to Egnyte via WebDAV, and as an rclone cron job which copies the filesystem locally

**Importance**
Medium
_Justification_
- Although Egnyte is a SaaS and they should have their own backups, they're also a bit shit. Regardless keeping an in-house off-site (site being Egnyte) backup is a good thing.
- If we ever want to move away from Egnyte then having our own full copy of all files can only be a good thing.
- This server was already set up and configured (by Harry) including instructions to open it to the internet if that was ever needed.
- This essentially costs nothing to run.

**Risk**
Medium
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

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## Monitor (Prometheus, Grafana, Loki)

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## Wiki

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## WazuhOSSEC

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## SQLServerTest1

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## PWM

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**


## UnifiNetworkDN

**DNS Name**

**IP Address**

**Machine type**

**Accessible**

**Function**

**Importance**

**Risk**

**Actions**
