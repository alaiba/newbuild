# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

> For ChatGPT Work / fresh-agent sessions: start with [`WORK.md`](WORK.md).

## Purpose

Greenfield self-built workstation optimized primarily for very heavy Java/Android development, WSL2/containers/local services and occasional VMs, with gaming secondary.

Design philosophy: **stability first, utility per leu second, speculation last**.

## Current architecture and procurement state

| Component | Current configuration | State |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D** Box/WOF `100-100000719WOF` | **Installed; BIOS detects model** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Installed; UEFI first POST passed (BIOS 3287)** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24), DDR5-5600, non-ECC, 1DPC** | **Installed A2/B2; 48 GB detected, EXPO off** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | **Installed; initial BIOS 36 °C** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Assembled** |
| Case airflow | **2x included 140 mm PWM**, front intake + rear exhaust | **Connected, monitored in BIOS** |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Installed, detected in BIOS** |
| Storage expansion | `M.2_2` + `M.2_3` free; reuse healthy existing SATA drives for cold/bulk data | Selected |
| Storage RAID/cache/tiering | **None** | Selected |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Installed and operating** |
| GPU | Existing **RTX 3060 12 GB** | **Not installed yet (iGPU baseline)** |
| Host OS | **Windows 11 Pro x64** | **Pending installation** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Pending** |
| UPS | none | No purchase planned |
| Dedicated surge protector | none | No purchase planned |

## Executed orders — 2026-09-01

| Provider | Order | Total incl. VAT |
|---|---|---:|
| EvoMAG | CPU + motherboard + T710 SSD + PSU | **6,531.95 lei** |
| Vexio | `BG074` case + Phantom Spirit 120 standard | **662.98 lei** |
| CEL.ro | Crucial Pro `CP2K24G56C46U5`, 48 GB / 2x24 GB | **2,899.00 lei** |
| **Total committed** | all required newly purchased hardware | **10,093.93 lei** |

EvoMAG total includes 11.99 lei courier. Vexio shipping was 0.00 lei. No separate shipping charge was shown in the supplied CEL.ro checkout total.

See [`docs/purchases-2026-09-01.md`](docs/purchases-2026-09-01.md).

## Key architecture choices

- **48 GB / 2x24 GB / 1DPC** is final and purchased.
- If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit; do **not** add a second pair as the planned upgrade path.
- ECC is not used.
- `M.2_1` hosts the purchased **2 TB Crucial T710 Gen5 primary SSD**; `M.2_2` and `M.2_3` remain free for later expansion.
- No separate system/work SSD split, SSD cache layer, automatic tiering or RAID initially.
- **Phantom Spirit 120 + Pure Base 501 `BG074`** is the final purchased cooling/chassis combination.
- **Pure Power 13 M 850W** is purchased; 1000–1200 W remains unnecessary.
- Reuse the RTX 3060 until a concrete replacement need appears.
- Windows 11 Pro is the selected host OS; the license is already available and outside procurement.

## Procurement position — 2026-09-01

**Procurement is complete. No required new hardware remains to be purchased.**

The procurement statement above reflects the September order state; current assembly and commissioning status is below.

Critical arrival controls:

- motherboard: confirm **`90MB1LT0-M0EAY0`** on the box;
- RAM: confirm **`CP2K24G56C46U5`**, 48 GB as 2x24 GB;
- case: confirm **`BG074`**;
- cooler: confirm **standard Phantom Spirit 120**, not SE/EVO;
- SSD: confirm **`CT2000T710SSD8`**, bare/non-heatsink;
- PSU: confirm **`BP027EU`**;
- CPU: confirm **`100-100000719WOF`** Box/WOF.

## Repository structure

- [`WORK.md`](WORK.md) — mandatory fresh-session / ChatGPT Work entrypoint
- [`docs/final-build.md`](docs/final-build.md) — source-of-truth architecture and commissioning state
- [`docs/bring-up-2026-10-31.md`](docs/bring-up-2026-10-31.md) — first POST, observed BIOS readings and remaining tests
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened/superseded decisions
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — completed procurement plan/record
- [`docs/final-order-plan-2026-08-31.md`](docs/final-order-plan-2026-08-31.md) — executed order record
- [`docs/purchases-2026-09-01.md`](docs/purchases-2026-09-01.md) — purchase ledger
- [`docs/checkout-checklist.md`](docs/checkout-checklist.md) — arrival verification workflow
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/constraints
- [`docs/components/`](docs/components/) — component deep dives

## Current stage — 2026-10-31

**Assembled; first UEFI POST passed using Ryzen integrated graphics (without RTX 3060).** ASUS BIOS 3287 identifies Ryzen 9 9950X3D, 48 GB DDR5-5600 A2/B2, and Crucial T710 2 TB in M.2_1. Initial idle temperatures: CPU **36 °C**, motherboard **28 °C**; CPU and both case fan groups report RPM.

Next: install Windows 11 Pro to the T710 with RTX 3060 and old SATA drives absent, verify stability and peripheral function, then add GPU, WSL2/Ubuntu and eventually BitLocker. Windows installation and sustained-load stability have **not** yet been reported.

