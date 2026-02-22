# ⚠️ Bypassing Microsoft Family Safety via Local Admin Access  
**For educational and recovery purposes only**

**Important Legal & Ethical Notice**  
This guide explains how to regain access to a local Administrator account on a Windows PC using offline tools.  
**This is NOT a direct bypass of Microsoft Family Safety cloud restrictions** — those are enforced server-side and tied to the Microsoft account.

What this method **can** do:
- Enable/reset a built-in local Administrator account
- Allow uninstallation of the Microsoft Family Safety app (or other software) **locally**
- Install/run programs without the restricted user noticing (if you switch to the admin account)

What this method **cannot** do:
- Remove cloud-based Family Safety restrictions (screen time, app blocks, web filters)
- Bypass Microsoft account PIN/password requirements if the account is online-only
- Work on BitLocker-encrypted drives (or any full-disk encryption)

**You may still be detected** by Family Safety activity reports or if the organizer checks installed software / event logs.

**Proceed only if you have legitimate ownership / permission to access the device.**

---

## Requirements

- USB flash drive (≥8 GB — **all data will be erased**)
- A second working computer (to prepare the USB)
- Internet connection (for downloads)
- Rufus (portable or installer version)

**Important compatibility notes**:
- Works best on local accounts or older Family Safety setups
- **Will NOT work** if the drive is encrypted with BitLocker / Device Encryption
- UEFI systems are common in 2025–2026 → prefer GPT + NTFS

---

## Step 1: Download Hiren's BootCD PE

Hiren's BootCD PE is a free, modern Windows PE recovery environment with many troubleshooting utilities (including password tools).

1. On the second computer, go to the **official** website:  
   https://www.hirensbootcd.org

2. Click **Download** → get the latest **HBCD_PE_x64.iso** (~3 GB)

> **Security warning**  
> Always download from https://www.hirensbootcd.org to avoid tampered / malware-infected copies.

---

## Step 2: Download Rufus

Rufus is the most reliable tool for creating bootable USBs from ISOs.

1. Go to: https://rufus.ie
2. Download the latest version (portable `.exe` is fine)
3. Run it (requires admin rights)

---

## Step 3: Create Bootable USB

**⚠️ This will completely erase the USB drive.**

1. Plug in your USB stick.
2. Open Rufus.
3. **Device** → select your USB drive.
4. Click **SELECT** → choose the `HBCD_PE_x64.iso` file.
5. **Partition scheme**:
   - **GPT** (recommended for UEFI / modern PCs 2015+)
   - **MBR** (only for very old BIOS systems)
6. **Target system** → usually auto-selected (UEFI or BIOS)
7. **File system** → **NTFS** (default & recommended)
8. Leave other settings default.
9. Click **START**.
10. If asked, choose **ISO Image mode (Recommended)**.
11. Confirm formatting → wait until **READY** appears.

---

## Step 4: Boot from USB on Target Computer

1. Insert the USB into the **target** (restricted) computer.
2. Power on / restart.
3. Enter the **boot menu** immediately by pressing (repeat key press):
   - **F12**, **F9**, **F10**, **F11**, **Esc**, or **Del**  
     (varies by brand: Dell=F12, HP=F9/Esc, Lenovo=F12/F1, ASUS=F8/Esc, etc.)
4. Select the USB device (may show as UEFI: USB name or just USB).
5. Press Enter → Hiren's BootCD PE should load (Windows-like desktop).

---

## Step 5: Enable & Reset Built-in Administrator Account

Once the desktop loads:

1. Open the **Start menu** (or desktop shortcut) → navigate to:  
   **Utilities** → **Security** → **Passwords**

2. Launch one of these tools:
   - **Windows Login Unlocker** (Recommended)
   - OTHER TOOLS HAVE BEEN REMOVED FROM THIS TUTORIAL.

3. The tool should auto-detect Windows installations → select the correct one (usually the only / main drive).
4. It will list local user accounts.
5. Locate **Administrator** (built-in hidden admin account).
6. **Right-click** → **Enable** (if disabled)
7. **Right-click** → **Reset password** / **Clear password** / **Unlock**
   - Set a new password (or leave blank for no password)
   - Confirm / Apply changes

8. Close the tool → **reboot** normally (remove USB before restart).

After reboot:
- At login screen, you should now see the **Administrator** account.
- Log in (with the password you set, or blank).
- You now have full local admin rights → you can:
  - Uninstall Microsoft Family Safety
  - Install software
  - Modify settings
  - Create new local accounts, etc.

---

**Use responsibly.**
