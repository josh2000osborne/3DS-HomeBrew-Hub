# 3DS Homebrew Hub — Installation Instructions (Old 3DS, 11.17.0-50)

> **Independent companion checklist, not a replacement for [3ds.hacks.guide](https://3ds.hacks.guide/).** Prepared 19 October 2026 for this public repository. This project is not affiliated with or endorsed by the 3DS Hacks Guide maintainers or Nintendo. Always follow the live official guide if it differs from this summary.

## Supported target
- **Old Nintendo 3DS**, system version **11.17.0-50** (region suffix **E/U/J/K** must be checked on the console).
- This document is **not** a New 3DS / New 2DS XL guide.
- An **Old 3DS XL** or **Old 2DS** may share a category in the official selector, but confirm there before using its method.
- This companion assumes access to a **Mac / Windows / Linux computer** with an SD card reader for the MSET9 CLI workflow.

## Before doing anything
1. Charge the console, check that the SD card works and copy **all SD card contents** to a safe folder on your computer.
2. Power off the console, hold **SELECT**, power on while holding SELECT. **If a Luma3DS or other CFW menu appears, STOP:** use the official [existing CFW path](https://3ds.hacks.guide/get-started.html), not a fresh installation.
3. Open **System Settings**; read the version on the top screen, including its final **region letter** (for example, `11.17.0-50E`). Select **Old 3DS/2DS** plus the exact firmware on the [official Get Started selector](https://3ds.hacks.guide/get-started.html).
4. **Follow the method returned by that selector.** As of this document's review, **MSET9** is an available method for Old 3DS systems at 11.17; the selector remains authoritative because routes can change.
5. Do not perform system formatting, random NAND writes, or “downgrade” steps from old video tutorials. A bad step may make the console unbootable.

## Files and tools — use current official links
For the **MSET9 CLI** route, follow the current [MSET9 CLI page](https://3ds.hacks.guide/installing-boot9strap-%28mset9-cli%29.html), which specifies:
- Latest **MSET9 ZIP** from that page's official download link.
- **Python 3.x** on your Mac/PC (on macOS check `python3 -V`). Avoid a Microsoft Store Python install if using Windows, as the guide cautions.
- The SD card and a working computer SD card reader. Download any additional files **only as instructed by the current official page**.
- Later, for [Finalizing Setup](https://3ds.hacks.guide/finalizing-setup), obtain the page's current `finalize.romfs` and `x_finalize_helper.firm` downloads.

**Do not trust stale bundled installation packs** just because they are in a public GitHub repository. Compare with the official guide and source releases before using any files.

## Installation overview — follow the live official steps at every stage
The instructions below explain the stages, but do **not** replace the exact timed SD-card and console interaction sequence on the source pages.

### A. Prepare MSET9
1. Extract MSET9 ZIP contents onto the **root** of the 3DS SD card as directed.
2. Run the platform-appropriate MSET9 launcher: on macOS, the `MSET9-macOS.command` launcher; on Linux or where specified, `python3 mset9.py`.
3. Choose the correct **Old 3DS and version** option shown in MSET9; never guess menu numbers.
4. Follow **Section I — Prep Work** of the [MSET9 CLI guide](https://3ds.hacks.guide/installing-boot9strap-%28mset9-cli%29.html), including its temporary HOME Menu data changes and readiness checks. Temporary disappearance of user apps can be expected during this process; the cleanup step restores the profile.

### B. Trigger the exploit and install boot9strap
1. Follow **Section II — MSET9** exactly. It requires specific navigation in **System Settings → Data Management** and temporarily handling the SD card **while the console remains powered on**. Do not improvise.
2. Once **SafeB9SInstaller** opens, use the confirmation sequence **shown on the console screen**; do not force the process if its checks fail.
3. After installation, the console should open the **Luma3DS configuration menu**. Leave default settings unless the live guide states otherwise, then save/reboot.

### C. Mandatory MSET9 cleanup
**Do not skip this.** Follow **Section IV — Removing MSET9** in the official guide using the MSET9 script to remove the trigger and temporary MSET9 changes. This is essential to avoid errors and return your original user data.

### D. Finalise setup and create backups
1. Continue to [Finalizing Setup](https://3ds.hacks.guide/finalizing-setup) without skipping ahead.
2. Follow the page to place `finalize.romfs` at the SD root and `x_finalize_helper.firm` in `/luma/payloads/`; run its on-console finalisation workflow as directed.
3. Finalisation sets up tools such as **GodMode9, Checkpoint, Universal-Updater, FBI, Anemone3DS and Homebrew Launcher Loader**.
4. **Back up** `/gm9/backups/` (including the console-specific **SysNAND backup** and `essential.exefs`) to **at least two safe places**. These are **private recovery files**, not redistributable resources for this project.
5. Verify the console boots normally and that installed tools launch. Keep an offline copy of the original SD contents and backups.

## Troubleshooting and recovery
- [MSET9 troubleshooting](https://3ds.hacks.guide/troubleshooting-mset9.html)
- [Finalizing Setup troubleshooting](https://3ds.hacks.guide/troubleshooting-finalizing-setup.html)
- If the console reports a failure, **stop** and consult the matching troubleshooting section before modifying the SD card further.
- Never share `essential.exefs`, NAND dumps, personal game saves or other device-specific data in public issues or commits.

## Public repository integrity and licensing
- Only redistribute third-party assets if their licences/permissions allow it; provide original author, project URL, version and licence attribution.
- Prefer official download links and checksums over mirrored binaries. No copyrighted game ROMs, keys, personal NAND dumps or console identifiers.
- Link to the official guide rather than copying its instructions or images wholesale.
- Record a **last verified** date and re-check the guide periodically.

## Source of truth
- [3DS Hacks Guide — Get Started](https://3ds.hacks.guide/get-started.html)
- [Installing boot9strap — MSET9 CLI](https://3ds.hacks.guide/installing-boot9strap-%28mset9-cli%29.html)
- [Finalizing Setup](https://3ds.hacks.guide/finalizing-setup)
- [MSET9 troubleshooting](https://3ds.hacks.guide/troubleshooting-mset9.html)

**Remember:** The console's exact model, firmware and region, plus the **current** official selector, take priority over this static document.
