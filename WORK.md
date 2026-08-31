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

## Current objective

The architecture is closed and **procurement is complete**.

All required new hardware has been purchased. Do not perform further component shopping or price optimization unless a delivered item is wrong, damaged, cancelled, or a material compatibility defect is discovered.

The current task is:

1. verify every delivered component physically against the exact identity below;
2. preserve invoices, serial numbers and packaging through return windows;
3. assemble the system;
4. perform BIOS/firmware bring-up and stability validation;
5. install Windows 11 Pro, WSL2 and Ubuntu after hardware stability is established.

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
| CPU | **AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`** | **Purchased — EvoMAG; arrival verification pending** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Purchased — EvoMAG; exact box SKU verification pending** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2x24 GB DDR5-5600, non-ECC** | **Purchased — CEL.ro; arrival verification pending** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Purchased — Vexio; arrival verification pending** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Purchased — Vexio; arrival verification pending** |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink | **Purchased — EvoMAG; arrival verification pending** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | **Purchased — EvoMAG; arrival verification pending** |
| GPU | existing **RTX 3060 12 GB** | Already owned / reuse |
| Host OS | **Windows 11 Pro x64** | License already available |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | Selected |
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
- install in **A2/B2** and commission at **Auto/JEDEC first**.

Do not add a second pair later. If more capacity is eventually required, replace this pair with a larger matched two-DIMM kit.

### Cooler
- required: **Thermalright Phantom Spirit 120 standard**;
- reject SE/EVO substitution;
- confirm both 120 mm fans and AM5 mounting hardware.

### Case
- required: **be quiet! Pure Base 501 Airflow Black `BG074`**;
- confirm non-window Airflow Black and both included 140 mm PWM fans.

### SSD
- required: **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink;
- install in motherboard `M.2_1` CPU PCIe 5.0 x4 under the ASUS heatsink.

### PSU
- required: **be quiet! Pure Power 13 M 850W `BP027EU`**;
- use only modular cables supplied with this exact PSU.

## What Work should do now

1. Treat every required new hardware component as **purchased**, not a shopping candidate.
2. Verify box labels, seals, condition and accessories before installation.
3. Record serials/photos where useful and retain packaging.
4. Proceed to assembly after all delivered identities pass.
5. Update to a current stable BIOS before enabling BitLocker.
6. Install RAM in A2/B2 and begin with Auto/JEDEC.
7. Validate memory, CPU thermals, T710 firmware/SMART/temperature, GPU, storage and sleep/network behavior.
8. Install Windows 11 Pro + WSL2/Ubuntu after the baseline hardware is stable.
9. Enable BitLocker only after firmware/driver/storage stability is established.
