# Microsoft Family Safety — Local Admin Recovery Guide

> ⚠️ **For educational and recovery purposes only.**  
> This guide helps device owners regain access to their own machines. See [DISCLAIMER.md](DISCLAIMER.md) before proceeding.

---

## Table of Contents

- [What This Guide Covers](#what-this-guide-covers)
- [What This Method Can & Cannot Do](#what-this-method-can--cannot-do)
- [Requirements](#requirements)
- [Quick Start](#quick-start)
- [Detailed Guides](#detailed-guides)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

---

## What This Guide Covers

Microsoft Family Safety enforces restrictions at **two levels**:

| Level | Examples | Can be bypassed locally? |
|---|---|---|
| **Local** (on the device) | Installed app, screen time app, local account restrictions | ✅ Yes |
| **Cloud** (Microsoft servers) | Web filters, app blocks, activity reports, screen time limits | ❌ No |

This guide focuses exclusively on **local** recovery — enabling or resetting the built-in Windows Administrator account using an offline boot environment.

---

## What This Method Can & Cannot Do

### ✅ Can Do
- Enable the hidden built-in Administrator account
- Reset or clear the local Administrator password
- Uninstall Microsoft Family Safety from the device
- Install or run programs under an unrestricted local admin account
- Create new local accounts

### ❌ Cannot Do
- Remove cloud-based Family Safety restrictions (these are enforced by Microsoft servers tied to the Microsoft account)
- Bypass Microsoft account PIN/password for online-only accounts
- Work on BitLocker or Device Encryption protected drives
- Hide activity from Microsoft Family Safety activity reports

> **Still visible:** Even after uninstalling the local app, Microsoft may log device usage if the device remains signed into a supervised Microsoft account.

---

## Requirements

| Item | Notes |
|---|---|
| USB flash drive (≥ 8 GB) | **All data on it will be erased** |
| A second working computer | To download tools and prepare the USB |
| Internet connection | For downloads |
| [Rufus](https://rufus.ie) | Free, open-source USB creation tool |
| [Hiren's BootCD PE](https://www.hirensbootcd.org) | Free Windows PE recovery environment (~3 GB ISO) |

### Compatibility Notes
- ✅ Works on local accounts and most older Family Safety setups
- ✅ UEFI and legacy BIOS systems both supported (use GPT for UEFI)
- ❌ Will NOT work if the drive uses BitLocker or Device Encryption
- ℹ️ Most 2015+ computers use UEFI → use GPT + NTFS in Rufus

---

## Quick Start

If you're already familiar with bootable USBs:

1. Download [Hiren's BootCD PE](https://www.hirensbootcd.org) (`HBCD_PE_x64.iso`)
2. Flash it to a USB with [Rufus](https://rufus.ie) (GPT + NTFS + ISO Image mode)
3. Boot the target computer from the USB
4. Open **Start → Utilities → Security → Passwords → Windows Login Unlocker**
5. Enable and reset the built-in **Administrator** account
6. Reboot, log in as Administrator, uninstall Family Safety

---

## Detailed Guides

Step-by-step walkthroughs for each stage:

- [Step 1 — Download Hiren's BootCD PE](docs/01-download-hirens.md)
- [Step 2 — Download & Run Rufus](docs/02-download-rufus.md)
- [Step 3 — Create the Bootable USB](docs/03-create-bootable-usb.md)
- [Step 4 — Boot from USB on the Target Computer](docs/04-boot-from-usb.md)
- [Step 5 — Enable & Reset the Administrator Account](docs/05-enable-admin-account.md)
- [Step 6 — After Reboot: Uninstall Family Safety](docs/06-after-reboot.md)
- [Troubleshooting](docs/troubleshooting.md)

---

## FAQ

**Q: Will this remove screen time limits from my Microsoft account?**  
A: No. Screen time limits are enforced server-side by Microsoft. Uninstalling the app removes local enforcement but your account may still be restricted.

**Q: What if I see "BitLocker" during boot?**  
A: This method will not work on BitLocker-encrypted drives. You'll need the BitLocker recovery key first.

**Q: My computer skips the boot menu — what do I do?**  
A: Fast Boot may be enabled in UEFI. Enter BIOS/UEFI settings (usually Del or F2 at startup) and disable Fast Boot, then try again.

**Q: The Administrator account doesn't appear at the login screen after reboot.**  
A: The account was likely enabled but Windows is hiding it. See [Troubleshooting](docs/troubleshooting.md#admin-account-not-visible).

**Q: Is this legal?**  
A: Laws vary by jurisdiction. Generally, this is legal when you own the device or have permission from the owner. See [DISCLAIMER.md](DISCLAIMER.md).

---

## Contributing

Improvements, corrections, and additional troubleshooting scenarios are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License

MIT — see [LICENSE](LICENSE).
