# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Purchased 2026-09-01 — EvoMAG; exact box SKU verification pending** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24 GB) DDR5-5600 CL46-class, 1.1 V, non-ECC** | **Selected / not yet purchased** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | **Selected** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected / not yet purchased** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected / not yet purchased** |
| Case airflow | **2× included 140 mm PWM: front intake + rear exhaust** | **Selected initial layout** |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| Bulk/cold storage | Reuse healthy existing SATA drives; `M.2_2` + `M.2_3` remain free for future expansion | **Selected policy** |
| Storage RAID/cache/tiering | **None** | **Selected** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| PSU fallback | Corsair RM850x 2024 850W `CP-9020270-EU` | **Obsolete fallback; primary PSU already purchased** |
| UPS | **None initially** | **Selected** |
| Dedicated surge protection | **None required** | **Selected** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163`** | **Selected / not yet purchased** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Purchase record — first executed order

On **2026-09-01**, the following EvoMAG order was placed:

| Item | Paid price incl. VAT |
|---|---:|
| AMD Ryzen 9 9950X3D Box | **3,349.99 lei** |
| ASUS TUF GAMING B650E-E WIFI | **785.99 lei** |
| Crucial T710 2 TB | **1,699.99 lei** |
| be quiet! Pure Power 13 M 850W | **683.99 lei** |
| **Hardware subtotal** | **6,519.96 lei** |
| Courier | **11.99 lei** |
| **Order total** | **6,531.95 lei** |

These four components are now **committed purchases**. Do not re-source or redesign around them unless the delivered item is incorrect, damaged, cancelled, or a material defect is discovered.

Detailed transaction record: `docs/purchases-2026-09-01.md`.

## Motherboard — final

Selected and purchased board: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

It satisfies the actual workstation requirements without paying for unused B850/Creator capabilities: PCIe 5.0 x16 graphics, CPU-direct Gen5 + Gen4 M.2 paths, a third chipset Gen4 x4 M.2, four SATA ports, BIOS FlashBack/Q-LED, adequate stock-load VRM margin, 2.5 GbE and Wi-Fi 6E.

The second physical x16 slot is only chipset PCIe 4.0 x1. That trade-off is accepted because no high-bandwidth add-in card is required.

**Arrival gate:** the EvoMAG order text identifies the B650E-E model, but the exact manufacturer part number must still be verified on the physical box before assembly. Required: `90MB1LT0-M0EAY0`.

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

These two components remain to be purchased.

## Storage architecture — final

Purchased primary NVMe:

> **Crucial T710 2 TB `CT2000T710SSD8`** in **`M.2_1` CPU PCIe 5.0 x4** under the motherboard heatsink.

Current use is about 600 GB, so 2 TB provides ample active-storage headroom. `M.2_2` and `M.2_3` remain empty for later additive expansion; existing healthy SATA drives remain available for cold data.

No separate system/work SSD split, SSD cache, automatic tiering or RAID is required.

## GPU policy

Reuse the RTX 3060 until a concrete upgrade need appears. No dual-GPU design.

## PSU — final

Purchased:

> **be quiet! Pure Power 13 M 850W `BP027EU`**

The 850 W model won because the premium over a comparable premium 750 W unit was small while retaining excellent acoustics, ATX 3.1 support and a long warranty. No 1000–1200 W provisioning is required.

## UPS / mains protection — final

No UPS and no dedicated surge protector initially. Use a properly earthed wall outlet or an ordinary reputable 16 A Schuko strip if extra outlets are needed.

## Hard purchase / arrival gates

### CPU
- AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`;
- **already purchased**; reject tray/OEM substitution on arrival.

### Motherboard
- ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`;
- **already purchased by model name**; verify exact physical box SKU before installation;
- do not accept B650-E `90MB1GT0-M0EAY0` or B650E-PLUS.

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
- Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink, in `M.2_1`;
- **already purchased**; verify exact variant on arrival.

### PSU
- be quiet! Pure Power 13 M 850W `BP027EU`;
- **already purchased**; use only its supplied modular cables.

### Windows
- Windows 11 Pro Retail/FPP English USB `HAV-00163`.

## Procurement position — 2026-09-01

Architecture and component selection are closed. Procurement is **partially complete**.

Purchased from EvoMAG: **CPU + motherboard + primary SSD + PSU**, order total **6,531.95 lei including 11.99 lei courier**.

Remaining to source: **RAM + CPU cooler + case + Windows license**.

For the four purchased components, stop price shopping and perform physical identity/condition verification when they arrive. For the remaining items, continue exact-model sourcing without relaxing the anti-substitution rules.

Detailed decisions: `docs/decisions.md`.
