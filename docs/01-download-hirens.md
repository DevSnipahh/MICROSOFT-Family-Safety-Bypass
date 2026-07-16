# Step 1 — Download Hiren's BootCD PE

Hiren's BootCD PE is a free, modern Windows PE (Preinstallation Environment) that boots from USB and includes dozens of recovery and password tools. It requires no installation on the target computer.

## Download

1. On a **second working computer** (not the restricted one), open a browser.
2. Go to the **official website only**:  
   **https://www.hirensbootcd.org**

> ⚠️ **Security warning:** Only download from the official site above.  
> Third-party mirrors may distribute modified or malware-infected copies.  
> The official ISO is always named `HBCD_PE_x64.iso`.

3. Click **Download** on the homepage.
4. Wait for the download to complete (~3 GB).

## Verify the Download (Recommended)

The official site publishes SHA-256 checksums. Verifying the file ensures it wasn't corrupted or tampered with.

**On Windows (PowerShell):**
```powershell
Get-FileHash .\HBCD_PE_x64.iso -Algorithm SHA256
```

Compare the output hash against the one shown on the Hiren's BootCD website.

---

**Next:** [Step 2 — Download & Run Rufus](02-download-rufus.md)  
**Back:** [README](../README.md)
