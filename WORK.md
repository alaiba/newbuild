# ChatGPT Work Handoff

Use this file as the mandatory entrypoint for any fresh ChatGPT Work session or other agent operating on this repository.

## Authority and precedence

When repository files disagree, use this precedence order:

1. `WORK.md` — current handoff contract and operating rules.
2. `docs/final-build.md` — current source-of-truth architecture and purchase state.
3. `docs/decisions.md` — closed/superseded decisions and rationale.
4. `docs/procurement-plan-2026-08-31.md` — procurement record/policy.
5. `docs/final-order-plan-2026-08-31.md` — executed order state.
6. `docs/purchases-2026-09-01.md` — executed purchase ledger.
7. `docs/checkout-checklist.md` — arrival verification workflow.
8. Component dossiers under `docs/components/`.
9. Other date-stamped analysis/history files.

Historical/date-stamped files may contain superseded decisions. They must never override a higher-precedence current file.

## Current objective — 2026-11-05

**Procurement complete; Windows 11 Pro installed and working. Initial UEFI POST and Windows bring-up succeeded with integrated Radeon graphics; the existing ASUS RTX 3060 has since been physically installed and recognized by Windows (user confirmed 2026-11-01).**

Observed in ASUS UEFI BIOS 3287: AMD Ryzen 9 9950X3D (16 cores), 48 GB Crucial DDR5-5600 in A2/B2 (EXPO disabled), Crucial T710 2 TB `CT2000T710SSD8` in M.2_1, CPU temperature 36 °C and motherboard 28 °C. Monitored fans: CPU_FAN 555 RPM, CHA_FAN1 434 RPM, CHA_FAN2 406 RPM. An 8 GB UEFI USB boot device is detected.

**First-week update (2026-11-05):** user reports smooth daily usage and exceptionally quiet operation. Short SSE CPU stress: 100% utilization, ~4.8 GHz average effective clock, 80.5 °C CPU peak, ~200 W package power, no reported WHEA errors. HWiNFO confirms 48 GB dual-channel DDR5 at ~5590 MT/s, 46-45-45-90; MemTest86 downloaded but **not yet run/reported**. Crucial T710 NVMe confirmed PCIe 5.0 x4; CrystalDiskMark 9 (3 runs, 1 GiB) sequential read/write **14,022.52 / 12,936.93 MB/s**, SSD peak **72 °C**, SMART 100% remaining life and no warnings. Full result table and evidence limits: `docs/bring-up-2026-10-31.md`.

**Still unverified/pending:** MemTest86 and extended system stability, individual CPU fan rotation and load RPM/curves, SSD firmware and extended write behavior, peripheral/USB/audio and post-driver Wi-Fi/Bluetooth checks, NVIDIA driver/GPU-load thermals, and WSL2/Ubuntu. Short tests do not guarantee long-term stability. Wired Ethernet was usable for obtaining drivers and updates.

Windows 11 Pro installation note: offline setup had **no working Wi-Fi or Bluetooth** out of the box. A **wired Ethernet cable was required** to obtain drivers and Windows updates. Next: complete MemTest86 (four passes), confirm wireless connectivity after driver installation, RTX 3060 driver/load checks and WSL2 work as needed. Initial CPU cooling and SSD performance/SMART checks have favorable results. Do not enable BitLocker before firmware/driver/storage stability is established.

Additional Windows CPU-Z baseline screenshots verify 9950X3D (16C/32T), ASUS B650E-E WIFI BIOS 3287, 48 GB DDR5-5600 CL46-45-45-90, Micron/Crucial 24 GB SPD module, and AMD integrated graphics. Memory controller ~1400 MHz vs DRAM ~2800 MHz (1:2). The CPU-Z screenshots alone did not establish GPU identity, but the user subsequently confirmed successful RTX 3060 installation and Windows recognition; PCIe 4.0 x16 was reported. ASUS BIOS newer than 3287 is available; evaluate only after initial stability tests.

See `docs/bring-up-2026-10-31.md` for the dated observation log. Keep packaging and invoices; some exact retail-box suffix checks are not separately documented.

## Executed orders — 2026-09-01

| Provider | Contents | Order total incl. VAT |
|---|---|---:|
| EvoMAG | CPU + motherboard + T710 SSD + PSU | **6,531.95 lei** |
| Vexio | case + CPU cooler | **662.98 lei** |
| CEL.ro | Crucial Pro 48 GB RAM kit | **2,899.00 lei** |
| **Committed total** | all required newly purchased hardware | **10,093.93 lei** |

EvoMAG includes **11.99 lei courier**. Vexio shipping was **0.00 lei**. CEL.ro order total reported by the user is **2,899.00 lei**; no separate shipping charge was shown in the supplied checkout total.

