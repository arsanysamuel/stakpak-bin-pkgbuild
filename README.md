# stakpak-bin AUR Package

This repository contains the **PKGBUILD** and **.SRCINFO** files for the [stakpak-bin](https://aur.archlinux.org/packages/stakpak-bin) package on the Arch User Repository (AUR).

## Overview
The package provides prebuilt binaries of the [Stakpak Agent](https://github.com/stakpak/agent) for Arch Linux users.  
This repository is used to maintain and publish updates automatically to the AUR.

## Files
- **PKGBUILD** – Defines how the package is built and installed.  
- **.SRCINFO** – Metadata file required by the AUR.  
- **.github/workflows/publish.yml** – GitHub Actions workflow that checks for new releases and updates the AUR package automatically.

## Automation
A scheduled GitHub Actions workflow:
1. Checks the latest release of [`stakpak/agent`](https://github.com/stakpak/agent).  
2. Compares it with the version currently published on AUR.  
3. Updates `pkgver`, regenerates checksums, and pushes changes to both GitHub and AUR if a new version is available.

## Manual Update
To update manually:
```bash
makepkg --printsrcinfo > .SRCINFO
git add PKGBUILD .SRCINFO
git commit -m "Update to <new version>"
git push
```
