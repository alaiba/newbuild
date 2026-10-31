# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Installed; BIOS identifies 9950X3D; box SKU not independently recorded** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Installed, POST passed; BIOS version 3287; retail box SKU not independently recorded** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24 GB) DDR5-5600 CL46-class, 1.1 V, non-ECC** | **Installed A2/B2; UEFI reports 49,152 MB DDR5-5600, EXPO off** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | Final |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Mounted with TF7; fans in middle + rear configuration; 36 °C BIOS idle** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Assembled; front/rear 140 mm fans connected** |
| Case airflow | **2x included 140 mm PWM: front intake + rear exhaust** | **CHA_FAN2 406 RPM front / CHA_FAN1 434 RPM rear at BIOS idle** |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Installed; UEFI detects CT2000T710SSD8 (2,000.3 GB)** |
| Bulk/cold storage | Reuse healthy existing SATA drives; `M.2_2` + `M.2_3` remain free | Final policy |
| Storage RAID/cache/tiering | None | Final |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Installed and operating; exact retail suffix not independently recorded** |
| GPU | Existing **RTX 3060 12 GB** | **Not yet installed, intentionally omitted for iGPU baseline** |
| Host OS | **Windows 11 Pro x64** | **Not yet installed; UEFI 8 GB USB detected** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Pending after Windows commissioning** |
| UPS | None initially | Final |
| Dedicated surge protection | None required | Final |

## Physical assembly and UEFI first-boot checkpoint — 2026-10-31

**Initial POST passed** without the RTX 3060 using the CPU's integrated graphics. BIOS 3287 detected 9950X3D (16 cores), 48 GB Crucial DDR5-5600 in A2/B2 (EXPO disabled), and the Crucial T710 `CT2000T710SSD8` 2 TB in M.2_1. At BIOS idle: CPU **36 °C**, motherboard **28 °C**, CPU_FAN **555 RPM**, CHA_FAN1 **434 RPM**, CHA_FAN2 **406 RPM**. No Windows installation or prolonged stability result has been recorded.

CPU cooler fans are deliberately positioned **middle + rear**, pushing toward case rear exhaust and avoiding the RAM overhang; they use a PWM Y-splitter on CPU_FAN, so only one CPU tachometer reading is expected. The 24-pin ATX and CPU EPS leads, F_PANEL, front USB-A/USB-C, HD_AUDIO and both chassis fans are connected. RTX 3060 and prior SATA drives remain disconnected for the initial OS baseline.

Before further operation, confirm both cooler fans spin, wires cannot enter blades, cooler mounting and side-panel clearance are correct. See `docs/bring-up-2026-10-31.md` for detailed observations and remaining validation.

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

Purchased from CEL.ro for **2,899.00 lei** and **received 2026-09-02**:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24 GB), DDR5-5600 CL46-class, 1.1 V, non-ECC UDIMM.**

Arrival verification passed from the supplied package photo: 48 GB total, 2x24 GB, DDR5-5600, CL46, UDIMM, AMD EXPO and Intel XMP 3.0 markings, with the matching Crucial Pro kit identity visible on the modules.

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

Purchased from Vexio and **received/verified 2026-09-15**:

- Thermalright Phantom Spirit 120 standard — **246.99 lei**;
- be quiet! Pure Base 501 Airflow Black `BG074` — **415.99 lei**.

Cooler verification passed from supplied photos: standard Phantom Spirit 120 branding with no SE/EVO suffix, dual-tower seven-heatpipe heatsink, both 120 mm fans, installation guide and accessory pack containing AM5 mounting hardware. For AM5 installation, retain the motherboard's original AMD backplate; the Intel backplate included in the cooler kit is not used. Remove the protective film/sticker from the cooler base before installation.

Case verification passed from supplied photos: shipping-box label explicitly identifies **`BG074 (Black)`**, and the chassis interior shows both included 140 mm fans. Initial airflow remains one included 140 mm front intake + one included 140 mm rear exhaust.

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
- RAM: **passed 2026-09-02** — `CP2K24G56C46U5`, 48 GB = 2x24 GB;
- cooler: **passed 2026-09-15** — Phantom Spirit 120 standard, dual 120 mm fans and AM5 hardware verified;
- case: **passed 2026-09-15** — `BG074` Black, both included 140 mm fans verified;
- SSD: `CT2000T710SSD8`, bare/non-heatsink;
- PSU: `BP027EU`, complete original modular cable set.

## Commissioning position — 2026-10-31

**Procurement complete; initial hardware assembly/UEFI POST passed.** Windows 11 Pro, sustained memory/CPU/SSD tests, GPU installation, WSL2/Ubuntu and BitLocker remain pending. Operational model detection is distinct from retail-box verification: CPU Box/WOF SKU, motherboard box SKU and PSU regional suffix were not independently recorded.

Maintain Auto/JEDEC memory defaults (EXPO off) for the initial Windows baseline, check whether BIOS 3287 requires a stable-release update, and delay BitLocker until firmware/driver/storage stability is confirmed.

