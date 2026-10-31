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

## Current objective — 2026-10-31

**Procurement complete. Assembly substantially complete, and initial UEFI POST successful with integrated Radeon graphics; no RTX 3060 installed.**

Observed in ASUS UEFI BIOS 3287: AMD Ryzen 9 9950X3D (16 cores), 48 GB Crucial DDR5-5600 in A2/B2 (EXPO disabled), Crucial T710 2 TB `CT2000T710SSD8` in M.2_1, CPU temperature 36 °C and motherboard 28 °C. Monitored fans: CPU_FAN 555 RPM, CHA_FAN1 434 RPM, CHA_FAN2 406 RPM. An 8 GB UEFI USB boot device is detected.

**Not yet demonstrated:** Windows installation, sustained CPU/memory/storage stability, both CPU fans' rotation individually, SSD SMART/firmware/temperature, USB/network/audio operation, GPU installation, or WSL2/Ubuntu.

Next: final cooler/cable/side-panel checks; Windows 11 Pro installation on the T710 with the RTX 3060 and old SATA drives disconnected; baseline validation; later GPU/WSL2 setup. Do not enable BitLocker before firmware/driver/storage stability is established.

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
| GPU | existing **RTX 3060 12 GB** | **Intentionally not installed for iGPU-only baseline** |
| Host OS | **Windows 11 Pro x64** | **Pending installation; UEFI USB detected** |
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

1. Treat procurement as complete, assembly as substantially complete, and **initial POST as passed**; do not confuse this with validated stability.
2. Refer to `docs/bring-up-2026-10-31.md` for observed values and open checks.
3. Verify cooler mounting, both CPU fans actually spinning, no fan-wire interference, rear clearance and side-panel fit before prolonged load.
4. Keep RAM Auto/JEDEC, EXPO disabled during baseline. Check whether BIOS 3287 merits an update to a current stable ASUS release.
5. Boot the verified Windows installation USB and install **Windows 11 Pro** on the new T710. Leave RTX 3060 and existing SATA drives disconnected.
6. Install AMD chipset/iGPU and other platform drivers, then check SSD SMART/firmware/temperature, memory stability, load thermals, USB/network/audio and sleep.
7. Add existing RTX 3060 and its PCIe/VGA power cable after passing iGPU-only baseline; retest.
8. Install WSL2/Ubuntu; enable BitLocker only after firmware/storage stability and protect recovery keys.
9. Preserve invoices/packaging. Retail-box SKU evidence for CPU, motherboard and PSU regional suffix remains unrecorded.

