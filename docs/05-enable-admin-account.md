# Step 5 — Enable & Reset the Built-in Administrator Account

Once Hiren's BootCD PE has loaded to a desktop, follow these steps to enable the hidden Administrator account on the target Windows installation.

## Open the Password Tool

1. Click **Start** (bottom left of the Hiren's desktop).
2. Navigate to: **Utilities → Security → Passwords**
3. Launch **Windows Login Unlocker** (recommended).

> **Alternative:** If Windows Login Unlocker is unavailable, look for **NTPWEdit** or **Offline NT Password & Registry Editor** in the same menu.

## Using Windows Login Unlocker

1. The tool will **auto-detect** Windows installations on the hard drive.
2. Select your Windows installation (usually the only one listed — typically on `C:` or `D:`).
3. A list of local user accounts appears.
4. Find **Administrator** (the built-in hidden account — not your personal account name).

### Enable the Account

- **Right-click** on **Administrator** → select **Enable** (if it shows as Disabled).

### Reset the Password

- **Right-click** on **Administrator** → select **Reset Password** / **Clear Password** / **Unlock**.
- Set a new password, or leave it **blank** for no password.
- Click **Apply** / **OK** to confirm.

5. Close the tool.

## Reboot

1. Remove the USB drive.
2. Restart the computer normally.

> Keep the USB — you may need it again if something doesn't go as expected.

---

**Next:** [Step 6 — After Reboot](06-after-reboot.md)  
**Back:** [Step 4 — Boot from USB](04-boot-from-usb.md)