Windows 11 Pro is already available and is outside procurement. The RTX 3060 and suitable existing SATA drives are reused.

## Current selected build

| Component | Exact current selection | Procurement status |
|---|---|---|
| CPU | **AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`** | **Installed; BIOS identifies 9950X3D, 16 cores; retail box SKU not separately checked** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Installed; UEFI POST passed, BIOS 3287; exact retail box SKU not separately checked** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2x24 GB DDR5-5600, non-ECC** | **Installed A2/B2; UEFI reports 49,152 MB DDR5-5600, EXPO disabled** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Installed with TF7 paste, two CPU fans middle + rear; 36 °C BIOS idle** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Assembled; both 140 mm chassis fans connected and reporting RPM** |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink | **Installed M.2_1; exact model detected by BIOS (2,000.3 GB)** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | **Installed and powering system; exact regional suffix not independently checked** |
| GPU | existing **RTX 3060 12 GB** | **Installed after iGPU-only baseline; recognized by Windows (user confirmed 2026-11-01); driver/version/load tests not yet recorded** |
| Host OS | **Windows 11 Pro x64** | **Installed and reported operational; offline installer lacked Wi-Fi/Bluetooth, so Ethernet was used for drivers and updates** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Pending** |
| UPS | none | No purchase planned |
| Dedicated surge protector | none | No purchase planned |

## Exact arrival controls

### CPU
- required: `100-100000719WOF`, Ryzen 9 9950X3D Box/WOF;
- reject tray/OEM substitution.

### Motherboard
- required: **TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS or other similarly named variants;
- the physical box label is the decisive control.

### RAM
- required: **Crucial Pro `CP2K24G56C46U5`**;
- 48 GB total as **2x24 GB**;
- DDR5-5600, desktop non-ECC UDIMM;
- **arrival verification passed 2026-09-02** from the supplied package photo: Crucial Pro, 48 GB (2x24 GB), DDR5-5600 CL46 UDIMM, AMD EXPO / Intel XMP 3.0, matching kit identity visible on the modules;
- install in **A2/B2** and commission at **Auto/JEDEC first**.

Do not add a second pair later. If more capacity is eventually required, replace this pair with a larger matched two-DIMM kit.

### Cooler
- required: **Thermalright Phantom Spirit 120 standard**;
- reject SE/EVO substitution;
- **arrival verification passed 2026-09-15**: standard-model box/manual visible, dual-tower/seven-heatpipe heatsink, both 120 mm fans and accessory pack with AM5 mounting hardware verified from supplied photos;
- for AM5 installation, retain the motherboard's original AMD backplate; do not substitute the Intel backplate from the cooler kit;
- remove the protective film/sticker from the cooler base before installation.

### Case
- required: **be quiet! Pure Base 501 Airflow Black `BG074`**;
- **arrival verification passed 2026-09-15**: box label explicitly shows `BG074 (Black)` and interior photo confirms both included 140 mm fans;
- preserve the box label/packaging through commissioning and the return window.

### SSD
- required: **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink;
- install in motherboard `M.2_1` CPU PCIe 5.0 x4 under the ASUS heatsink.

### PSU
- required: **be quiet! Pure Power 13 M 850W `BP027EU`**;
- use only modular cables supplied with this exact PSU.

## What Work should do now

1. Treat procurement as complete, assembly as substantially complete, **initial POST as passed**, and **Windows 11 Pro as installed/working per user report**; this does not establish sustained stability.
2. Refer to `docs/bring-up-2026-10-31.md` for observed values and open checks.
3. Verify cooler mounting, both CPU fans actually spinning, no fan-wire interference, rear clearance and side-panel fit before prolonged load.
4. Keep RAM Auto/JEDEC, EXPO disabled during baseline. Check whether BIOS 3287 merits an update to a current stable ASUS release.
5. Windows 11 Pro installation completed; preserve the observation that offline setup provided neither Wi-Fi nor Bluetooth and required wired Ethernet to obtain drivers and updates. Verify both radios now work and record their installed drivers.
6. Confirm AMD chipset/iGPU and remaining platform drivers are correctly installed. Initial SSD SMART, temperature and CrystalDiskMark performance checked favorably; SSD firmware, MemTest86, longer load checks, USB/network/audio and sleep remain open.
7. **Completed:** mount existing RTX 3060 and connect its PCIe/VGA power cable; **user confirms Windows recognizes it**. Next verify NVIDIA driver version, display outputs, GPU thermals and stability under load.
8. Install WSL2/Ubuntu; enable BitLocker only after firmware/storage stability and protect recovery keys.
9. Preserve invoices/packaging. Retail-box SKU evidence for CPU, motherboard and PSU regional suffix remains unrecorded.

