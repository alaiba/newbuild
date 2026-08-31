# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Purchased — EvoMAG; arrival verification pending** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Purchased — EvoMAG; exact box SKU verification pending** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24 GB) DDR5-5600 CL46-class, 1.1 V, non-ECC** | **Purchased — CEL.ro; arrival verification pending** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | Final |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Purchased — Vexio; arrival verification pending** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Purchased — Vexio; arrival verification pending** |
| Case airflow | **2x included 140 mm PWM: front intake + rear exhaust** | Final initial layout |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Purchased — EvoMAG; arrival verification pending** |
| Bulk/cold storage | Reuse healthy existing SATA drives; `M.2_2` + `M.2_3` remain free | Final policy |
| Storage RAID/cache/tiering | None | Final |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Purchased — EvoMAG; arrival verification pending** |
| GPU | Existing **RTX 3060 12 GB** | Reuse |
| Host OS | **Windows 11 Pro x64** | Selected; license already available |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | Selected |
| UPS | None initially | Final |
| Dedicated surge protection | None required | Final |

## Executed purchases — 2026-09-01

### EvoMAG

| Item | Paid price incl. VAT |
|---|---:|
| Ryzen 9 9950X3D Box | **3,349.99 lei** |
| ASUS TUF GAMING B650E-E WIFI | **785.99 lei** |
| Crucial T710 2 TB | **1,699.99 lei** |
| be quiet! Pure Power 13 M 850W | **683.99 lei** |
| Hardware subtotal | **6,519.96 lei** |
| Courier | **11.99 lei** |
| **Order total** | **6,531.95 lei** |

### Vexio

| Item | Paid price incl. VAT |
|---|---:|
| be quiet! Pure Base 501 Airflow Black `BG074` | **415.99 lei** |
| Thermalright Phantom Spirit 120 standard | **246.99 lei** |
| Shipping | **0.00 lei** |
| **Order total** | **662.98 lei** |

### CEL.ro

| Item | Paid price incl. VAT |
|---|---:|
| Crucial Pro `CP2K24G56C46U5`, 48 GB / 2x24 GB | **2,899.00 lei** |
| **Order total** | **2,899.00 lei** |

No separate shipping charge was shown in the supplied CEL.ro checkout total.

**Total committed for all newly purchased hardware: 10,093.93 lei.**

Procurement is complete. Do not re-source or redesign around these components unless a delivered item is incorrect, damaged, cancelled, or a material defect is discovered.

Detailed transaction ledger: `docs/purchases-2026-09-01.md`.

## Motherboard — final

Selected and purchased: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

Arrival gate: the physical box must identify `90MB1LT0-M0EAY0`. Reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS, or another similarly named board.

## Memory — final

Purchased from CEL.ro for **2,899.00 lei**:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24 GB), DDR5-5600 CL46-class, 1.1 V, non-ECC UDIMM.**

Why 48 GB remains correct:

- preserves two DIMMs / 1DPC;
- preserves the Ryzen 9 9950X3D DDR5-5600 two-DIMM path;
- capacity is a concurrency limit, not an intrinsic CPU-speed lever while the workload fits;
- larger current kits did not justify their price premium.

Upgrade policy: do **not** add another 2x24 GB pair later. If measured memory pressure eventually justifies more capacity, replace this pair with a larger matched two-DIMM kit.

Bring-up:

1. install in **A2/B2**;
2. update to a current stable production BIOS;
3. boot at **Auto/JEDEC**;
4. confirm DDR5-5600 operation at conservative voltage;
5. do not enable EXPO/XMP during initial commissioning unless later justified;
6. run extended memory testing and representative Java/Android/WSL workloads.

## Cooling and chassis — final

Purchased from Vexio:

- Thermalright Phantom Spirit 120 standard — **246.99 lei**;
- be quiet! Pure Base 501 Airflow Black `BG074` — **415.99 lei**.

Initial airflow: one included 140 mm front intake + one included 140 mm rear exhaust.

Arrival gates: cooler must be standard Phantom Spirit 120, not SE/EVO; case must be exact `BG074` with both included 140 mm PWM fans.

## Storage architecture — final

Purchased primary NVMe:

> **Crucial T710 2 TB `CT2000T710SSD8`** in `M.2_1` CPU PCIe 5.0 x4 under the motherboard heatsink.

`M.2_2` and `M.2_3` remain free for later additive expansion. Existing healthy SATA drives may be reused for cold data. No separate system/work SSD split, SSD cache, automatic tiering or RAID is required.

## PSU — final

Purchased:

> **be quiet! Pure Power 13 M 850W `BP027EU`**

Use only the modular cables supplied with this exact PSU.

## GPU / OS / mains policy

- reuse RTX 3060 until a concrete upgrade need appears;
- Windows 11 Pro x64 is the host OS; license already available;
- WSL2 + Ubuntu 26.04.1 LTS is the Linux environment;
- no UPS and no dedicated surge protector initially.

## Arrival gates

- CPU: `100-100000719WOF`, Box/WOF;
- motherboard: `90MB1LT0-M0EAY0`;
- RAM: `CP2K24G56C46U5`, 48 GB = 2x24 GB;
- cooler: Phantom Spirit 120 standard, not SE/EVO;
- case: `BG074`, non-window Airflow Black;
- SSD: `CT2000T710SSD8`, bare/non-heatsink;
- PSU: `BP027EU`, complete original modular cable set.

## Procurement position — 2026-09-01

**Procurement complete. No required new hardware remains to source.**

Current phase: physical identity/condition verification, then assembly and commissioning.
