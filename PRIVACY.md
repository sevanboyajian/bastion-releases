# Bastion privacy policy

Bastion collects nothing about you. It has no analytics, no telemetry, no
crash reporting and no account. Nothing you do in Bastion is sent to its
maker, except feedback you choose to send yourself.

This page lists everyone Bastion's own features talk to, and what they learn.
Websites you visit see what any browser shows them, minus what Bastion
blocks.

## Who Bastion talks to

| Who | When | What they learn |
|---|---|---|
| **Your DNS provider** (Cloudflare or Quad9, as chosen in Settings) | Every new site name you visit, over encrypted DNS-over-HTTPS | The names of the sites you visit, and your IP address (the VPN's address while the VPN is on, and then the VPN provider's DNS is used instead). |
| **Your VPN provider**, if you turned the VPN on | All of Bastion's traffic | Which sites you connect to, and when (not page content, which stays encrypted). Your real IP address. |
| **Microsoft** (the WebView2 engine) | SmartScreen checks of pages and downloads for phishing and malware; engine components | Addresses of some pages you visit, for the safety check. Bastion blocks Microsoft's engine-configuration service and some engine telemetry. The engine itself is updated by Windows, separately from Bastion. |
| **GitHub** (Bastion's releases page) | Once a day, if "Check for updates automatically" is on, and when you click "Check now" or install an update | That a copy of Bastion is checking for updates, and your IP address (the VPN's while it's on). Nothing else is sent. |
| **GitHub** (issues) | Only when you click "Open GitHub issue" and then submit it | What you write, your Bastion version and settings summary, and the Connection log only if you tick it. Issues are public. |

## What stays on your computer

- Settings, bookmarks, sites where you turned blocking off, and your VPN
  config are stored encrypted (XChaCha20-Poly1305, with the key sealed to
  your Windows account) in `%LOCALAPPDATA%\Bastion`.
- In the default amnesia mode, cookies, history and site data are wiped every
  time Bastion starts. With "Keep logins and site data" on, the engine keeps
  them in its profile folder there.
- The Connection log only lives in memory and is gone when Bastion closes.

## Questions

Ask on the [releases page's issues](https://github.com/sevanboyajian/bastion-releases/issues).
