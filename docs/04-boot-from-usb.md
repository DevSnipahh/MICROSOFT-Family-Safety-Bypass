# Step 4 — Boot from USB on the Target Computer

## Insert & Power On

1. Plug the prepared USB drive into the **target (restricted) computer**.
2. Power on or restart the computer.
3. **Immediately** start pressing the boot menu key repeatedly (before Windows starts loading).

## Boot Menu Keys by Brand

| Brand | Common Boot Menu Key | BIOS/UEFI Setup Key |
|---|---|---|
| **Dell** | `F12` | `F2` |
| **HP** | `F9` or `Esc` | `F10` or `Esc` |
| **Lenovo** | `F12` or `F1` | `F1` or `F2` |
| **ASUS** | `F8` or `Esc` | `Del` or `F2` |
| **Acer** | `F12` | `Del` or `F2` |
| **MSI** | `F11` | `Del` |
| **Samsung** | `F2` | `F2` |
| **Toshiba** | `F12` | `F2` |
| **Surface** | Hold Volume Down while pressing Power | — |

> **Tip:** If you miss the window, restart and try again — you need to press the key before the Windows spinner appears.

## Selecting the USB in the Boot Menu

1. A list of bootable devices appears.
2. Select your USB drive. It may be labeled:
   - `UEFI: [USB brand name]`
   - `USB: [drive name]`
   - `Removable Devices`
3. Press Enter.

## What to Expect

Hiren's BootCD PE loads a Windows-like desktop environment. This is running entirely from the USB — nothing on the hard drive is modified yet.

> **If you see a BitLocker prompt:** This method will not work without the BitLocker recovery key. See [Troubleshooting](troubleshooting.md#bitlocker-prompt).

---

**Next:** [Step 5 — Enable & Reset the Administrator Account](05-enable-admin-account.md)  
**Back:** [Step 3 — Create the Bootable USB](03-create-bootable-usb.md)
