# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Selected** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24 GB) DDR5-5600 CL46-class, 1.1 V, non-ECC** | **Selected** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | **Selected** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** |
| Case airflow | **2× included 140 mm PWM: front intake + rear exhaust** | **Selected initial layout** |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Selected** |
| Bulk/cold storage | Reuse healthy existing SATA drives; `M.2_2` + `M.2_3` remain free for future expansion | **Selected policy** |
| Storage RAID/cache/tiering | **None** | **Selected** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Selected** |
| PSU fallback | Corsair RM850x 2024 850W `CP-9020270-EU` | **Fallback only** |
| UPS | **None initially** | **Selected** |
| Dedicated surge protection | **None required** | **Selected** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163`** | **Selected purchase target** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Motherboard — final

Selected board: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

It satisfies the actual workstation requirements without paying for unused B850/Creator capabilities: PCIe 5.0 x16 graphics, CPU-direct Gen5 + Gen4 M.2 paths, a third chipset Gen4 x4 M.2, four SATA ports, BIOS FlashBack/Q-LED, adequate stock-load VRM margin, 2.5 GbE and Wi-Fi 6E.

The second physical x16 slot is only chipset PCIe 4.0 x1. That trade-off is accepted because no high-bandwidth add-in card is required.

## Memory — final

Selected kit:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24 GB), DDR5-5600 CL46-class, 1.1 V, non-ECC UDIMM.**

Why 48 GB:

- preserves **two DIMMs / 1DPC**, which is the preferred AM5 topology;
- preserves the Ryzen 9 9950X3D's official DDR5-5600 two-DIMM support path;
- current Romanian price is around **2,899 lei**, dramatically below the currently distorted 64/128 GB alternatives;
- larger capacities do not materially improve CPU performance while the active working set already fits;
- the trade-off is concurrency headroom, not raw CPU speed.

### Upgrade policy

Do **not** add another 2×24 GB pair later. AMD officially rates the 9950X3D at DDR5-3600 with four DIMMs versus DDR5-5600 with two DIMMs.

If real monitoring later shows persistent memory pressure, replace the current pair with a larger matched two-DIMM kit available at that time.

### Bring-up policy

1. Install the two modules in **A2/B2**.
2. Update to a current stable production BIOS.
3. Boot at **Auto/JEDEC**.
4. Confirm normal DDR5-5600 operation at conservative voltage.
5. Do not enable EXPO/XMP during initial commissioning unless later justified.
6. Run extended memory testing plus representative Java/Android/WSL workloads.
7. Record BIOS/AGESA, trained timings and voltages.
8. Monitor committed memory during real work to establish whether a future capacity replacement is actually needed.

## Cooling and chassis — final

- Thermalright Phantom Spirit 120 standard;
- be quiet! Pure Base 501 Airflow Black `BG074`;
- one included 140 mm front intake + one included 140 mm rear exhaust initially.

## Storage architecture — final

Use one primary NVMe:

> **Crucial T710 2 TB `CT2000T710SSD8`** in **`M.2_1` CPU PCIe 5.0 x4** under the motherboard heatsink.

Current use is about 600 GB, so 2 TB provides ample active-storage headroom. `M.2_2` and `M.2_3` remain empty for later additive expansion; existing healthy SATA drives remain available for cold data.

No separate system/work SSD split, SSD cache, automatic tiering or RAID is required.

## GPU policy

Reuse the RTX 3060 until a concrete upgrade need appears. No dual-GPU design.

## PSU — final

Selected:

> **be quiet! Pure Power 13 M 850W `BP027EU`**

The 850 W model won because the premium over a comparable premium 750 W unit was small while retaining excellent acoustics, ATX 3.1 support and a long warranty. No 1000–1200 W provisioning is required.

## UPS / mains protection — final

No UPS and no dedicated surge protector initially. Use a properly earthed wall outlet or an ordinary reputable 16 A Schuko strip if extra outlets are needed.

## Hard purchase gates

### CPU
- AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`.

### Motherboard
- ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`;
- do not substitute B650-E `90MB1GT0-M0EAY0` or B650E-PLUS.

### RAM
- exact **Crucial Pro `CP2K24G56C46U5`** matched **2×24 GB** kit;
- non-ECC UDIMM;
- DDR5-5600, 1.1 V-class conservative operation;
- install A2/B2;
- no planned four-DIMM expansion.

### Cooler
- Thermalright Phantom Spirit 120 standard; no SE/EVO substitution.

### Case
- be quiet! Pure Base 501 Airflow Black `BG074` with both included 140 mm fans.

### Storage
- Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink, in `M.2_1`.

### PSU
- be quiet! Pure Power 13 M 850W `BP027EU`;
- use only its supplied modular cables.

### Windows
- Windows 11 Pro Retail/FPP English USB `HAV-00163`.

## Procurement position — 2026-08-31

Architecture and component selection are now closed, including RAM at **48 GB / 2×24 GB**. Perform a same-day price/provider refresh before payment, especially for the exact RAM kit and exact B650E-E motherboard.

Detailed decisions: `docs/decisions.md`.
