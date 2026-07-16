# Step 6 — After Reboot: Uninstall Family Safety

## Logging In as Administrator

1. At the Windows login screen, the **Administrator** account should now appear.
   - If it doesn't appear, see [Troubleshooting — Admin account not visible](troubleshooting.md#admin-account-not-visible).
2. Log in with the password you set (or leave blank if you cleared it).
3. You now have **full local Administrator access**.

## Uninstall Microsoft Family Safety

### Method A — Settings (Recommended)

1. Open **Settings** → **Apps** → **Installed apps** (or **Apps & features** on Windows 10).
2. Search for **Microsoft Family Safety**.
3. Click the three-dot menu → **Uninstall**.
4. Confirm.

### Method B — PowerShell

Open PowerShell as Administrator and run:

```powershell
Get-AppxPackage *FamilySafety* | Remove-AppxPackage
```

### Method C — Control Panel (Older Windows)

1. Open **Control Panel** → **Programs** → **Uninstall a program**.
2. Find **Microsoft Family Safety** → right-click → **Uninstall**.

## Optional: Create a New Local Admin Account

To have a permanent admin account that isn't the hidden built-in Administrator:

```powershell
# Create a new local account
net user YourUsername YourPassword /add

# Add it to the Administrators group
net localgroup Administrators YourUsername /add
```

Replace `YourUsername` and `YourPassword` with your preferred credentials.

## ⚠️ Reminder: Cloud Restrictions Still Apply

If the device remains signed into a supervised Microsoft account, cloud-based restrictions (web filters, app blocks, screen time) may still be enforced through the Microsoft account itself. To fully escape them, you would need to sign out of the supervised Microsoft account and use a local account or an unsupervised Microsoft account instead.

---

**Done!**  
**Back:** [Step 5 — Enable & Reset the Administrator Account](05-enable-admin-account.md)  
**See also:** [Troubleshooting](troubleshooting.md) | [README](../README.md)
