# Bastion

Bastion is a small, hardened web browser for Windows 10 and 11. It runs on
Microsoft's Edge engine (WebView2), so sites work as they do in Edge, and
locks down the risky parts of a normal browser:

- Trackers, ads and known malware sites are blocked before they're even
  looked up. The 🛡️ button shows what was blocked on each page.
- HTTPS only, encrypted DNS, no extensions, WebRTC off by default, and
  dangerous downloads (`.exe`, `.ps1` …) refused.
- An optional browser-only **WireGuard VPN** (Proton VPN, Mullvad or your own
  server) with a built-in kill switch.
- Settings and bookmarks are encrypted on your PC. By default every session
  starts clean (amnesia mode).
- No telemetry and no account: see [what Bastion sends, and to whom](PRIVACY.md).

This repository is where Bastion's **beta** releases are published and where
you report problems. Bastion's source code is private.

## Install

1. Open the [latest release](https://github.com/sevanboyajian/bastion-releases/releases/latest)
   and download **`bastion-setup-<version>.exe`**.
2. Run it. It installs for your Windows account only and needs no admin
   rights. You'll find Bastion in the Start menu.
3. **Windows will probably warn you**, because Bastion isn't code-signed yet:
   on "Windows protected your PC", click **More info**, then **Run anyway**.

To check your download is the real one, compare its fingerprint with the
SHA-256 listed on the release page. In PowerShell:

```powershell
Get-FileHash .\bastion-setup-<version>.exe -Algorithm SHA256
```

Bastion needs the Microsoft Edge WebView2 Runtime, which Windows 11 and
up-to-date Windows 10 already have.

## Updates

Bastion checks this page once a day. When a new version is out, an
**Update** button appears in the toolbar; click it, then **Install and
restart**. Updates are signed: Bastion checks the signature and the download
and refuses anything that doesn't match. Nothing installs without your
click. You can turn the daily check off in ☰ Settings.

## Report a problem

In Bastion, open **☰ Settings → Send feedback**, describe what happened and
click **Open GitHub issue**. It fills in your Bastion version and settings
for you; you can edit everything before you submit. Or
[open an issue](https://github.com/sevanboyajian/bastion-releases/issues/new)
directly. You need a free GitHub account.

Issues are public, so leave out personal details. The Connection log is only
included if you tick it, because it shows which sites you visited.

If a site doesn't work, click 🛡️ on that page and **Turn off blocking for**
that site. If that fixes it, please report the site so the blocklist can be
fixed for everyone.

## Uninstall

Windows **Settings → Apps → Installed apps → Bastion → Uninstall**. Your
settings, bookmarks and VPN config stay in `%LOCALAPPDATA%\Bastion` until you
delete that folder.

## License

Bastion is proprietary beta software: invited testers may install and use
it; please don't share the installer. It includes open-source components
under their own licenses, listed in `THIRD_PARTY_NOTICES.md` in the install
folder. The HaGeZi blocklist it ships is GPL-3.0 and comes as a separate
file with its license.
