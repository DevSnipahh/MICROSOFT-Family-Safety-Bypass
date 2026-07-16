# Step 3 — Create the Bootable USB

> ⚠️ **This will completely erase everything on the USB drive.**  
> Back up any files you need before continuing.

## Recommended Rufus Settings

| Setting | Value | Notes |
|---|---|---|
| **Device** | Your USB drive | Double-check the drive letter — wrong choice = data loss |
| **Boot selection** | `HBCD_PE_x64.iso` | Click **SELECT** to browse for it |
| **Partition scheme** | **GPT** | Recommended for any PC made after ~2015 (UEFI) |
| **Target system** | UEFI (non-CSM) | Auto-selected when GPT is chosen |
| **File system** | **NTFS** | Default and recommended |
| **Cluster size** | Default | Leave as-is |
| **Volume label** | Any | You can rename it if you like |

## Steps

1. Plug in your USB drive.
2. Open Rufus (run as Administrator if prompted).
3. Under **Device**, select your USB drive.
4. Click **SELECT** → browse to and open `HBCD_PE_x64.iso`.
5. Set **Partition scheme** to **GPT**.
6. Set **File system** to **NTFS**.
7. Click **START**.
8. If asked to choose a write mode, select **Write in ISO Image mode (Recommended)**.
9. Confirm the format warning → click **OK**.
10. Wait for the **READY** status bar — this typically takes 5–15 minutes.
11. Close Rufus. Safely eject the USB.

## Partition Scheme Reference

| Your Computer | Partition Scheme |
|---|---|
| Made after 2015 (most laptops/desktops) | **GPT** |
| Very old BIOS system (pre-2012) | **MBR** |
| Not sure | Try **GPT** first |

---

**Next:** [Step 4 — Boot from USB](04-boot-from-usb.md)  
**Back:** [Step 2 — Download Rufus](02-download-rufus.md)
