<!-- File: /README.md - v0.1.0.1 (What this repository is, and how to check a Folio Forge download) -->
<!-- Last updated: 2026-11-14 -->
<!-- Changes: v0.1.0.1: Initial creation (the releases plan, docs/RELEASES_PLAN.md on the owner's PC, section 3). -->
<!-- Analysis: Holds no source code. Public only from launch; until then the repository is private and every release is a draft. -->

# Folio Forge releases

This repository holds the published downloads of **Folio Forge**, the offline PDF reader, editor and markup tool for construction drawings, made by Samurai Dynasty Online. It holds no source code.

- **Folio Forge:** https://samuraidynasty.online/folio-forge
- **Download page:** https://samuraidynasty.online/folio-forge/download
- **Your account (your licence, your devices, the versions you own):** https://samuraidynasty.online/account
- **License Agreement:** https://samuraidynasty.online/folio-forge/eula
- **Privacy:** https://samuraidynasty.online/folio-forge/privacy
- **Open-source notices and FFmpeg's source:** https://samuraidynasty.online/folio-forge/open-source
- **Support:** support@samuraidynasty.online

Folio Forge needs a licence key or a 14-day trial, started inside the app. One licence covers one Windows PC and one Android phone or tablet.

## What each release holds

Each release is one version of Folio Forge, tagged `vB.C.D.A` (for example `v1.0.0.50`). Its files are:

| File | What it is |
|---|---|
| `Folio-Forge-Setup-<version>.exe` | The Windows installer (64-bit Windows) |
| `FolioForge-<version>.apk` | The Android app (Android 11 or later) |
| `ffmpeg-source-for-folio-forge-<version>.tar.xz` | The FFmpeg source this version was built with (see below) |
| `SHA256SUMS.txt` | The SHA-256 of every file above |

Only the last version of each Release Year is kept, with the current Release Year's newest version. They stay available to download for as long as Folio Forge is sold. A lifetime licence owns the Release Year it was bought in and the next; the account page shows which versions your licence owns.

## Check a download

Compare the file's SHA-256 with the line for it in the release's `SHA256SUMS.txt` (the download page shows the same value). They must match exactly; if they don't, delete the file and download it again from the download page.

**Windows (PowerShell):**

```powershell
Get-FileHash -Algorithm SHA256 "$env:USERPROFILE\Downloads\Folio-Forge-Setup-<version>.exe"
```

**macOS or Linux** (with `SHA256SUMS.txt` in the same folder):

```sh
sha256sum -c SHA256SUMS.txt --ignore-missing
```

**Android:** check the APK on a computer before copying it to your phone, or download it on the phone from the download page, which links to these same files.

The Android app is signed with Samurai Dynasty Online's release key. Its certificate's SHA-256 fingerprint is:

```
BE:02:60:47:88:D9:90:34:9B:14:A4:55:0A:1B:07:C2:AD:95:0F:0B:00:5A:83:68:A4:DF:66:DE:43:91:24:7A
```

With the Android SDK's build tools you can check it: `apksigner verify --print-certs FolioForge-<version>.apk`.

Until the Windows installer is code-signed, Windows may say the publisher is unrecognised: choose **More info**, then **Run anyway**.

## FFmpeg's source

Folio Forge for Windows is built on Electron, which includes Chromium, which includes FFmpeg under the GNU Lesser General Public License 2.1 or later. Each release carries the complete FFmpeg source of the Electron it was built with, with a `README-FOLIO-FORGE.txt` naming the Electron, Chromium and FFmpeg revisions. Folio Forge itself is proprietary software under its License Agreement.

## Questions

Email support@samuraidynasty.online. This repository takes no issues or pull requests.

© Samurai Dynasty Online. All rights reserved.
