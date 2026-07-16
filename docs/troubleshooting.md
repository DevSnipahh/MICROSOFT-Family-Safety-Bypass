# Troubleshooting

Common problems and their solutions.

---

## Computer Won't Boot from USB

**Symptom:** Windows loads normally instead of Hiren's BootCD PE.

**Causes & fixes:**

1. **Wrong key timing** — Press the boot menu key immediately after powering on, before anything appears on screen. Try repeatedly tapping it, not holding.

2. **Fast Boot enabled** — Enter BIOS/UEFI settings (usually `Del` or `F2`) and disable **Fast Boot** or **Fast Startup**.

3. **Secure Boot blocking the USB** — In BIOS/UEFI, find **Secure Boot** and set it to **Disabled**. Some systems require you to enroll the boot medium's key instead.

4. **USB not in boot order** — In BIOS/UEFI, find **Boot Order** or **Boot Priority** and move your USB to the top.

5. **Wrong partition scheme** — If the USB was flashed as MBR but the system is UEFI-only, reflash with Rufus using **GPT**.

---

## BitLocker Prompt {#bitlocker-prompt}

**Symptom:** After selecting the USB boot entry, you see a BitLocker recovery key prompt before any tools load.

**Explanation:** The drive is encrypted with BitLocker (or Device Encryption). Hiren's cannot access the Windows files without the decryption key.

**Fix:** You need the **BitLocker Recovery Key**.

- Sign into https://account.microsoft.com/devices with the Microsoft account linked to the device.
- Go to **Manage** → find your device → **View BitLocker recovery keys**.
- Enter the key at the prompt to unlock the drive, then proceed normally.

If you don't have the key, this method will not work.

---

## Administrator Account Not Visible After Reboot {#admin-account-not-visible}

**Symptom:** You reboot and the Administrator account doesn't appear on the login screen.

**Fixes:**

**Option 1 — Force show via registry (from Hiren's):**  
Boot back into Hiren's and open a registry editor. Navigate to:
```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\SpecialAccounts\UserList
```
Set `Administrator` (DWORD) to `1`.

**Option 2 — Command line (from Hiren's or another admin account):**  
Open a command prompt and run:
```cmd
net user Administrator /active:yes
```

**Option 3 — Verify the account was actually enabled:**  
Boot back into Hiren's, reopen Windows Login Unlocker, and confirm the account shows as **Active/Enabled**.

---

## Windows Login Unlocker Doesn't Detect Any Drives

**Symptom:** The tool opens but shows no Windows installations.

**Causes & fixes:**

1. **Drive is using a non-standard storage controller** — Some NVMe or RAID configurations require drivers. Look for a **Load Drivers** option in the tool.

2. **Drive uses a different file system** — Uncommon, but possible. Try **NTPWEdit** as an alternative (also in Hiren's).

3. **Wrong tool selected** — Ensure you're running a Windows account tool, not a Linux password tool.

---

## The Password I Set Doesn't Work

**Symptom:** You log out of Hiren's, reboot, and the password you set for Administrator doesn't work.

**Fix:** Boot back into Hiren's and reset the password again. This time:
- Leave the password **blank** (press Enter/OK without typing anything) to remove the password entirely.
- Reboot and click the Administrator tile without entering a password.

---

## Microsoft Family Safety Won't Uninstall

**Symptom:** The app appears in Apps but the Uninstall button is grayed out or fails.

**Fix — PowerShell (run as Administrator):**
```powershell
Get-AppxPackage *FamilySafety* -AllUsers | Remove-AppxPackage -AllUsers
```

If that fails, try:
```powershell
Get-AppxProvisionedPackage -Online | Where-Object DisplayName -like "*FamilySafety*" | Remove-AppxProvisionedPackage -Online
```

---

## Still Need Help?

Open an issue on the repository with:
- Your Windows version (10 / 11)
- Your computer brand and model
- Exactly where in the process you got stuck
- Any error messages you saw
