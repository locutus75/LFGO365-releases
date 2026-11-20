<p align="center">
  <img src="lfgo365-logo.png" alt="LFGO365" width="260">
</p>

# LFGO365 releases

**LFGO365** is a Windows desktop app for running powerful Microsoft 365 admin scripts with less
hassle. Every tool gets a proper form, a **preview of exactly what will change**, a typed
confirmation, live progress, and a per-user result you can export. Every applied change is saved
to a local run history. You sign in with your own admin account; nothing is stored in the cloud.

Tools include converting AD-synced users to cloud-managed (Source of Authority switch), restoring
de-scoped users as cloud-only, and switching the tenant's hard-match takeover protection.

This repository only holds the ready-to-run builds. It contains no source code.

## Download

Open the [latest release](https://github.com/locutus75/LFGO365-releases/releases/latest) and pick one:

| File | Use it when |
| --- | --- |
| `LFGO365-Setup-x.y.z.exe` | You want LFGO365 installed, with a Start menu entry. **Recommended.** |
| `LFGO365-x.y.z-portable.exe` | You want to run LFGO365 without installing it, for example from a USB stick or a tools share. |

The other files in a release (`latest.yml` and `.blockmap`) are used by the app's own updater.
You don't need to download them.

Windows may show a SmartScreen warning, because the builds are not code-signed. Choose
**More info** and then **Run anyway**.

## Requirements

- Windows 10/11 or Windows Server 2016+. Windows PowerShell 5.1 is enough; PowerShell 7 is used
  when it is installed (faster, recommended).
- The PowerShell module `Microsoft.Graph.Authentication` (needed to sign in; demo mode works
  without it) and, for Exchange Online tools, `ExchangeOnlineManagement`. The app offers to install
  them for your user when they are missing.
- An admin account with the roles the tool needs (for example **Hybrid Administrator** to convert
  users, **Global Administrator** for the hard-match setting). Each tool's readiness checks tell you
  what is missing.

## Updates

LFGO365 updates itself from this repository:

- At startup, and when you click **Check for updates** in the sidebar, it looks for a newer
  release and shows what's new.
- **Installed copy:** **Download update** fetches the new installer. When it can, it fetches only
  the parts that changed. **Restart now** then installs the update silently and starts LFGO365 again.
- **Portable exe:** the new exe is saved next to the current one, and **Start the new version**
  opens it. You can delete the old exe afterwards.
- **Running as administrator:** LFGO365 starts again with administrator rights after an update
  (Windows asks once with UAC).

LFGO365 doesn't update while a tool is running. Your settings, run history and logs are kept.
Set the environment variable `LFGO_NO_UPDATE_CHECK=1` to turn off the check at startup.

## What's new

Each [release](https://github.com/locutus75/LFGO365-releases/releases) lists its changes.
